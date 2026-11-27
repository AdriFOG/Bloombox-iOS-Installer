<p align="center"><img src="assets/bloom-floating.svg" width="130" alt="BloomBox mascot"></p>

<h1 align="center">BloomBox iOS Installer</h1>

<p align="center">Your iPhone, your way. · Tu iPhone, a tu manera.</p>

<p align="center"><a href="https://adrifog.github.io/Bloombox-iOS-Installer/"><img src="https://img.shields.io/badge/INSTALL%20BLOOMBOX%20%26%20MEDIABLOOM-NO%20PC-7856D8?style=for-the-badge&logo=apple&logoColor=white" alt="Open the official installer"></a></p>

<p align="center"><a href="#español">Español</a> · <a href="#english">English</a> · <a href="#technical-notes">Technical notes</a></p>

**0.3 — Animated guided installer / Nuevo asistente animado**

[Open the installer / Abrir el instalador](https://adrifog.github.io/Bloombox-iOS-Installer/)

> [!NOTE]
> The web installer remains experimental. BloomBox installation was confirmed on an iPhone with the previous flow; full device testing of the redesigned flow and MediaBloom is pending. This repository does not build a native IPA.
>
> El instalador web sigue siendo experimental. Se confirmó la instalación de BloomBox en un iPhone con el flujo anterior; faltan pruebas completas del nuevo flujo y de MediaBloom. Este repositorio no compila una IPA nativa.

## Español

### Novedades de la versión 0.3

- Portada compacta con Bloom flotando, fondo de símbolos animados y panel negro translúcido.
- Selector de BloomBox y MediaBloom con expresiones felices y tristes, rebote y brillo suave; SVG locales, sin librerías de animación.
- Nueve pantallas individuales, barra de progreso, confirmaciones manuales y avance guardado en el navegador.
- Siete videotutoriales integrados en los pasos correspondientes, con modo de consulta independiente.
- Español e inglés, apariencia clara, oscura y automática, y respeto por la preferencia de movimiento reducido.
- Descarga de versiones estables oficiales, enlace a Open Minis y métodos manuales y alternativos conservados.

### Requisitos

iOS 27+, Wi-Fi, Open Minis 1.16+, LocalDevVPN y modo de desarrollador. No requiere computadora.

### Cómo instalar

Abre el [instalador oficial](https://adrifog.github.io/Bloombox-iOS-Installer/) en Safari, toca **Comenzar instalación**, elige una mascota y pulsa **Instalar versión final**. Revisa la IPA oficial y continúa con el asistente:

1. Prepara la conexión Wi-Fi.
2. Instala y abre Open Minis.
3. Configura LocalDevVPN; déjala desconectada hasta que siboot la solicite.
4. Activa el modo de desarrollador y reinicia si es necesario.
5. Abre el instalador en Open Minis, revisa el comando y pulsa Enter. Si el enlace no abre la terminal, copia el comando y pégalo manualmente.
6. Empareja el iPhone si se solicita, usando el código de tu propia sesión.
7. Inicia sesión con Apple únicamente en el asistente local y espera el resultado de la instalación.
8. Confía en tu cuenta desde Ajustes si iOS lo solicita.
9. Abre la app instalada y confirma que funciona.

El avance es manual: Safari no verifica automáticamente el estado de iOS ni el éxito de la instalación. La web no solicita credenciales, certificados ni archivos de emparejamiento. Revisa el código de siboot y sus servicios de autenticación antes de usar tu cuenta. Las firmas gratuitas normalmente caducan a los siete días. No borres una instalación existente para probar.

## English

### What's new in 0.3

- Compact landing page with floating Bloom, animated background and translucent black panel.
- Expressive BloomBox and MediaBloom selector with gentle bounce, glow and desaturated unselected artwork.
- Nine individual instruction screens, progress bar, manual confirmations and locally saved progress.
- Seven integrated video tutorials and a standalone tutorial browsing mode.
- English and Spanish, light/dark/system appearance and reduced-motion support.
- Official stable release lookup, Open Minis integration and existing manual/fallback methods retained.

### Requirements

iOS 27+, Wi-Fi, Open Minis 1.16+, LocalDevVPN and Developer Mode. No computer required.

### Installation

Open the [official installer](https://adrifog.github.io/Bloombox-iOS-Installer/) in Safari. Select an app, tap **Install stable version**, review the official IPA and continue through the nine guided steps: Wi-Fi, Open Minis, LocalDevVPN, Developer Mode, terminal installation, pairing, Apple sign-in, device trust and first launch.

Keep LocalDevVPN disconnected until requested by siboot. Review the terminal command and press Enter yourself. If the link opens only the Open Minis home screen, use the manual copy method. Enter your Apple Account and verification code only in the local assistant. Progress is manually confirmed, not detected by Safari. Free signatures normally expire after seven days; do not delete a working installation to test.

## 0.3 — Release lookup hotfix / Corrección de búsqueda

The live GitHub release lookup has a 5-second deadline, including the response body. If unavailable, the installer uses an embedded, verified stable snapshot (BloomBox 3.6.0 / MediaBloom 2.4.0, checked 2026-11-26). The UI explicitly identifies backup use; it may be older than the latest release. Refresh the snapshot when publishing new stable versions.

La búsqueda en GitHub tiene un límite de 5 segundos. Si falla, el instalador usa versiones estables verificadas de respaldo (BloomBox 3.6.0 y MediaBloom 2.4.0, consultadas el 26/11/2026). Se indica el uso del respaldo, que puede no ser la versión más reciente.

## Terms and privacy / Términos y privacidad

The installer asks for explicit acceptance of [Terms of Use](TERMS.md) and acknowledgment of the [Privacy Notice](PRIVACY.md) before installation instructions. Version and date are saved locally; a new version requires renewed acceptance. Tutorial browsing remains available without acceptance. No credentials or acceptance records are sent to a project server.

El instalador solicita aceptar los [Términos de uso](TERMS.md) y reconocer el [Aviso de privacidad](PRIVACY.md) antes de las instrucciones de instalación. La versión y fecha se guardan localmente; una nueva versión requiere otra aceptación. Los tutoriales pueden consultarse sin aceptar. No se envían credenciales ni registros de aceptación a un servidor del proyecto.

## Technical notes

- Static HTML/CSS/JavaScript; no backend, analytics or credential form.
- Public latest-release API for the two allowlisted AdriFOG repositories; validates official HTTPS IPA asset URLs and excludes drafts/prereleases.
- Locally bundled mascot SVGs from BloomBox and MediaBloom; seven original tutorial MP4s with lazy loading and no autoplay.
- No upstream source or binaries are redistributed. The command uses pinned siboot revision [117cb3b](https://github.com/FrizzleM/siboot/commit/117cb3b993d07b63b64fd9fd6652ee36f1d85219). The script checks the binary against its supplied SHA-256; an independent upstream security audit remains pending.
- Deploy via GitHub Pages: Settings → Pages → Deploy from a branch → main → / (root). The separate /preview/ path is reserved for design testing and has independent local progress storage.
- Existing signing certificates may conflict. Avoid deleting working apps or revoking existing certificates.
- JavaScript syntax, unique IDs, translation completeness, tutorial paths and simulated navigation checks have passed. These checks do not establish device compatibility.

## Open Minis integration

The documented implementation is in [DeepLinkRouter.swift](https://github.com/OpenMinis/OpenMinis/blob/1a71df0f381cefde80bf912b723de6f9831bc177/src/ios/Shared/DeepLinkRouter.swift) and [ISHTerminalView.swift](https://github.com/OpenMinis/OpenMinis/blob/1a71df0f381cefde80bf912b723de6f9831bc177/src/ios/Views/Rootfs/ISHTerminalView.swift). The link is activated by a user click, pre-fills a command and never submits it automatically. App Store deep-link compatibility still needs device testing; manual copying is supported. No AI account or model is required.

### Alternative IPA download / Descarga alternativa

If the remote IPA download fails (e.g. connection reset 104), download the selected official IPA in Safari. Create a folder named `BloomBoxInstaller` in Files, save a copy as `BloomBox.ipa` or `MediaBloom.ipa`, and mount the folder in Open Minis with that exact name. Follow the local installation instructions in step 5. The local command uses `/var/minis/mounts/BloomBoxInstaller/` and `--ipa`; verify that the file matches the selected release. This fallback still requires device testing. See [siboot download.rs](https://github.com/FrizzleM/siboot/blob/117cb3b993d07b63b64fd9fd6652ee36f1d85219/minis/src/download.rs).

## Device acceptance checklist

- [x] Load a stable release and start siboot on an iPhone using the previous flow.
- [x] Install and launch BloomBox with the previous flow (user-confirmed).
- [x] Validate redesigned wizard navigation in a simulated DOM.
- [ ] Complete an end-to-end installation with the redesigned wizard.
- [ ] Install and launch MediaBloom.
- [ ] Verify renewal, data retention, app groups and custom IPA installation.
- [ ] Validate missing Developer Mode, connection failures and local IPA fallback.
- [ ] Verify App Store terminal prefill deep link compatibility.
- [x] Pin upstream revision.
- [ ] Independently audit upstream.

## Credits

- [siboot by FrizzleM](https://github.com/FrizzleM/siboot) · [Open Minis guide](https://github.com/FrizzleM/siboot/tree/main/minis)
- [SideInstaller by FrizzleM](https://github.com/FrizzleM/SideInstaller) · [License](https://github.com/FrizzleM/SideInstaller/blob/main/LICENSE.md)
- [Official setup guide](https://sideinstaller.net/install.html)

SideInstaller's license limits commercial use and redistribution of official builds. This project links to upstream and does not redistribute its code or binaries. No affiliation with Apple, Open Minis or FrizzleM is implied.
