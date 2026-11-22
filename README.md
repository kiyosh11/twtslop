# twtslop

A community-maintained X account filter list used by **Slop Shield**. The list starts with six accounts selected by the maintainer; it is not an automated account classifier.

**[View the list](accounts.json)** · **[How to add an account](ADDING_ACCOUNTS.md)** · **[Raw JSON](https://raw.githubusercontent.com/kiyosh11/twtslop/main/accounts.json)**

## Use the list

Paste this URL into Slop Shield’s **Sources & sync** settings:

```text
https://raw.githubusercontent.com/kiyosh11/twtslop/main/accounts.json
```

Slop Shield already uses this source by default. GitHub updates refresh the local list; they never automatically block accounts on X. You choose whether to collapse or hide matching posts and confirm any account blocks yourself.

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
