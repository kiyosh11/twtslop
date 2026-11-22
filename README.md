# twtslop

A community-maintained X account filter list used by **Slop Shield**. The list starts with six accounts selected by the maintainer; it is not an automated account classifier.

**[View the list](accounts.json)** · **[How to add an account](ADDING_ACCOUNTS.md)** · **[For AI tools](llms.txt)** · **[Raw JSON](https://raw.githubusercontent.com/kiyosh11/twtslop/main/accounts.json)**

## Use the list

Paste this URL into Slop Shield’s **Sources & sync** settings:

```text
https://raw.githubusercontent.com/kiyosh11/twtslop/main/accounts.json
```

Slop Shield already uses this source by default. Choose whether to collapse or hide matching posts, review blocks manually, or start an **Auto-block list** / **Auto-block selected** queue. Automatic queues confirm blocks on X and have pause, resume, and stop controls. Keep the queue’s X tab open and signed in.

**Auto-block after list updates** is a separate opt-in under **Sources & sync**, off by default. It applies eligible list accounts after updates, skips your allowlist, and remembers verified blocks per X account. Queues pause on errors or account changes. Stop disables this automatic option. Removing a list entry or adding an exception does not undo a block already applied on X.

## Countries, activity, and recorded blocks

**Countries & activity** lets you choose countries, see detected locations and hidden/collapsed post counts, and choose a block prompt, automatic blocking, or profile links for manual blocking. It reads X’s **About this account → Account based in**, opened from a profile’s **Joined** date. Unknown, region-only, stale (over seven days), and possibly inaccurate observations are not country matches. Bio locations, flags, language, and App Store countries are not used. Optional background checks are off by default and use public X profile controls. English labels are supported.

**Block history** provides search, filtering by your X account, and JSON export for blocks verified by the extension. It is a local record, not an import of every server-side X block; a block may have changed since verification.

Select recorded accounts and choose **Prepare PR from selected** to add reasons and public examples. The helper merges proposed entries into the latest GitHub JSON, then offers copy buttons and GitHub’s editor. Create a new branch (or fork) and submit the final PR on GitHub. No GitHub token is stored in the extension. Personal country rules are not uploaded to the shared list.

## Add or correct an account

Read the [account-addition policy](ADDING_ACCOUNTS.md), edit `accounts.json`, and open a pull request with a short explanation and public examples. Maintainers review additions. To request a correction or removal, open an issue or pull request identifying the handle and the change.

```json
{
  "handle": "example_handle",
  "category": "ai-slop",
  "reason": "A concise description of the repeated behavior"
}
```

Categories: `ai-slop`, `engagement-bait`, `spam`, and `other`. Being listed is a filtering preference, not a claim that an account is illegal or unsafe.
