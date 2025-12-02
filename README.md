# CCL — CyclomotorCycloramicLegacy

**CCL** stands for **CyclomotorCycloramicLegacy**. This repository collects legacy Cycloramic and Cyclomotor assets plus a modern 64‑bit rebuild and example code to run automated, compass‑driven multi‑shot capture sequences on iOS devices. Full instructions are in this README.

---

## What this repo contains
- **Original Cycloramic 32‑bit files** included for historical/reference purposes.  
- **64‑bit rebuild** targeted to run on **iPhone 5s** (provided in the repo).  
- **Example `ViewController.swift`** demonstrating: numeric step capture, degrees‑per‑step, compass triggers with timed fallback, flash/torch sync, optional triple end flash signal, and horizontal merge of captured images in reverse order (last → first)(not functioning).  
- **README** with build, signing, and usage instructions.

---

## Key features
- **Configurable steps** and **degrees per step** (negative).  
- **Compass‑based capture** with adjustable heading tolerance and haptic feedback.  
- **Timed fallback burst** when heading is unavailable.  
- **Flash handling**: uses camera flash when available; simulates flash with torch when needed.  
- **Merge images horizontally** in reverse capture order or save images individually.  
- **Optional triple torch flash** at the end of the sequence to signal completion (toggleable in settings).  
- **Saves to Photos** using `UIImageWriteToSavedPhotosAlbum`.

---

## Compatibility and important notes
- The **64‑bit build is provided and tested on iPhone 5s**.  
- The **original 32‑bit Cycloramic files** are included for reference.  
- **I have not tested the 64‑bit build on iPhone 6 or 6s**; behavior on those devices is unverified.  
- Compass, torch, and flash features require a **physical device**; the Simulator will not reproduce those behaviors.  
- Ensure `Info.plist` contains **NSCameraUsageDescription** and **NSLocationWhenInUseUsageDescription** before running.

---

## Signing and installation
**You must sign the Xcode project or IPA before installing on a device.** iOS requires code signing with a valid provisioning profile and certificate to run apps on physical devices.

**Steps to sign and install**
1. Open the Xcode project in this repository.  
2. Set a unique **Bundle Identifier** (for example `com.yourname.CCL`).  
3. In the project **Signing & Capabilities** pane select your **Team**.  
4. Let Xcode manage signing automatically or attach a provisioning profile tied to your Apple developer account.  
5. Confirm `NSCameraUsageDescription` and `NSLocationWhenInUseUsageDescription` are present in `Info.plist`.  
6. Select a physical device (iPhone 5s or newer) and build/run. Grant camera and location permissions when prompted.

**Sideloadly signing**
- If you prefer sideloading, you can sign and install the app using **Sideloadly**. Use your Apple ID or a valid provisioning profile to sign the IPA, then install it to your device with Sideloadly. The repository does not include pre‑signed binaries; you must sign the app yourself before installation.

---

## Settings and usage
- Open the app and use the **Settings** button to configure:  
  - **Number of steps**  
  - **Degrees per step**  
  - **Heading tolerance**  
  - **Start delay**  
  - **Image processing mode** (`merge` or `single`)  
  - **End flash signal** (`on` / `off`)  
- Press the shutter to start. The app takes an initial photo, then captures at each rotation target. If merge mode is selected, the final saved image is the horizontal merge of captured frames in reverse order (last → first)(not functioning).

---

## Troubleshooting
- **Missed captures**: increase heading tolerance.  
- **Merge memory issues**: switch to save individually mode.  
- **Torch/flash inconsistent**: test on another device or disable torch simulation.  
- **Permissions**: check camera and location permissions in iOS Settings.

---

## Liability and risk
**Use at your own risk**  
By using the code and binaries in this repository you accept full responsibility for any outcomes. **I am not liable for any damages, losses, or other consequences** that may result from using, installing, modifying, or running this software. This includes, but is not limited to, device damage, data loss, or other direct or indirect harm. Use the software only if you understand and accept these risks.

**No warranty**  
The software is provided “as is,” without warranty of any kind, express or implied. No assurances are made about fitness for a particular purpose, reliability, or suitability. You are responsible for testing and verifying the code before use in any production or critical environment.

---

## Contact and Xcode project requests
If you want the full Xcode project file or a packaged build, **email me** and I will provide the file on request. You are responsible for signing the project or IPA before installing it on any device.

---

## License and contributions
- Add your preferred license (for example **MIT**) to the repository.  
- Contributions and pull requests are welcome. Please open issues for bugs or feature requests.

---

## Short repo description and topics
**Description**: CCL — CyclomotorCycloramicLegacy: legacy Cycloramic and Cyclomotor utilities with a 64‑bit build for iPhone 5s; instructions in README.  
**Topics**: `ios`, `camera`, `cycloramic`, `cyclomotor`, `compass`, `photo-merge`, `legacy`

---
