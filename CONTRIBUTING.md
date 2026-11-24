# Contributing to ivLyrics

> **한국어 요약**
> 큰 기능이나 구조 변경은 PR 전에 이슈나 [Discord](https://discord.gg/2fu36fUzdE)에서 먼저 이야기해 주세요. PR에는 실행한 확인 절차와 화면 변화(전후 캡처)를 적어 주세요. 새 문구는 지원하는 모든 언어에 추가하고, 설정 키는 저장된 값을 옮기는 마이그레이션 없이 바꾸거나 지우지 마세요. AI로 만든 코드도 직접 검토하고 설명할 수 있어야 합니다. 기여한 코드는 각 저장소 LICENSE 6조에 따라 라이선스됩니다. 보안 문제는 공개 이슈 대신 [보안 정책](SECURITY.md)을 따라 주세요.

Thanks for helping improve ivLyrics. This guide applies to every ivLis Studio repository that does not have its own `CONTRIBUTING.md`. ivLyrics for PC has a [detailed guide](https://github.com/ivLis-Studio/ivLyrics/blob/main/CONTRIBUTING.md).

## Before you start

- **Bugs:** report them with the [bug report form](https://github.com/ivLis-Studio/ivLyrics/issues/new/choose) in the ivLyrics repository, and select the platform. Android, LSPatch, and iOS bugs are tracked there too.
- **Questions and help:** ask on [Discord](https://discord.gg/2fu36fUzdE).
- **Features and larger changes:** open a feature request or start a Discord thread before writing code.
- **Small fixes:** typos, clear bugs, and focused fixes can go straight to a pull request.
- **Security problems:** do not open an issue. Follow the [security policy](SECURITY.md).

## License of contributions

ivLyrics projects are source-available under the ivLyrics Source-Available License 1.0, described in each repository's `LICENSE`. They are not open source: you may fork and modify them to develop and contribute changes, but not redistribute them. By submitting a contribution, you confirm that you have the right to submit it and grant ivLis Studio the license in Section 6 of `LICENSE`. You keep the copyright in your work. Files that a repository's `NOTICE.md` lists under other licenses keep those licenses.

## Repository checks

Run the checks for the repository you change. CI runs them too where available.

| Repository | Checks |
|---|---|
| [ivLyrics](https://github.com/ivLis-Studio/ivLyrics) (PC) | `node --test tests/*.test.mjs`. See its [guide](https://github.com/ivLis-Studio/ivLyrics/blob/main/CONTRIBUTING.md). |
| [ivLyrics-Android](https://github.com/ivLis-Studio/ivLyrics-Android) | `./gradlew :shared:testDebugUnitTest`, then the `tests/run_*_regression.py` scripts listed in `.github/workflows/android-ci.yml`. |
| [ivLyrics-IOS](https://github.com/ivLis-Studio/ivLyrics-IOS) | Build in Xcode. For simulator builds, set `IVLYRICS_LLAMA_STUB=1`. Run the `scripts/test-*` checks that cover the area you changed. |
| [ivLyrics-overlay](https://github.com/ivLis-Studio/ivLyrics-overlay) | `npm ci`, `npm test`, and `npm run build`. |
| [ivLyrics-helper](https://github.com/ivLis-Studio/ivLyrics-helper) | `cargo check --manifest-path src-tauri/Cargo.toml`, with the [Tauri prerequisites](https://tauri.app/start/prerequisites/) installed. |

The motion lyrics page in the Android and iOS apps (`MotionLyricsPage.html`) is generated from ivLyrics for PC. Change the PC sources instead of editing the generated file.

## Rules for changes

- **Do not break saved settings.** Never rename or remove a settings key, or change what a stored value means, without migrating values that users already saved.
- **Translate every string.** Add new interface text in every supported language.
- **Keep behavior and performance stable.** The lyrics views update every frame. A performance change must not change what users see.
- **Keep endpoints and keys private.** Some provider addresses are deliberately obfuscated. Do not de-obfuscate them in code, comments, or pull request descriptions, and never commit API keys, tokens, or signing files.
- **Leave releases to maintainers.** Do not change version numbers or release workflows in a feature pull request.

## AI-assisted contributions

You may use AI tools. You are still the author: read every line, test it, and be able to explain it. Keep the diff focused on one problem. Pull requests that rename settings, rewrite unrelated code, or ship untested generated code will be closed.

## Commits and pull requests

- Write commit messages in English using [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `perf:`, `refactor:`, `docs:`, `test:`, `chore:`.
- Keep one topic per pull request, fill in the pull request template, and attach before and after screenshots for visible changes.
- Enable **Allow edits by maintainers**. Maintainers may push fixes to your branch before merging.

## Code of conduct

Everyone taking part in ivLyrics spaces follows the [code of conduct](CODE_OF_CONDUCT.md).
