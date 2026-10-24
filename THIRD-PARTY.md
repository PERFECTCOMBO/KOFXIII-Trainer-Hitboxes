# License scope and third-party material

The root MIT license covers the project's custom native trainer, loaders,
renderer adapters, build/extraction tooling, tests and documentation.
Retain the original KoF XIII Hitbox Viewer attribution and permission notice
in `Original-KOF13-Hitbox-Viewer.txt` for the viewer-derived work.

SNK owns the original game, debug renderer implementation, collision shaders,
game scripts, compiled menus, artwork and other game resources. These are not
relicensed under MIT. Screenshots show SNK game artwork and are documentation,
not MIT-licensed artwork. Steam belongs to Valve. This project is unofficial.

`extract-snk.py` generates `snk-renderer/original-loop.h` and
`snk-renderer/original-shaders.h` from files supplied locally by the builder.
Those generated files and resulting embedded SNK material are excluded from
the MIT license and source control. The extractor is custom source; the data
it extracts is not. This repository does not distribute the debug executable.

The downloadable Beta 7 bundle also contains modified game-dependent Lua and
GFX resources. Their editable source/build pipeline is not included here;
the native source release does not claim that the whole bundle or game is MIT.

Build dependencies (MSVC, Windows SDK, Python, pefile, Unicorn, Capstone) retain
their respective licenses. They are not vendored in this repository.
