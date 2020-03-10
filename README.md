# jira-tools
If you're like me, you forget (on a daily basis) to move your JIRA tickets around. I wrote this script to not only remind myself to do so, but to embed it into my already command-line-heavy workflow.

## Note
This is **super** not production ready. It's currently pretty tightly coupled with my use case, but I plan to (very) slowly fix that.

## How does it work?
The script is currently dependent on https://github.com/go-jira/jira, along with some custom configuration files from my dotfiles repo.

The general gist is this:
  - a many-to-one relationship exists between git branches and JIRA tickets.
  - `jira-tools start` will show you your currently active tickets
    - selecting one will show the associated branches or prompt you to create one
  - `jira-tools pull-request` will open a PR for the current branch (and autofill the JIRA ticket if found)
  - `jira-tools daemon` is a GitHub poller that moves completed tickets to "Done" when the PR lands.
