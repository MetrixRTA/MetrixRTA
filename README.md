# MetrixRTA

Real-time audio spectrum and distortion analyzer for Windows.

MetrixRTA is a Windows application for real-time FFT spectrum analysis and audio measurement.

## Features (so far)

- Real-time FFT spectrum analysis
- THD / THD+N measurement
- CCIF IMD measurement
- SMPTE IMD measurement
- TD+N Multitone measurement
- WASAPI and ASIO support
- High sample rate support
- Two-channel analysis
- Spectrum averaging and overlays

## Download

Download the latest version from the **Releases** section of this repository.

This repository contains documentation and binary releases only.  
The application source code is not published.

## System requirements

- Windows 10 / Windows 11
- x64 system
- WASAPI or ASIO compatible audio device

## File verification

For every release, a SHA-256 checksum is published.

To verify a downloaded file in Windows:

```cmd
certutil -hashfile MetrixRTA.exe SHA256

## MetrixRTA is free software.

If you find it useful, you can optionally support its continued development.
Donations are completely voluntary and do not unlock any additional features.
