## Start Design and Development Work on a New Story

### Pivotal Tracker

We use [Pivotal Tracker](https://www.pivotaltracker.com) to capture ideas, turn them into stories, prioritize stories and communicate status of stories. When starting a new story, follow these steps in the Pivotal Tracker project.

1. **Review** the story description, labels, tasks and activities. 
If your review of the story creates any open questions, create a new comment with the question to the story owner.

2. **Confirm** there are no blockers or impediments. 
If you think of any blockers at this point, note them in the Pivotal BLOCKERS field and add a comment. If you can work to remove the blocker, do so. Otherwise you may need to move on to another story.

3. **Take ownership**. Set STORY OWNER to yourself and any other developers working on the story.
This lets all stakeholders know who to contact regarding items related to the story.

4. **Start**
Hit the "Start" button. This changes the story STATE from 'Unstarted' to 'Started'.

### Design

Create a high level design document before a single line of code is written. While some of the design decisions can be captured in the Pivotal story or in code comments, we should keep a business-level document that explains the new feature or changes to future stakeholders. Describing the design in writing is also a great way to walk through design decisions. See <as yet unwritten section> on design documentation.

### Develop

Now that you have taken ownership of the story and have an initial understanding of how you will will develop the solution, it is time to dive in. We use [git](https://git-scm.com/) and [GitHub](https://github.com/). We use a simple branch handling strategy. Topic branches merge off of master, are deployed to an integration environment, and merge back into master when approved. See <as yet unwritten section> for details. Note: Consider something like [GitFLow](https://datasift.github.io/gitflow/IntroducingGitFlow.html) as the team grows or company needs begin to lean toward standard release cycles.

#### Ensure you are on the master branch.

```bash
$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
```

#### Create a topic branch

Follow the naming convention of `<storynumber>-story-title`.

```bash
$ git checkout -b 143534991-export
Switched to a new branch '143534991-export'
```

#### Ensure npm is up to date

Additional `npm` libraries may have been recently introduced to `master` branch. Ensure your local development environment is up-to-date and prepared for tests.

```bash
$ cd client
$ npm install
$ npm run build
```

#### Run the test suite

The `master` branch should always be passing, so ideally this step is optional. Sometimes I run the specs to ensure that if any spec failures occur, I am assured that changes I made were the cause. 

At the least, initiate guard.

```bash
$ guard
10:30:37 - INFO - Guard::RSpec is running
10:30:37 - INFO - Guard is now watching ...
```

#### Begin coding

### Document
