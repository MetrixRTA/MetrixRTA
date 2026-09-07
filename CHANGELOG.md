# Changelog

All notable changes to MetrixRTA are documented here.

## [0.2.3] - 2026-09-07 (pre-release)

### Added

- Compact per-channel result panels displayed directly over the spectrum
- Draggable and collapsible result panels with positions saved in the configuration
- Clickable result values that open detailed measurement information
- Copy-to-clipboard support for screenshots
- Day/night spectrum theme with an adaptive high-contrast palette
- Compact contact and donation controls in the status area

### Changed

- The former lower results table was removed and the spectrum now uses the released space
- Two-channel measurements show an independent result panel for each channel
- Measurement headings, bandwidth labels, Phase and Time actions were consolidated in the new panels
- Screenshot control-panel selection now includes or excludes both side panels
- Input and output status presentation was made more compact and informative
- Startup and redraw sequencing was consolidated to reduce redundant painting and panel flicker

## [0.2.2] - 2026-09-07 (pre-release)

### Added

- Per-channel level calibration with manual Offset and one-click Norm controls
- Relative dBr presentation for calibrated input measurements
- Persistent text and arrow annotation objects on the spectrum
- Native Windows font and arrow-color selection for spectrum annotations
- Configurable screenshot filename prefixes with automatic numbering
- Optional inclusion of the control panel in screenshots

### Changed

- The GUI is more responsive through consolidated frame updates and fewer redundant redraws
- Mode and control changes are presented atomically instead of repainting interface sections sequentially
- The spectrum viewport remains stable while controls and measurement modes change
- Capture and generator controls operate independently and preserve their intended state while devices reconnect
- Screenshot capture and spectrum annotation workflows are integrated into the STOP-mode interface

## [0.2.1] - 2026-09-06 (pre-release)

### Added

- THD / THD+N vs Frequency measurement with FFT-bin-aligned fractional-octave steps
- Selectable 1, 1/3, 1/8, and 1/24 octave frequency-step sizes
- Named THD and THD+N traces with overlay support
- Per-step progress display and automatic completion after the final frequency
- Input-tone detection and fresh FFT capture windows for reliable step transitions
- Global Show BW control
- DUT-based screenshot folders under Measurements with automatic numbering

### Changed

- Measurement-mode changes now stop capture and generator before applying the new mode
- Frequency-step limits account independently for input and output sample rates
- Measurement result columns are selected centrally for each measurement mode
- WASAPI format lists remain available after runtime validation
- Frequency-step stability checks both channels independently using frequency, level, THD, and THD+N

## [0.2.0] - 2026-08-30 (pre-release)

First public preview release of MetrixRTA.

### Added

- Real-time FFT spectrum analysis
- THD and THD+N measurement
- THD+N vs time measurement mode
- CCIF IMD measurement
- SMPTE IMD measurement
- TD+N Multitone measurement
- Measurement within a user-defined frequency bandwidth (BW)
- Frequency weighting modes: A, C, Z, ITU-R 468, and RIAA
- Native WASAPI audio input and output
- Native ASIO audio input and output
- Independent ASIO input and output drivers
- Independent input and output sample rates
- High sample rate support up to 768 kHz with compatible hardware
- Two-channel spectrum analysis
- Multiple channel display modes
- Linear and logarithmic frequency-axis display
- Configurable FFT size
- Multiple FFT window functions
- Spectrum averaging
- Spectrum overlays
- Overlay subtraction and averaging
- Built-in signal generators for supported measurement modes
- Audio device capability probing
- Automatic recovery after audio device reconnection
- Support for saving application settings
- Support for saving and loading spectrum overlays

### Notes

- This is an early public preview release.
- MetrixRTA is under active development.
- Features, measurement modes, and the user interface may change in future versions.
- MetrixRTA is free to use.
- Donations are completely voluntary and do not unlock any additional features.
- The application is distributed as closed-source software.
- The application source code is not published.
