# Issues Migration

This is a small script that will migrate bitbucket issues to a github project.
It will use the bitbucket api to pull out the issues and comments.

It will import issues (and close them as needed) and their comments. Labels and
milestones are not supported.

Forked from [vbabiy/bitbucket_issue_migration](https://github.com/vbabiy/bitbucket_issue_migration).
Incorporated code from [jimfulton](https://github.com/jimfulton)'s [PR](https://github.com/vbabiy/bitbucket_issue_migration/pull/22).

## Before running

You will need to install the requirements first

    pip install -r requirements.txt

## Usage

    Usage: migrate.py [options]

    Positional arguments:
      bitbucket_repo        Name of Bitbucket repo to pull data from.
      bitbucket_username    Bitbucket username or organisation name.
      github_username       Your GitHub username
      github_repo           GitHub to add issues to. Format: <username>/<repo_name>

    Options:
      -h, --help            Show this help message and exit
      -t, --dry-run         Preform a dry run and print eveything.
      -f <id>, --start <id> Bitbucket id of the issue to start import (1 means you want all the issues)
      --bitbucket-auth <username:password>
                            Add this option when importing from private Bitbucket repo.

    python migrate.py <bitbucket_repo> <bitbucket_username> <githbu_username> <github_user>/<github_repo> -f 1

Note: if you need to migrate to a GitHub organizational repository, use your
personal username, but the appropriate API token for the repository.

### Important stuff

This script is licensed under [GPL](./LICENSE.txt) and it belongs to [vbabiy](https://github.com/vbabiy/).
I have no intention of contributing to the original, so any questions head over
to [vbabiy/bitbucket_issue_migration](https://github.com/vbabiy/bitbucket_issue_migration).
