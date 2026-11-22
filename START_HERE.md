# Atomic-AGD-Script-Compiler: start here

The AGD (Arcade Game Designer) script compiler, originally by Jonathan Cauldwell (ZX Spectrum/CPC), Acorn Atom version by Kees van Oss (oss003). This copy carries KC's 2018 changes towards a BBC Micro target (MODE 1 colour, sideways RAM). A C command-line tool.

| | |
|---|---|
| GitHub | https://github.com/kieranhj/Atomic-AGD-Script-Compiler (public; not a GitHub fork, but its history is Kees's) |
| Upstream | `oss003` remote = https://github.com/oss003/Atomic-AGD-Script-Compiler (31 of the 43 commits are oss003's) |
| Local path | D:\beeb\mine\Atomic-AGD-Script-Compiler (moved from OneDrive\BEEB\Repos\Atomic-AGD-Script-Compiler in the 2026-11 tidy) |
| Branch | mode1-colour (checked out); others: master (9 commits ahead of origin/master), block-attributes, compiler-investigation, wip/2026-11-tidy |
| Last commit | 2018-08-16: Sideways RAM changes |

## What's in here
- `AGD6.c`: the compiler source (one file). `engine.inc`: the 6502 engine it emits code against.
- `AGD.exe`: a checked-in Windows build.
- `AGD\`: a Visual Studio project (`AGD.sln`, `AGD.cpp`, Debug/Release), gitignored, so local only.
- `makefile`: `gcc -o AGD.exe AGD6.c`. `GNUmakefile`: Windows wrapper (see below).

## Build and run
- `make` from Windows Terminal (PowerShell) works (verified 2026-11-22): builds `AGD.exe` from `AGD6.c` with MSYS2 UCRT64 gcc 15.2, no warnings; `AGD.exe` with no arguments prints its usage banner. `GNUmakefile` (read before `makefile`) runs recipes in Git's `sh.exe` with `C:\msys64\ucrt64\bin` on PATH. The `makefile` target was renamed `AGD` -> `AGD.exe` because `AGD` collided with the gitignored `AGD\` folder (make said "up to date").
- Note: `AGD.exe` is tracked (the 2018 Visual Studio build), so `make` overwrites it and it then shows as modified. `git checkout AGD.exe` restores the 2018 build. `make` compiles the working copy of `AGD6.c`, including the uncommitted change below.
- In practice the compiler was built with Visual Studio (`AGD\AGD.sln`) and copied into Atomic-AGD-Suite (`BBC Suite\AGD\AGD.exe`).

## Local changes
- Uncommitted: `AGD.exe` (rebuilt by `make` on 2026-11-22, see above) and `AGD6.c` (+10/-5). The same diff is saved on branch `wip/2026-11-tidy` (pushed), the snapshot taken before the move.
- Local `master` is 9 commits ahead of `origin/master` (unpushed; includes the 2018-08-13 merge of oss003/master).

## Status and next steps
- Left in August 2018 mid-experiment (MODE 1 colour, SWRAM). No TODO/plan notes here; see `BBC Suite\notes.txt` in Atomic-AGD-Suite for the design notes.

## See also
- README.md. D:\beeb\mine\Atomic-AGD-Suite (the suite that uses this compiler).
