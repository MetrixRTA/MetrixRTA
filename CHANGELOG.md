# Changelog

All notable changes to MetrixRTA are documented here.

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
