# AGENTS.md — hello_c_gtk

## What this is
A C example demonstrating GTK4 cross-compilation for Linux and Windows (32/64-bit).

## Stack
- C
- GTK4 (`libgtk-4-dev`)
- GNU Make
- Docker (cross-compile container `myridia/fedora_cross_compile`) for Windows builds

## Build
Linux:
```bash
make linux
```
Windows (inside the cross-compile Docker container):
```bash
docker run --name hello_gtk -it --rm -v "$(pwd)":"/root/src" myridia/fedora_cross_compile /bin/bash
./makewindows.sh
```

## Run
`./helloc_gtk_linux` on Linux; Windows exes may need GTK dlls from `bin32.tar.gz` / `bin64.tar.gz` (`/usr/...-mingw32/sys-root/mingw/bin/` on the Fedora container).

## Structure
- `hello.c` — GTK4 source
- `Makefile` — build targets
- `makewindows.sh` — Windows cross-build
- `enter.sh` — helper to enter the build container
- `bin32.tar.gz` / `bin64.tar.gz` — runtime DLLs for 32/64-bit Windows

## Conventions
- No comments in code unless asked.
- Verify: `make linux && ./helloc_gtk_linux`
