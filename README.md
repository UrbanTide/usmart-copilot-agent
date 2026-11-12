# uSmart agent for Microsoft 365 Copilot

Search, describe and query the uSmart datasets you have access to, in plain language, inside Microsoft 365
Copilot Chat. You sign in with your own uSmart account and see exactly what you could see on usmart.ai.
The agent is read-only.

**Download:** `usmart-copilot-agent-v<version>.zip` from [`releases/`](releases/), or the file of the same name attached
to the GitHub Release. Do **not** use the "Source code (zip)" that GitHub adds to every release: that is a copy of this
repository, not the agent package, and the admin centre will reject it.
Current version: **1.0.3**. See [CHANGELOG.md](CHANGELOG.md).

Published by uSmart (UrbanTide). Source and build tooling are internal; this repository carries the
installable package and the guide below.

---


The uSmart agent lets people in your organisation search, describe and query the uSmart datasets they
already have access to, in plain language, inside Microsoft 365 Copilot Chat. Each person signs in with
their own uSmart account and sees only what they could see on usmart.ai. The agent is read-only: it
cannot add, change or delete anything in uSmart.

## What you need

- A Microsoft 365 tenant with Copilot Chat. A Microsoft 365 Copilot licence is **not** required.
- An administrator with the Global Administrator, AI Administrator or Teams Administrator role.
- uSmart accounts for the people who will use it.
- The package: `usmart-copilot-agent-v<version>.zip` from the latest release.

## Install (administrator, about five minutes)

1. Sign in to the Microsoft 365 admin centre: https://admin.microsoft.com
2. Go to **Agents** > **All agents**, then **Add agent** and upload the zip.
3. Open the new **uSmart** row, **Users** tab. Set **Available to** (everyone, or specific groups) and,
   if you want it pre-installed, **Installed for**. Save.
4. Wait. Microsoft takes **a few hours** to make an uploaded agent's tools available. If someone tests it
   immediately and the agent says it has no tools, that is the delay, not a fault.

Alternative route: Teams admin centre > **Teams apps** > **Manage apps** > **Actions** > **Upload new app**,
then set availability on the app's **Users and groups** tab. Custom apps must be allowed in
**Org-wide app settings**.

Nothing else is configured on your side. There are no client IDs, secrets or URLs to enter.

## Use (everyone)

1. Open https://m365.cloud.microsoft/chat (or Copilot in Teams).
2. Pick **uSmart** from the Agents list. If it isn't listed, open **All agents** and look under
   **Built by your org**.
3. Ask, for example, "Which uSmart datasets can I see?"
4. The first time, a sign-in card appears. Sign in with your uSmart account. You won't be asked again
   until the session expires.

Good prompts: "Find datasets about air quality", "What columns does the planning applications dataset
have?", "Show me the five most recent records in the car park occupancy dataset."

## Updating

When uSmart publishes a new version, upload the new zip from the agent's details page (**Update in store**
in the Microsoft 365 admin centre, or **Upload file** in the Teams admin centre). Availability settings carry
over.

## If something doesn't work

| Symptom | Cause and fix |
| --- | --- |
| Agent replies but says it has no tools, or never asks you to sign in | The upload is still propagating. Try again in a few hours. |
| "This agent is blocked by your organisation's policy" | Microsoft 365 admin centre > Agents > Settings > Agent and plugin access: allow agents built by your organisation. |
| Sign-in card appears but sign-in fails | The person has no uSmart account, or signed in with the wrong one. |
| Agent can't see a dataset you expect | The signed-in uSmart user doesn't have access to it on usmart.ai. The agent never sees more than the user does. |
| Upload rejected: version not higher | You already have this or a newer version installed. |

## Privacy and support

- Data flows only between Microsoft 365 Copilot and uSmart's API, over HTTPS, on behalf of the signed-in user.
- Privacy policy: https://usmart.ai/privacy. Terms: https://usmart.ai/terms.
- Support: hello@usmart.ai
