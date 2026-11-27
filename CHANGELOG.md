# Changelog

Release history for MetrixRTA, newest first. Dates are GitHub publication dates in Australia/Perth (UTC+08:00). Only published versions are listed.

MetrixRTA is free to use, closed-source software. All rights reserved. All versions below are pre-releases. For downloads, checksums, screenshots, and version-specific instructions, follow the linked release titles.

This file is the consolidated release history; separate per-version release-note files are no longer maintained.

## [0.4.0](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.4.0) - 2026-11-26 (pre-release)

### Audio transport and rendering architecture

Audio input and output have been moved to isolated processes using shared memory, an input ring buffer, and dual-bank PCM output buffering.

FFT computation, averaging, geometry preparation, and spectrum rendering run in a dedicated process independently of the GUI and measurement DSP. Rasterization, graphics caching, interprocess communication, and memory management have been optimized.

## [0.3.8](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.8) - 2026-11-22 (pre-release)

### New: Dual-Channel Analysis

Added 11 dual-channel analysis modes:

- Channel Addition and Averaging
- Real Transfer Function (L/R, R/L)
- Cross Spectrum (L/R, R/L)
- Complex Transfer Function (L/R, R/L)
- Coherence Function
- Complex Transfer + Coherence (L/R, R/L)

Features include spectral averaging, independent channel analysis, magnitude and phase measurements, interactive graph scaling, coordinate cursors, annotations, and overlays with measurement metadata.

### New: Multitone31 Spectral Profiles

Added two selectable spectral profiles for the 31-tone generator:

- **Equal Amplitude:** Original profile with equal-amplitude tones.
- **Music-shaped:** Frequency-dependent tone amplitudes with a pink-noise-like slope of approximately -3 dB/octave.

Both profiles retain the original tone frequencies and phases, with automatic peak-level normalization.

## [0.3.7](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.7) - 2026-11-20 (pre-release)

### Highlights

This release introduces **dual-channel cross-correlation analysis** for high-sensitivity amplitude and phase noise measurements.

By averaging complex cross-spectra from two independent ADC channels, MetrixRTA progressively suppresses uncorrelated measurement noise, allowing AM and PM noise to be measured below the noise floor of either individual channel.

**Key features:**

- **Complex cross-spectrum averaging (XAVG):** Suppresses uncorrelated channel noise while preserving correlated noise from the device under test.
- **Continuous and Fixed Count modes:** Accumulate measurements continuously or stop automatically after a selected number of independent blocks.
- **Selectable cross-spectrum estimators:** Magnitude and abs(I), providing different approaches to extracting correlated noise.
- **Real-time AM/PM noise spectra:** Separate amplitude and phase noise density curves in dBc/Hz, plotted against frequency offset from the carrier.
- **Integrated noise measurements:** AM Noise, PM Noise, AM RMS, PM RMS, and RMS time jitter over a selectable offset range.
- **Detection limit visualization:** Displays estimated AM/PM measurement limits to help assess the significance of low-level noise results.

Cross-correlation is particularly useful when the noise of the device under test approaches or falls below the noise floor of the measurement ADCs.

The existing single-channel AM/PM noise analysis remains available and unchanged.

**Note:** Effective noise suppression requires two sufficiently independent measurement channels. Noise correlated between the channels is not rejected by cross-correlation.

## [0.3.6](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.6) - 2026-11-15 (pre-release)

### Highlights

- Measurement History
- IM3 asymmetry

This pre-release introduces a built-in measurement history system for recording, browsing, and replaying measurement results.

**Key features:**
- **Automatic recording:** Capture live spectra, measurement results, and settings.
- **History Browser:** Browse recordings grouped by DUT, measurement type, or date.
- **Playback:** Replay recorded measurements at adjustable speeds or review the final results of Step Tests.
- **Recorded Settings:** Review FFT, generator, scaling, and measurement configurations.
- **Text-based results:** View recorded measurement results in a numerical table with configurable column visibility.
- **CSV export:** Export recorded measurement results to CSV, including only the selected columns.
- **Diagnostics:** Save Audio I/O diagnostics with recordings and review them during playback.
- **File formats:** New `.mtrx` format - 1 file for 1 history record.
- **File management:** Open external recordings, delete individual files, or clear the history.
- **Screenshots:** Save or copy measurement displays during playback.

