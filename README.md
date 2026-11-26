# BloomBox iOS Installer

Instalador basado en SideInstaller / Experimental no-computer installation assistant for BloomBox and MediaBloom.

**Estado / Status: 0.2 experimental preview. siboot startup confirmed on an iPhone; complete installation remains unverified. No native IPA is built by this repository.**

## Español

1. Activa GitHub Pages en Settings → Pages → Deploy from a branch → main → / (root).
2. Abre la página desde Safari, elige una aplicación, busca la release estable y selecciona su IPA oficial.
3. Instala Open Minis 1.16+ y LocalDevVPN de App Store. Necesitas iOS 27+, Wi-Fi y modo de desarrollador activado.
4. Deja LocalDevVPN desconectada hasta que siboot la solicite y pulsa **Abrir instalador en Open Minis**. Si la versión de Open Minis admite el enlace, abre la terminal y rellena el comando sin ejecutarlo. Si solo aparece Inicio, regresa a Safari y vuelve a pulsar el enlace. Revísalo y pulsa Enter; luego sigue el asistente gráfico de siboot. Si no funciona el enlace, usa el método manual. Si falta Modo de desarrollador, utiliza el botón de preparación.
5. Confirma el emparejamiento y la confianza en tu cuenta si iOS lo solicita.

La web no solicita correo, contraseña, códigos, certificados ni archivos de emparejamiento. Siboot realiza la firma y utiliza servicios de Apple y anisette. Revisa el código oficial antes de usar tu cuenta. Las firmas gratuitas normalmente caducan en siete días. No borres una instalación existente para probar.

## English

Enable GitHub Pages from main / (root), open the site in Safari, select an app and its stable IPA, then follow the on-device instructions. Requires iOS 27+, Wi-Fi, Developer Mode, Open Minis 1.16+ and LocalDevVPN. The Open Minis deep link is designed to pre-fill the terminal command for the selected release; review it and press Enter. A manual copy fallback is available. The graphical siboot assistant then opens within Open Minis. It is not a Safari-only installer. Free signatures normally expire after seven days.

## Technical notes

- Static HTML/CSS/JavaScript; no backend, analytics or credential form.
- Reads GitHub's public latest-release API for the two allowlisted AdriFOG repositories; validates official HTTPS IPA asset URLs.
- No upstream source or binaries are redistributed. The command downloads the script and binary from pinned upstream revision [117cb3b](https://github.com/FrizzleM/siboot/commit/117cb3b993d07b63b64fd9fd6652ee36f1d85219). The script checks the binary against its supplied SHA-256. An independent upstream security audit remains pending.
- Custom IPA installation, entitlements, app groups and renewal with data retention remain untested on hardware. A phone without the Developer Mode switch may need additional setup.
- Existing signing certificates may conflict. Test with a spare Apple account and avoid deleting working apps or revoking existing certificates.

## Device acceptance checklist

- [x] Load a stable release in Safari and start siboot on an iPhone.
- [ ] Complete a download on Wi-Fi (previous cellular attempt returned connection reset 104).
- [ ] Pair a test iPhone running iOS 27 with itself.
- [ ] Install and launch BloomBox; verify guest installation.
- [ ] Repeat for MediaBloom.
- [ ] Verify renewal, data retention and app groups.
- [ ] Validate missing Developer Mode and connection failures.
- [ ] Verify that the App Store version accepts the terminal prefill deep link on iOS.
- [x] Pin upstream revision.
- [ ] Independently audit upstream before recommending broad public use.

## Credits

- [siboot by FrizzleM](https://github.com/FrizzleM/siboot) · [Open Minis guide](https://github.com/FrizzleM/siboot/tree/main/minis)
- [SideInstaller by FrizzleM](https://github.com/FrizzleM/SideInstaller) · [License](https://github.com/FrizzleM/SideInstaller/blob/main/LICENSE.md)
- [Official setup guide](https://sideinstaller.net/install.html)

SideInstaller's license limits commercial use and redistribution of official builds. This preview links to upstream and does not redistribute its code or binaries. No affiliation with Apple, Open Minis or FrizzleM is implied.

## Open Minis integration

The documented implementation is in [DeepLinkRouter.swift](https://github.com/OpenMinis/OpenMinis/blob/1a71df0f381cefde80bf912b723de6f9831bc177/src/ios/Shared/DeepLinkRouter.swift) and [ISHTerminalView.swift](https://github.com/OpenMinis/OpenMinis/blob/1a71df0f381cefde80bf912b723de6f9831bc177/src/ios/Views/Rootfs/ISHTerminalView.swift). The link is activated only by a user click, passes a fixed command with validated official IPA URL and no newline, and does not submit the command automatically. App Store build compatibility must be tested on-device. No AI account or model is needed for the terminal flow.

## 0.2 — Guided setup / Instalación guiada

- Three screens, app selection and setup checklist persisted locally (manual confirmations, not device detection).
- Official project artwork, Spanish/English, light/dark mode.
- A harmless terminal link test (`echo BloomBox-Link-OK`) and visible retry guidance; no automatic execution.
- Safari IPA download fallback: create a folder named `BloomBoxInstaller` in Files, save the official IPA there as `BloomBox.ipa` or `MediaBloom.ipa` according to the selected app, mount that folder in Open Minis under the exact name `BloomBoxInstaller`, then open the local installer link. The local command uses the documented `/var/minis/mounts/BloomBoxInstaller/` path and `--ipa` option. Manual copy is available. The browser cannot verify the mounted file, so users must check the selected app and version. This flow is not yet verified on a device.
- Source for local IPA support: [siboot download.rs at pinned revision](https://github.com/FrizzleM/siboot/blob/117cb3b993d07b63b64fd9fd6652ee36f1d85219/minis/src/download.rs).
- JavaScript syntax, unique IDs, translation completeness, link encoding and simulated wizard state checks passed. Hardware validation and security audit remain pending.
