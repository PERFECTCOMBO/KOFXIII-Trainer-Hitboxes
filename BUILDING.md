# Building the native components

Requirements: Windows, Visual Studio 2022 C++ Build Tools (x86 compiler),
Windows SDK, and PowerShell. The game is 32-bit even on 64-bit Windows.

## Trainer and recording bridge only

```powershell
./build.ps1 -TrainerOnly
```

This builds `KOF13RecordingSlots.dll` and `KOF13InputChain.dll`, and runs the
recording regression tests. It does not need a debug executable.

## All four native DLLs

The genuine SNK renderer needs proprietary inputs, supplied locally. Install
Python 3 and the extractor dependencies in a virtual environment:

```powershell
python -m venv .venv
./.venv/Scripts/python -m pip install pefile unicorn capstone
./.venv/Scripts/python extract-snk.py --debug-exe "<debug-folder>/game.exe" --shader-dir "<steam-game-folder>/shader"
./build.ps1
```

The extractor accepts only the following debug executable SHA-256:

`d2e8e374f844f477874fa47cec20a8b66101ec1fb903ada2512cb926a3c1d806`

It validates both collision shader hashes, recovers the original geometry,
and generates the draw-loop and shader headers locally. No PDB is required.
The Steam game is the runtime target; the debug executable is a build input.

Outputs in `build/`: `dinput8.dll`, `KOF13InputChain.dll`,
`KOF13NativeHitboxes.dll`, `KOF13RecordingSlots.dll`.
Compiler output is not expected to be byte-identical across toolchain versions.

The supported Steam `game.exe` SHA-256 is:

`e7718f5c553de852135ddef5833a7bb6eafd05508d1206ac6f3ce7767b474835`

Unsupported builds are deliberately refused.

## Testing and integration

`build.ps1` runs focused tests against the production recording implementation:
nonempty-slot eligibility, repeated selections, empty-bank rejection, variable
recording lengths, allocation-failure rollback, and the offline guard.
These tests do not replace an in-game rendering or OBS capture test.

The script only builds locally; it never installs into a game directory.
For integration, start with an isolated copy of the supported Steam game and
the Beta 7 release installed, close the game, then replace its four native DLLs
with your build outputs. The release's modified Lua/GFX menu resources are
still required: this is not a source-only rebuild of those proprietary resources.
Do not put generated headers, game files, recordings or build outputs into commits.
