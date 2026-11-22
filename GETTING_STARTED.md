# ReLink development preview

The current preview connects Stadia Controllers using their original Wi-Fi firmware to a ReLink receiver on a Raspberry Pi, which sends controller input to paired Windows or Linux computers. This is early test software, not a finished consumer installation. A complete, supported Pi setup package and guide are still being developed; the client downloads alone do not create a receiver.

## What you need

- A Stadia Controller running its original Wi-Fi firmware and a compatible, already configured ReLink Pi receiver with its controller network running.
- A Windows or Linux computer that can reach the receiver's management dashboard on the local network. Multiple controllers and separate computer assignments have been tested, but setup and identification are still being refined.
- A current development preview from the [releases page](https://github.com/Black-Sheep-Software/relink-app/releases/latest). Check the release notes for the exact build and known limitations.

The Bluetooth firmware is a different controller mode; the Wi-Fi receiver requires the original Wi-Fi firmware. Do not assume firmware conversion or recovery is reversible. Keep the Pi dashboard on a trusted local network and protect its sign-in and pairing codes.

## Choose a download

- **Windows first installation:** choose the file named `ReLink-Setup-…exe`. Setup asks for administrator approval and installs the app and any needed virtual-controller components. This is an unsigned development build, so Windows may identify the publisher as unknown.
- **Linux:** choose `ReLink-Linux-….AppImage`. The preview requires permission to create a virtual controller through `/dev/uinput`; how to configure that permission depends on the distribution. Do not run the app as root to work around input permissions. AppImage and desktop integration can vary between distributions.
- **Existing clients:** use **Connection options → Check for updates** while connected to the Pi. The Windows update uses the app-only package and has been tested. The Linux update button is present but its complete update-and-restart flow still needs a real-world test.
- **Pi source archive, Windows app-only update, manifest and signature:** these are update-system assets, not stand-alone setup packages. The Pi stages signed updates and makes matching client updates available after successful activation.

## Pair and assign a controller

1. Open the Pi's authenticated dashboard and create a pairing code under **Computers**. Treat the code as a secret.
2. Open ReLink on the computer and enter the pairing code. Keep the client running while playing.
3. Connect the controller to the receiver. If controller assignments are enabled, use **Computers → Controller assignments** on the Pi dashboard to assign it to the intended computer. Give computers and controllers meaningful names so you can tell them apart.
4. Check the client and a game or controller tester for input. The client may show the receiver as connected while waiting for a controller assigned to that computer.

The Pi receiver and clients are still being refined. Restarting or updating the Pi can briefly interrupt controller input. Battery reporting may take time to arrive. Headset audio and microphone support are in development and should not be assumed to work in this preview.

## Help improve ReLink

Report problems or suggestions in [GitHub Issues](https://github.com/Black-Sheep-Software/relink-app/issues). Include the client build, operating system, what happened and steps to reproduce. Never post pairing codes, dashboard passwords, controller identifiers or private network details.
