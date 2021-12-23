# GitHub Actions Auto Commit

This is a script for GitHub actions which, when enabled, automatically makes a commit to the repository every day at around 12PM UTC. It was active from 27 November to 20 December 2021. By then, I decided to disable the script because three and a half weeks is more than enough time to demonstrate how daily automation works. I have made this public so that it can be used as a reference.

---

## Running

The script itself is still there but it now runs on a manual trigger instead of a schedule. To re-activate the daily automation, open the [script file](./.github/workflows/commit-job.yaml) and edit it as follows:


**Before:**
```yaml
on: workflow_dispatch
```

\
**After:**
```yaml
on:
  schedule:
    # Each day at 12:00 UTC
    - cron:  '0 12 * * *'
```

\
The schedule code has been backed up to a [separate text file](./.github/workflows/cron.txt) for convenience.

You must supply your own [GitHub access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) in order to use this script. It is attatched to the repository as an [encrypted secret](https://docs.github.com/en/actions/security-guides/encrypted-secrets) under the name `REPO_ACCESS_TOKEN`


---

## Disclaimer

The contents of this repository are licensed under [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/). You can do whatever you want with it.