Recordings contain displayed measurement data without storing raw PCM or FFT arrays, keeping files compact.

To access Measurement History, click the History button in the left control panel.

**MetrixRTA now supports IM3 Asymmetry analysis using a two-tone test signal.**

The feature measures the upper and lower third-order intermodulation products (2f1 - f2 and 2f2 - f1) and calculates their level difference in dB.

Unlike conventional IMD measurements, IM3 Asymmetry reveals differences between the two distortion products, helping investigate frequency-dependent nonlinearities, amplifier behavior, and possible memory effects in audio devices.

How to use: Select IM3 Asymmetry in the Measurement menu, then select Two-tone in the Generator and open Options to configure the center frequency and tone spacing. Results are displayed in real time alongside individual IM3 levels.

## [0.3.5](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.5) - 2026-11-07 (pre-release)

### Highlights

- Added custom WAV file support in **Generator → Signal type → Custom file…**.

## [0.3.4](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.4) - 2026-11-05 (pre-release)

### Highlights

- Minor DSP improvements. Measurement results are unchanged.

## [0.3.3](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.3) - 2026-10-28 (pre-release)

### Highlights

Version 0.3.3 introduces **Step Tests** for automated distortion measurements versus frequency and signal level.

Step Tests are available in the **Measurement** menu.

- **Frequency Step Test:** measure distortion across a user-defined frequency range with selectable step intervals.
- **Level Step Test:** measure distortion versus signal level with adjustable level range, step density, and spacing.
- **Measurement types:** THD, THD+N, CCIF IMD, SMPTE IMD, TD+N Multitone, DIM30, and DIM100.
- **Harmonic analysis:** display individual H2-H9 curves with independent visibility controls.
- **Dual-channel measurements:** simultaneous measurement and comparison of left and right channels.
- **Measurement stabilization:** automatic settling and stability verification before accepting measurement points.
- **Interactive plots:** selectable curves, linear and logarithmic axis scaling, automatic range adjustment, and configurable visualization.
- **Calibration:** display measured input levels in dBFS, normalized dBr, voltage, or power using the calibration settings from the main Spectrum.
- **Advanced overlay system:** save, organize, rename, and compare multiple measurement curves. Each overlay retains associated measurement metadata, allowing results to be reviewed and compared with their original measurement context.
- **Measurement persistence:** collected curves remain available after the test is completed, allowing individual distortion components to be examined without repeating the measurement.

## [0.3.1](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.1) - 2026-10-20 (pre-release)

### Highlights

Calibration options are available in the **Scaling** menu.

- **Manual voltage calibration:** enter a digital reference level and its corresponding voltage in RMS, peak, or peak-to-peak units.
- **Measured voltage calibration:** apply a reference sine wave and enter its known voltage. The program measures the digital signal level to calculate the calibration factor.
- **Voltage units:** display calibrated levels in V, dBV, or dBu.
- **Power units:** display calculated power in W, mW, µW, nW, dBm, or dBW using RMS voltage and a user-defined load resistance: P = V²/R.
- **Channel handling:** separate channels use their own calibrations. In two-channel overlay mode, both channels use the calibration and display settings of the first channel — Left, or the first selected ASIO channel.
- **Normalization:** normalization to 0 dBr is disabled while physical-unit calibration is active.

## [0.3.0](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.3.0) - 2026-10-01 (pre-release)

### Release overview

The published notes summarize the capabilities available in this version; they do not identify every feature as newly introduced.

Key features:

