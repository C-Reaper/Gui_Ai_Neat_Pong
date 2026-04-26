## Overview
This project is a simple Pong game implemented in C, featuring AI opponents trained using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. The game supports multiple platforms and build configurations.

## Features
- Basic Pong game mechanics.
- Multiplayer mode with single-player AI opponents.
- Training of AI players using NEAT algorithm for improved gameplay over generations.
- Cross-platform support:
  - Linux (Makefile.linux)
  - Windows (Makefile.windows)
  - WebAssembly (Makefile.web)
  - Wine (Makefile.wine)

## Project Structure
```
<project>/
├── build/              # .exe files produced by Main.c
├── src/
│   ├── Main.c          # Entry point
│   └── *.h             # Standalone Header-based C-files, without *.c files that implement them
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
└── Makefile.web        # Emscripten Build configuration
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11 for GUI, ALSA for audio (if required).
  - Windows: WINAPI.
  - WebAssembly: Emscripten SDK.

## Build & Run
### Building the Project
To build the project on a specific platform, navigate to the project directory and run:
```bash
make -f Makefile.(os) all
```
Where `(os)` can be `linux`, `windows`, `wine`, or `web`.

For clean rebuilds:
```bash
make -f Makefile.(os) clean
make -f Makefile.(os) all
```

### Running the Project
To execute the compiled binary, use:
```bash
make -f Makefile.(os) exe
```

Each platform has its own specific build and run instructions in the respective Makefile.