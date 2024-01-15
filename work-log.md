# Eventide Project Work Log

## Sun Jan 14 2024

- [people] Nathan

- Supplant Bundler via a new gem installation script that just uses Rubygems directly
  - Finished implementation of the install-gems.sh script
  - [setback] Needed to determine the root cause of surprising behavior of the `gem cleanup` command
  - As a result of the setback, didn't complete the task

## Sun Jan 7 2024

- [people] Nathan, Scott

- Review word doc of gen 3 items that Nathan wrote

- Discussion of documentation namespaces for supporting multiple generations of the toolkit
  - [plan] We need to design a concrete strategy for this that accommodates both doc publishing and versioning and tagging in Git
  - [proposal] Domains:
    - docs.eventide-project.org
    - next.docs.eventide-project.org
    - previous.docs.eventide-project.org (won't host this until will switch it)

- [plan] Nathan will normalize the milestones for our repos in GitHub

- Coordination of Alek's work

- ZenHub review

- Notified community of Gen 3 work start

- [people] Nathan
  - Normalized the milestones for our repos in GitHub
  - Milestones that were called e.g. v2+ were renamed to Gen 2+, and their issues have been carried over
  - Descriptions are all blank, although they can be set later if needed
  - All milestones are "open" rather than "closed" at the moment, since that reflects the prior reality
  - Unfortunately, there doesn't appear to be a way to order milestones in GitHub
    - By observation, GitHub orders milestones by the time that a milestone was first created
    - Once past milestones are closed, GitHub's ordering won't be an issue

## Fri Jan 5 2024

- [people] Nathan, Scott

- Start of work planning for gen 3

- Bitly shortcut for issues list
  - https://bit.ly/evt-issues

- Initial tasks recognized
  - Create new items for the new libraries:
    - Protocol
    - Reflect
  - Breadth-wise review of work items
    - Eventide's root repo: https://github.com/eventide-project/eventide/issues
    - All issues, all repos: https://bit.ly/evt-issues
  - ZenHub
    - Review columns
    - Review remnant items
    - Decide on new columns
    - Is our ZenHub accessible to others
  - Review GitHub labels and decide on new ones for signalling things like requires-oversight-of-a-principal

- Refit label
  - New label
  - Significant change to a library or set of interdependent libraries

- Recorded new issues for refit of protocol discovery and reflection
