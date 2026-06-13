# Marlin 3D Printer Firmware (BTT SKR Mini E3 V3.0 Fork)

## Project Overview
This repository is a fork of Marlin Firmware with the specific goal of utilizing the **BigTreeTech (BTT) SKR Mini E3 V3.0** control board for generic G-code based motion control. The firmware is being adapted to provide a flexible platform for motion control beyond traditional 3D printing.

### Agent Constraints
- **NO BUILDING OR TESTING:** The AI agent is strictly forbidden from executing build or test commands (e.g., `platformio run`, `make`, etc.). All building and testing will be performed manually by the user.

### Key Technologies
- **Languages:** C++, Python (for build scripts).
- **Build Systems:** PlatformIO (preferred), Arduino IDE, Makefile.
- **Architectures:** AVR, STM32, ESP32, LPC176x, SAMD21/51, RP2040, etc.
- **Core Components:** Planner (motion control), Stepper (interrupt-driven motor control), Temperature (PID control), G-code (command parsing).

## Building and Running
The preferred way to build Marlin is using **Visual Studio Code** with the **PlatformIO** extension or the **Auto Build Marlin** extension.

### Key Commands
- **Build (PlatformIO CLI):** `platformio run -e <environment>`
- **Build (Make):** `make marlin`
- **Default Environment:** `mega2560` (defined in `platformio.ini`).
- **Clean:** `platformio run -t clean` or `make clean`.

### Configuration
1.  **Select Motherboard:** Identify your board in `Marlin/src/core/boards.h`.
2.  **Basic Settings:** Edit `Marlin/Configuration.h` to set `#define MOTHERBOARD BOARD_...` and configure machine-specific parameters (geometry, endstops, etc.).
3.  **Advanced Settings:** Edit `Marlin/Configuration_adv.h` for fine-tuning features.

## Testing
Marlin includes both build-time tests (to ensure configurations compile) and unit tests for core logic.

- **Run all unit tests:** `platformio run -t test-marlin` or `make unit-test-all-local`.
- **Run a specific unit test:** `platformio run -t marlin_<test-suite-name>` or `make unit-test-single-local UNIT_TEST_CONFIG=<test-name>`.
- **Run all build tests:** `make tests-all-local`.
- **CI Environment:** Tests are automatically run via GitHub Actions (`.github/workflows/`).

## Architecture
- `Marlin/src/HAL`: Platform-specific implementations for different MCUs.
- `Marlin/src/module`: Core functional modules (Planner, Stepper, Temperature, Settings).
- `Marlin/src/gcode`: G-code parsing and command handlers.
- `Marlin/src/inc`: Configuration management, macros, and sanity checks (`SanityCheck.h`).
- `Marlin/src/pins`: Pin definitions for supported motherboards.
- `buildroot/`: Scripts, tools, and shared assets used during the build process.

## Development Conventions
- **License:** GPL-V3.0.
- **Coding Style:** Marlin follows specific coding standards (see [Marlin Documentation](https://marlinfw.org/docs/development/coding_standards.html)).
- **Configuration Validation:** `Marlin/src/inc/SanityCheck.h` is used to validate configuration combinations at compile-time.
- **Contributing:** Submit patches to the `bugfix-2.1.x` branch.
- **Formatting:** Use `make format-pins` for pins files and `make validate-lines` for general text formatting (uses Prettier).
