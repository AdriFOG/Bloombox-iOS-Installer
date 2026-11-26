# BloomBox iOS Installer

Instalador basado en SideInstaller / Experimental no-computer installation assistant for BloomBox and MediaBloom.

**Estado / Status: experimental preview. Not tested on a physical iPhone. No native IPA is built by this repository.**

## Español

1. Activa GitHub Pages en Settings → Pages → Deploy from a branch → main → / (root).
2. Abre la página desde Safari, elige una aplicación, busca la release estable y selecciona su IPA oficial.
3. Instala Open Minis 1.16+ y LocalDevVPN de App Store. Necesitas iOS 27+, Wi-Fi y modo de desarrollador activado.
4. Conecta LocalDevVPN, abre Shell Terminal en Open Minis y pega el comando generado. Sigue el asistente oficial de siboot.
5. Confirma el emparejamiento y la confianza en tu cuenta si iOS lo solicita.

La web no solicita correo, contraseña, códigos, certificados ni archivos de emparejamiento. Siboot realiza la firma y utiliza servicios de Apple y anisette. Revisa el código oficial antes de usar tu cuenta. Las firmas gratuitas normalmente caducan en siete días. No borres una instalación existente para probar.

## English

Enable GitHub Pages from main / (root), open the site in Safari, select an app and its stable IPA, then follow the on-device instructions. Requires iOS 27+, Wi-Fi, Developer Mode, Open Minis 1.16+ and LocalDevVPN. The generated command invokes upstream siboot with the selected release URL. It is not a Safari-only installer. Free signatures normally expire after seven days.

## Technical notes

- Static HTML/CSS/JavaScript; no backend, analytics or credential form.
- Reads GitHub's public latest-release API for the two allowlisted AdriFOG repositories; validates official HTTPS IPA asset URLs.
- No upstream source or binaries are redistributed. The command fetches the official upstream script at runtime, tracking upstream main. The script checks its binary against its supplied SHA-256. Pin and audit upstream before a public stable release.
- Custom IPA installation, entitlements, app groups and renewal with data retention remain untested on hardware. A phone without the Developer Mode switch may need additional setup.
- Existing signing certificates may conflict. Test with a spare Apple account and avoid deleting working apps or revoking existing certificates.

## Device acceptance checklist

- [ ] Load a stable release in Safari.
- [ ] Pair a test iPhone running iOS 27 with itself.
- [ ] Install and launch BloomBox; verify guest installation.
- [ ] Repeat for MediaBloom.
- [ ] Verify renewal, data retention and app groups.
- [ ] Validate missing Developer Mode and connection failures.
- [ ] Pin and audit upstream before recommending broad public use.

## Credits

- [siboot by FrizzleM](https://github.com/FrizzleM/siboot) · [Open Minis guide](https://github.com/FrizzleM/siboot/tree/main/minis)
- [SideInstaller by FrizzleM](https://github.com/FrizzleM/SideInstaller) · [License](https://github.com/FrizzleM/SideInstaller/blob/main/LICENSE.md)
- [Official setup guide](https://sideinstaller.net/install.html)

SideInstaller's license limits commercial use and redistribution of official builds. This preview links to upstream and does not redistribute its code or binaries. No affiliation with Apple, Open Minis or FrizzleM is implied.
