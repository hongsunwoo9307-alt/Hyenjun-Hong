# ScopeGuard

ScopeGuard helps freelance video creators turn English or Korean briefs into clear quotes and review additional work before approving it.

## Get the full source

**All 132 source files are included in [scopeguard-source-v6.zip](scopeguard-source-v6.zip).** Download the ZIP from that link (use GitHub's Download raw file button), then extract it into a new folder. The archive includes the complete release README, source, tests, and MIT license. It contains no API keys or local database.

- Release: v6
- Deployed source commit: `ce62d5650d9919b8f9c7d4a3663d9a4ce53ad5cc`
- ZIP SHA-256: `79a3cf3c2ee24f89abc91cd58e32f678c6b3accd09bea1864f128ec5366c4f87`

## Run locally

Install **Node.js 24 or newer**. Open a terminal in the extracted folder containing `package.json`, then run:

```sh
node --env-file-if-exists=.env.local scripts/judge-server.mjs
```

Open **http://127.0.0.1:3000**. No package installation is needed for this local judge runner.

With no credentials, select the rule-based demo, generate the default **$450** quote, approve it in demo mode, and compare the sample follow-up for **$242.50** in extras. Saved proposals persist in `.local/`. Demo approval creates no payment.

For real AI analysis, configure your own Gemini key using the full README inside the ZIP. Optional PayPal integration uses Sandbox credentials and test accounts only. Keep secrets in server-side environment settings; never publish them. The local runner binds only to loopback and must not be exposed through a tunnel or public proxy.

## Verified status

These results include verification completed after the v6 release. The source ZIP remains the exact deployed commit and has not been changed.

- Real Gemini-backed English and Korean quotes were generated and saved in the hosted app.
- A separate live-Gemini integration check verified a **$450** base quote and **$242.50** scope-change result.
- **34 automated tests passed**, including local HTTP access restrictions and persistence across restarts. Payment responses in automated tests are mocked.
- **The complete hosted flow was verified on 12 November 2026:** Gemini quote → **$450** PayPal Sandbox base capture → Gemini change analysis → separate **$242.50** Sandbox change capture → reload/restoration of both paid states. The extra work was a vertical version ($105), Korean captions ($50), and rush delivery ($87.50). No real money moved.
- Cancellation and simultaneous duplicate-request scenarios have automated-test coverage; they were not live-browser tested.
- Local HTTP tests passed; local browser UI verification is still pending. The hosted development site remains owner-private.

This is a hackathon prototype. Approval records the operator's action; separate client identities and signed contracts are not implemented.

## License

[MIT](LICENSE). Implementation and testing were assisted by Codex.
