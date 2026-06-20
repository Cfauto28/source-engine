# Source Engine
[![GitHub Actions Status](https://github.com/Cfauto28/source-engine/actions/workflows/build.yml/badge.svg)](https://github.com/Cfauto28/source-engine/actions/workflows/build.yml) [![GitHub Actions Status](https://github.com/Cfauto28/source-engine/actions/workflows/tests.yml/badge.svg)](https://github.com/Cfauto28/source-engine/actions/workflows/tests.yml)
 
Source code is based on TF2 2018 leak. Don't use it for commercial purposes.

This project is using waf buildsystem. If you have waf-related questions look https://waf.io/book

# Features:
- [x] Android, macOS, FreeBSD, Windows, Linux (glibc, musl) support
- [x] Arm support (except windows)
- [x] 64bit support
- [x] Modern toolchains support
- [x] Fixed many undefined behaviours
- [x] Touch support (even on windows/linux/macos)
- [x] VTF 7.5 support
- [x] PBR support
- [x] bsp v19-v21 support (bsp v21 support is partial, portal 2 and csgo maps work fine)
- [x] mdl v46-49 support
- [x] Removed useless/unnecessary dependencies
- [x] Achivement system working without steam
- [x] Fixed many bugs
- [x] Serverbrowser works without steam
- [x] VScript support (based on the Mapbase implementation)
- [x] Utils port (Most important command-line utils have been ported)

# To Do (In order)
- [ ] Port the thing to cmake (check [here](https://github.com/valberrie/icepick)) 
- [ ] DirectX 10 (For some reason it seem to be stripped from the source code, check [Kisak-Strike](https://github.com/SwagSoftware/Kisak-Strike)) and [dxvk-native](https://github.com/doitsujin/dxvk) support
- [ ] Elbrus port (There is a [pull request](https://github.com/nillerusr/source-engine/pull/305) in upstream)
- [ ] Bink audio support (for video_bink, check [here](https://github.com/cherrybtw/source-engine))
