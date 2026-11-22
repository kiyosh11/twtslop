# Account-addition policy

This list helps people filter repetitive, low-value content on X. Inclusion should describe an account’s public posting behavior. A generated image, a single weak post, or a disagreement alone is not enough to establish a pattern.

## What belongs in the list

- **`ai-slop`**: repeated, low-effort generated posts or replies, such as unrelated generated replies or misleading mass-produced content. Explain the observed pattern; do not claim AI use as a fact based only on a detector or a hunch.
- **`engagement-bait`**: repeated formulaic outrage, recycled prompts, or reply/like farming with little substance.
- **`spam`**: repeated unsolicited promotions, duplicate replies, or irrelevant link flooding.
- **`other`**: a specific filtering reason that does not fit the categories above. Explain it clearly so maintainers can assess it.

Keep reasons factual and specific. Do not submit accounts solely for their identity, protected characteristics, or a personal dispute. Do not include private information, threats, or instructions to harass or mass-report anyone.

## How to add an account

1. Search `accounts.json` for the handle first. X handles are case-insensitive; do not add duplicates.
2. Review the account’s recent public posts. Include two or more representative public post links in your pull request and explain the repeated behavior. If only one example is available, explain that limitation.
3. Edit the `accounts` array in `accounts.json`, adding an object like this:

   ```json
   {
     "handle": "example_handle",
     "category": "engagement-bait",
     "reason": "Repeated copy-paste engagement prompts across unrelated topics"
   }
   ```

4. Keep the JSON valid: put commas between entries, use double quotes, and do not add comments or trailing commas. Keep `version` set to `1`.
5. Open a pull request. Include the handle, category, concise reason, and public examples. Maintainers decide whether the entry fits the list; opening a PR does not add an account automatically.

If you cannot edit JSON, open an issue with the same information. For multiple accounts, provide a separate reason and examples for each. Avoid unexplained bulk submissions.

Slop Shield also offers **Block history → Prepare PR from selected**. This prepares updated JSON and a PR description from the latest list after you supply reasons and public examples. Copy them into GitHub's editor, choose a new branch or fork, and submit a pull request there. Preparation does not publish or merge anything. Country filters are personal preferences; country alone is not evidence of the posting behavior described by this list.

## Entry format

| Field | Requirement |
| --- | --- |
| `handle` | Required. The current X username, 1–15 letters, numbers, or underscores. Prefer lowercase without `@`; an optional `@` prefix is accepted. Do not use a profile URL or display name. |
| `category` | One of `ai-slop`, `engagement-bait`, `spam`, or `other`. |
| `reason` | A short, factual explanation, at most 300 characters. Expected for new submissions. Put supporting post links in the PR description. |
| `name` | Optional display name, at most 80 characters. The handle remains the lookup key. |

The extension accepts plain handle strings too, but account objects are preferred for shared-list contributions. The original six starter entries were selected by the maintainer and do not include independently supplied reasons; do not invent reasons for them.

## Review, corrections, and removals

Maintainers check that the handle is correct, the behavior is relevant and supported by the examples, the entry is not duplicated, and the JSON is valid. An invalid entry can prevent an entire list update from syncing.

To challenge an entry, open an issue or PR with the handle, the requested correction or removal, and a short explanation. Corrections may be appropriate when a handle changes, an account is misidentified, the examples do not support inclusion, or the behavior has changed. Be respectful; the maintainer can remove or recategorize entries.

Handles can change or be reused. This format matches usernames, not immutable X account IDs, so entries should be reviewed periodically. Removing an entry stops future list-based filtering after sync; it does not undo a block someone already confirmed in X.

## What happens after a merge

Slop Shield fetches the JSON on its configured schedule, or immediately when a user selects **Sync now**. A successful update applies additions and removals. Failed validation leaves the last valid cached list active. A user’s personal allowlist always takes precedence.

Automatic blocking is off by default. Users can explicitly start an automatic queue or opt into **Auto-block after list updates**. For users who enable that option, additions can result in automatic blocks through their signed-in X session. Queues skip exceptions and disabled categories, pause on errors or account changes, and have stop/resume controls. This makes accurate handles and supported reasons particularly important. Removing an entry never reverses a block already applied on X.
