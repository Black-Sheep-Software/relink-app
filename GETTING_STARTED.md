# ReLink development preview

The current preview connects Stadia Controllers using their original Wi-Fi firmware to a ReLink receiver on a Raspberry Pi, which sends controller input to paired Windows or Linux computers. This is early test software, not a finished consumer installation. A complete, supported Pi setup package and guide are still being developed; the client downloads alone do not create a receiver.

## What you need

- A Stadia Controller running its original Wi-Fi firmware and a compatible, already configured ReLink Pi receiver with its controller network running.
- A Windows or Linux computer that can reach the receiver's management dashboard on the local network. Multiple controllers can be connected at once and assigned to separate computers through the dashboard; see [Pair and assign a controller](#pair-and-assign-a-controller) below.
- A current development preview from the [releases page](https://github.com/Black-Sheep-Software/relink-app/releases/latest). Check the release notes for the exact build and known limitations.

The Bluetooth firmware is a different controller mode; the Wi-Fi receiver requires the original Wi-Fi firmware. Do not assume firmware conversion or recovery is reversible. Keep the Pi dashboard on a trusted local network and protect its sign-in and pairing codes.

## Choose a download

- **Windows first installation:** choose the file named `ReLink-Setup-…exe`. Setup asks for administrator approval and installs the app and any needed virtual-controller components. This is an unsigned development build, so Windows may identify the publisher as unknown.
- **Linux:** choose `ReLink-Linux-….AppImage`. The preview requires permission to create a virtual controller through `/dev/uinput`; how to configure that permission depends on the distribution. Do not run the app as root to work around input permissions. AppImage and desktop integration can vary between distributions.
- **Existing clients:** use **Connection options → Check for updates** while connected to the Pi. The Windows update uses the app-only package and has been tested. The Linux update button is present but its complete update-and-restart flow still needs a real-world test.
- **Pi source archive, Windows app-only update, manifest and signature:** these are update-system assets, not stand-alone setup packages. The Pi stages signed updates and makes matching client updates available after successful activation.

For example, to start the Linux AppImage from a terminal after downloading it, replace `ReLink-Linux-….AppImage` below with the actual downloaded filename:

```sh
cd ~/Downloads
chmod +x ./ReLink-Linux-….AppImage
./ReLink-Linux-….AppImage --appimage-extract-and-run
```

This runs the preview; it does not install or configure the Pi receiver. The extraction option avoids depending on AppImage FUSE support. Desktop integration and automatic startup are not established for every distribution.

## Pair and assign a controller

1. Open the Pi's authenticated dashboard and create a pairing code under **Computers**. Treat the code as a secret.
2. Open ReLink on the computer and enter the pairing code. Keep the client running while playing.
3. Connect the controller to the receiver using the dashboard's **Setup** view. Give the controller and the computer meaningful names so you can tell them apart later.
4. If more than one controller is connected, use **Computers → Controller assignments** on the Pi dashboard to choose which computer each controller sends input to. This has been tested with two controllers connected to the same Pi and routed to two separate computers.
5. Check the client and a game or controller tester for input. The client may show the receiver as connected while waiting for a controller assigned to that computer.

Restarting or updating the Pi can briefly interrupt controller input, and reconnection is occasionally slower than expected. Battery reporting is controller-driven and may take a few minutes to arrive after connecting.

## Known limitations

- **Microphone (controller to PC) is not available.** A driver-based version works end to end against a real controller's own microphone, but shipping it would currently require enabling Windows test-signing on your own PC, which we don't think is reasonable to ask. A simpler, driver-free fallback exists but has a content bug that isn't fixed yet. Neither is in the current clients.
- **Headset audio (PC to controller) works, but not perfectly.** PC game audio reaching the controller's headset has been confirmed on real hardware on both Windows and Linux. It can still occasionally cut out during a play session, or take noticeably longer than expected to resume after the controller reconnects. Both are known, unresolved issues we're actively working on.
- **Windows builds are not code-signed yet**, so Windows will show the publisher as unknown during setup. This is expected for the current preview.
- **The Linux update button's full update-and-restart flow hasn't been verified end to end** in real use, even though the underlying update mechanism has been tested.
- Interrupted installs, power loss during an update, and using an administrator account different from the signed-in Windows user are all untested recovery scenarios.

## Help improve ReLink

Report problems or suggestions in [GitHub Issues](https://github.com/Black-Sheep-Software/relink-app/issues). Include the client build, operating system, what happened and steps to reproduce. Never post pairing codes, dashboard passwords, controller identifiers or private network details.
