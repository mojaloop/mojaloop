**New Issue** - Issues are first created as a New Issue. Issues that are
new have not been reviewed or accepted. Use [GitHub labels](./GitHub-Labels.md) to indicate an Epic, Story, Question, or Bug. Tasks are handled as a to do list on a story. Bugs are new till they have an estimate, description, and optionally some steps. Then they move to backlog. Scrum masters for each team set issues into the current milestone during sprint planning (or expected milestones as part of PI planning).

**Backlog** - Backlog items have been accepted into the project, but are
not being worked yet.
-   Stories and bugs must have an estimate. Stories must be doable in a
    2-week sprint. Epics must be doable in an 8-week program increment, but don't need an estimate filled in as they are the sum of their stories. 
-   If they are stories, they must labeled with “Story”. 
-   Most stories will be in epics, however, some smaller bits of work may be be on their own, often this is to support another team (an implied epic), a spike, or clean up work.
-   Bugs have the label "bug"
-   Epics and stories have acceptance criteria as a check list that define when the work is done

For Bugs, set the milestone to match whether we expect to fix the bug and when. We don't use priority, simply set the bug milestone. For bug Severity use the following three labels:
- **Blocking**: blocking issues must be fixed ASAP and are marked to be completed within the current sprint and moved to _In Progress_
- **Planned fix**: This is a bug a team expects to fix soon. The team sets the bug milestone to an appropriate upcoming sprint, typically the next one. It stays in the backlog till then.
- **May Fix**: This bug may or may not be fixed. Put the bug on the backlog, but don't give it a milestone. Bugs like this are grouped with changes in their underlying components. The team picks up the bug at that time and changes the milestone to the appropriate sprint milestone for the change.

**In Progress** - In Progress stories and epics must have
-   All the backlog requirements
-   at least one assignee
-   a milestone

In progress questions or bugs need only an assignee and milestone.

**Ice Box** - Issues here are postponed for the current release. Most often these are issues that are blocked because of bugs or work that is not ready yet. The Ice Box is a way to call out that you have work that is waiting on others. 

Issues that are not being worked on, but will eventually go in the current release remain in the backlog.

**QA/Review** – code and docs are being reviewed
-   All the In-Progress requirements are met
-   Code and docs are checked in
-   Reviewers are added as assignees

**Closed** – all work is complete (this definition is likely to grow over
time)
-   All QA/Review requirements are met
-   All acceptance criteria are completed
-   Code, docs, functionality and non-functional behavior are reviewed &/or tested