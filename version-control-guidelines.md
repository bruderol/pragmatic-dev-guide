# Version Control Guidelines
This guidelines cover the aspects of how to work with code under version control and with branches.

## Branching Model and Workflow

We work by following the **Git Flow Branching Model and Workflow**.
 
Here are the most important rules summarized and precised, how we live it in this project:

**Branch Workflow Rules:**

* **Branch `master`**: contains only the last published/released version of our software, no work is done directly on that branch. That is used for reference and bugfixes to the current released version.

* **Branch `develop`**: this is the branch where we integrate our work that is usually done on separate feature bracnhes.

* **Release Branches**: Done before a release to stabilize the release. During such stabilization phases for the next release all fixes need to be done on its release branch while we can continue to work for the next release on `develop`. 

* **Feature Branches**: That is where developers do their work, by following these simple rules:

   * **Create a feature branch with name `feature/xyz-some-description`**, 
     where the `xyz` prefix is the full issue number that this branch belongs to. 
     Example: `feature/#253-user-authentication`
   
   * **Integrate your feature branch often with work from others (at least daily!)** by pulling from the base branch (usualy `develop`)!
   
   * **Do small Pull Requests (per small task!) to review and merge your feature branches**: 
   
       * **Do this regularly (as fast as possible!) and NOT for work of several weeks!** Usually for each task on a story. Avoid having long living isolated feature branches with many unintegrated changes. Those will become more difficult to merge and to review. Try to slice your work into small junks that can be merged fast, without disturbing others (see "elephant carpaccio").
       
       * **Open Pull Request on your Git Web Frontend (Gitlab, Github, Bitbucket, ...) and post to your team's `#review`-channel for review:** One colleague (at least) will review it and give you feedback (4 eyes principle!). This is a good way we can learn from each other, do know how transfer and constantly improve our quality of work.
       
       * **Take the feedback from review seriously and try to improve accordingly:** 
          * Small corrections and critical issues should be done immediately on the same PR (just push to same branch again!)
          * Less critical review comments may also just lead to new tasks, that you open, to resolve them later. Because often during the review of a PR ideas may come up, that should not block the merging of your PR.
          * Some of this tasks might even need further discussions with the reviewer or even the team what is the best solution and further planning.
          * Do not block merging of PRs because of uncritical feedback that can be resolved later.

 * **Hotfix Branches:** those are used in the same way as Feature Branches to fix issues on release branches or even the master branch.
      * **Hotfixes need also be merged to the `develop` branch (immediately!)**: Every developer is responsible to merge the release or hotfix branch also to develop, as soon as he is done (after merging it to the target release or master branch). It is important to do this regularly and immediately after a merge is done to the release or master branches, such that no one else will have troubles (merge conflicts from other's changes) with merging later similar changes to the develop branch.

For more detailed informations about Git Flow Branching Workflow, see [Git Flow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

## Commit Messages

Most important Guidelines for Commit Messages:

* Prefix each commit message with a nice subject line.<br/>
  Example: `#253 Add User Authentication`
   * Start with the issue number of the issue (use same formatting as in your issue management tool, including any project prefix, if needed).
      e.g. `#253` or `MYPROJ-421`
   * Add short high level description of what you did 
   * Description is in imperative form: 
      as if you would order the commit what it does.
      E.g. “Update dependencies” instead of “Updates dependencies” or “Updated dependencies”
   * Try to keep it shorter than 50 characters
   * Avoid "Implement ..." as a verb 
      (yes, sure, that is what we usually do!)
* Use more lines to explain the commit, if necessary
* Try to follow other recommendations in this useful [Guide for Commit Messages](http://chris.beams.io/posts/git-commit/) 