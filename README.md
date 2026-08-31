# MetrixRTA

Real-time audio spectrum and distortion analyzer for Windows.

MetrixRTA is a Windows application for real-time FFT spectrum analysis and audio measurement.

## Features

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

Download the latest version from the [Releases](https://github.com/MetrixRTA/MetrixRTA/releases) section of this repository.

This repository contains documentation and binary releases only.

The application source code is not published.

## System requirements

- Windows 10 / Windows 11
- x64 system
- WASAPI or ASIO compatible audio device

## File verification

A SHA-256 checksum is published for each release.

To verify a downloaded file in Windows:

~~~cmd
certutil -hashfile MetrixRTA.exe SHA256
~~~

Compare the resulting SHA-256 hash with the checksum published on the corresponding GitHub release page.

## Security

Official MetrixRTA releases are distributed through this GitHub repository.

You can additionally scan the downloaded file with Microsoft Defender, VirusTotal, or another antivirus service before running it.

## Support MetrixRTA

MetrixRTA is free to use.

If you find it useful, you can optionally support its continued development.

Donations are completely voluntary and do not unlock any additional features.

Support with ko-fi: https://ko-fi.com/metrixrta

## Screenshots

![MetrixRTA screenshot](screenshots/Screenshot_1.png)

![MetrixRTA screenshot](screenshots/Screenshot_2.png)

![MetrixRTA screenshot](screenshots/Screenshot_3.png)

![MetrixRTA screenshot](screenshots/Screenshot_4.png)

## License

MetrixRTA is distributed as closed-source software.

All rights reserved.
