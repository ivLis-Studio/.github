# Security policy

> **한국어 요약**
> 보안 취약점은 공개 이슈, Discord, PR에 올리지 말고 비공개로 알려 주세요. 해당 저장소의 **Security → Report a vulnerability** 또는 me@ivl.is(제목에 `[security]`)로 보내면 됩니다. 7일 안에 확인 답장을 드립니다. 다른 사용자의 데이터에 접근하거나 서버에 대량 요청을 보내는 테스트는 하지 마세요.

## Supported versions

Security fixes go into the latest release of each app: ivLyrics for PC, the Android app and LSPatch module, the iOS app, ivLyrics Overlay, and ivLyrics Helper. ivLyrics servers and websites under `ivl.is` are always in scope. Please update to the latest release before reporting.

## Reporting a vulnerability

Report privately. Do not open a public issue, pull request, or Discord post about it.

- **GitHub:** open the affected repository's **Security** tab and choose **Report a vulnerability**. For server problems, or if you are unsure where it belongs, use [ivLyrics](https://github.com/ivLis-Studio/ivLyrics/security/advisories/new).
- **Email:** send it to me@ivl.is with `[security]` in the subject.

Include the affected app, version, or address; the steps or proof of concept; the impact you expect; and how to contact you.

## What to expect

- An acknowledgment within 7 days.
- Updates while we investigate and fix the problem. How fast a fix ships depends on severity.
- Credit in the release notes once the fix is out, if you want it.

## Scope

In scope:

- The ivLyrics apps, including how they store and send API keys and tokens.
- The local interfaces of ivLyrics Helper and ivLyrics Overlay.
- ivLyrics servers and websites, including accounts, sync data submission, and community data.

Out of scope:

- Problems in third-party services such as Spotify, YouTube, LRCLIB, lrc.red, and AI providers. Report those to the service.
- Attacks that need a rooted or jailbroken device, or physical access to an unlocked device.
- Denial of service, rate-limit, or spam testing.
- Automated scanner output without a demonstrated impact.

## Rules for research

- Test only with your own accounts and data. Do not access, change, or delete other users' data.
- Do not run high-volume or automated scans against ivLyrics servers.
- Stop once you confirm a problem, and report it.
- Give us reasonable time to fix it before any disclosure; 90 days is the default.

ivLis Studio will not pursue legal action for good-faith research that follows this policy.