- Real-time FFT analysis with FFT sizes up to 8M points, linear and logarithmic frequency scales, averaging, Peak Hold, and multiple FFT window functions.
- Support for sample rates up to 768 kHz.
- THD, THD+N, and THD/THD+N vs Frequency measurements.
- IMD CCIF and SMPTE, DIM30 and DIM100.
- Multitone TD+N and AM Level measurements.
- AM and PM noise analysis.
- Waveform mode for time-domain signal analysis, including simultaneous display of the input signal and residual during distortion measurements.
- Spectrum and Noise Density display modes.
- Measurement Details with a detailed breakdown of measurement results, including the formulas used, intermediate values, and substitution of actual measured values directly into the formulas.
- Built-in test signal generator and Digital Loopback mode.
- Independent input and output audio interface selection, including native WASAPI Exclusive and ASIO.
- Interactive plot scaling and configuration, with day and night display modes.

## [0.2.8](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.2.8) - 2026-09-10 (pre-release)

### Highlights

MetrixRTA 0.2.8 is a Windows x64 pre-release focused on the measurement workspace, generator controls, audio-I/O reliability, and real-time display performance.

- Reworked the Measurement and Generator panels with measurement-specific Settings dialogs and global generator controls.
- Made FFT-bin frequency alignment and phase inversion global generator options for all tonal signals.
- Kept the user-entered tone frequency unchanged while applying any internal generator alignment.
- Added clearer Fs IN and Fs OUT status fields and improved Digital loopback handling.
- Improved WASAPI and ASIO probing, readiness reporting, and protection against transient invalid sample rates.
- Added latest-frame display scheduling so FFT presentation keeps the newest available frame without building a frame queue.
- Synchronized THD and Residual waveform processing at up to 8 Hz. Waveform uses the same time-domain FFT block and completed fundamental frequency as THD.
- Reduced redundant waveform and measurement processing, including selected-channel waveform acquisition and NumPy hot-path optimizations.
- Improved FFT-only diagnostics and measurement details while keeping Settings responsive during RUN.

## [0.2.7](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.2.7) - 2026-09-09 (pre-release)

### Highlights

- Reorganized and streamlined the FFT, Generator, FFT display, and View sections.
- Combined normalization, frequency weighting, and frequency-response compensation in the Scaling dialog.
- Improved channel-mode controls, including channel-copy modes and linked frequency-scale settings in overlay mode.
- Redesigned measurement-bandwidth controls with validation and a Full-range button.
- Improved measurement result panels, normalization behavior, SINAD/ENOB calculations, and external-generator fundamental tracking.
- Added spectrum day/night mode and multiple visual consistency improvements.
- Fixed several startup, measurement-panel, normalization, and generator-control issues.

## [0.2.3](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.2.3) - 2026-09-07 (pre-release)

### Added

- Compact per-channel result panels displayed directly over the spectrum
- Draggable and collapsible result panels with positions saved in the configuration
- Clickable result values that open detailed measurement information
- Copy-to-clipboard support for screenshots
- Day/night spectrum theme with an adaptive high-contrast palette
- Compact contact and tip controls in the status area

### Changed

- The former lower results table was removed and the spectrum now uses the released space
- Two-channel measurements show an independent result panel for each channel
- Measurement headings, bandwidth labels, Phase and Time actions were consolidated in the new panels
- Screenshot control-panel selection now includes or excludes both side panels
- Input and output status presentation was made more compact and informative
- Startup and redraw sequencing was consolidated to reduce redundant painting and panel flicker

## [0.2.2](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.2.2) - 2026-09-07 (pre-release)

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

## [0.2.1](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.2.1) - 2026-09-06 (pre-release)

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

## [0.2.0](https://github.com/MetrixRTA/MetrixRTA/releases/tag/v0.2.0) - 2026-08-30 (pre-release)

First public preview release of MetrixRTA.

### Added

- Real-time FFT spectrum analysis
- THD and THD+N measurement
- THD+N vs time measurement mode
- AM level measurement
- Centralized results table with calculation details
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
- Tips are completely voluntary and do not unlock any additional features.
- The application is distributed as closed-source software.
- The application source code is not published.
