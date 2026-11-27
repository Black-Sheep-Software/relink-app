<div align="center">
  <img src="relink-mark.svg" alt="ReLink logo" width="100" height="100">

# ReLink

**Your controller has more games to play.**

[![Project status: development preview](https://img.shields.io/badge/status-development%20preview-087d74)](https://www.relink-app.co.uk/#status)
[![Linux: testing](https://img.shields.io/badge/Linux-testing-101827)](https://www.relink-app.co.uk/#status)
[![Windows: testing](https://img.shields.io/badge/Windows-testing-101827)](https://www.relink-app.co.uk/#status)

[Website](https://www.relink-app.co.uk) · [Preview downloads](https://github.com/Black-Sheep-Software/relink-app/releases/latest) · [Getting started](GETTING_STARTED.md) · [Report an issue](https://github.com/Black-Sheep-Software/relink-app/issues)

</div>

ReLink is an independent project by Black Sheep Software, giving Stadia Controllers more ways to play compatible games on a computer. Its current Wi-Fi preview uses a Raspberry Pi receiver and companion apps for Windows and Linux.

## Development preview

ReLink is still being built and tested; it is not a finished general release. The [latest release](https://github.com/Black-Sheep-Software/relink-app/releases/latest) contains development packages for testing with an existing ReLink Pi receiver. A complete, supported Pi installation guide is not yet available.

- **Native Wi-Fi:** real controller input and rumble have been demonstrated with a ReLink-controlled receiver. Multiple Wi-Fi controllers can be connected at once and assigned to separate computers through the receiver dashboard; reconnection after a restart or update is still occasionally slower than expected.
- **Windows and Linux:** desktop companion previews connect to the Pi and provide connection, controller and battery status. Windows and Linux gameplay have been tested; compatibility with all games and systems has not been established.
- **USB and Bluetooth:** controller input through earlier ReLink development paths has been tested on Linux. The current Pi companion packages are for the Wi-Fi receiver and should not be assumed to provide those paths directly.
- **Headset audio:** PC game audio to the controller's headset has been confirmed working on real hardware on both Windows and Linux. It can still occasionally cut out during play or take a while to resume after a controller reconnects; both are known, unresolved issues.
- **Microphone:** controller-to-PC microphone support is not available in this release. A working version exists in development but needs either a driver signing step we can't yet ask ordinary users to do, or a content bug fixed in its simpler fallback; see [Getting started](GETTING_STARTED.md#known-limitations) for details.
- **Updates:** the Pi can retrieve verified releases from GitHub and paired clients can obtain updates from the Pi. The Windows update flow has been tested end to end, including the in-app update button; the Linux update button and additional recovery scenarios still need testing.

The previews require a compatible, configured receiver; downloading a client by itself does not set one up. See [Getting started](GETTING_STARTED.md) for what the current packages do and what to expect.

## Feedback and support

Found a problem or have an idea? Open an [issue](https://github.com/Black-Sheep-Software/relink-app/issues). Include your ReLink build, operating system, receiver setup, expected behaviour and what happened. Please remove personal information, pairing codes, passwords and controller identifiers from reports and screenshots.

---

ReLink is an independent project and is not affiliated with Google.
