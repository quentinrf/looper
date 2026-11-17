# Triage Labels

The skills speak in terms of five canonical triage roles. This file maps those roles to the actual label strings used in this repo's issue tracker.

| Label in mattpocock/skills | Label in our tracker | Meaning                                  |
| -------------------------- | -------------------- | ---------------------------------------- |
| `needs-triage`             | `needs-triage`       | Maintainer needs to evaluate this issue  |
| `needs-info`               | `needs-info`         | Waiting on reporter for more information |
| `ready-for-agent`          | `ready-for-agent`    | Fully specified, ready for an AFK agent  |
| `ready-for-human`          | `ready-for-human`    | Requires human implementation            |
| `wontfix`                  | `wontfix`            | Will not be actioned                     |

When a skill mentions a role (e.g. "apply the AFK-ready triage label"), use the corresponding label string from this table.

Edit the "Label in our tracker" column to match whatever vocabulary you actually use.

## Creating the labels

Run from inside a clone. `--force` updates labels that already exist (new GitHub repos ship with `wontfix`), so this is safe to re-run:

```sh
gh label create needs-triage --force --color fbca04 --description "Maintainer needs to evaluate this issue"
gh label create needs-info --force --color d4c5f9 --description "Waiting on reporter for more information"
gh label create ready-for-agent --force --color 0e8a16 --description "Fully specified, ready for an AFK agent"
gh label create ready-for-human --force --color 1d76db --description "Requires human implementation"
gh label create wontfix --force --color ffffff --description "Will not be actioned"
```
