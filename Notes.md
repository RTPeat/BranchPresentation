# Git Branching and Merging

* Git branches are much more lightweight than in other version control systems.
* This means that in Git branches can be used much more frequently as part of a daily developer workflow.
* In Git a branch represents an independent line of development, so for example whereas in TFS you often just check out files from the main branch and merge the checked out files in as part of a changeset, and branches are often used only for large tasks, in Git you create a separate branch for your work and merge that branch in.
* Working on a branch allows you to easily store intermediate changes, and work can be passed between developers, something that's a lot harder on TFS when only checking out files.
* Branches also allow simultaneous work on the same code.
* There are multiple different branching strategies in use, these include:
    * GitFlow - a master branch, and develop branch, development happens in branches off the develop branch, which are merged into the develop branch. Code is released when it is merged from develop into master. Also allows hotfix branches off master.
    * In response to the complexity of GitFlow, there is GitHub flow, which has a single master branch, and feature development occurring on branches off master and merging into master.
    * A problem with GitHub flow is that it assumes that you will deploy every time you merge a feature branch. GitLab flow adapts this model by keeping development on a single master branch, but having at least one production branch to which code is merged to release it. This can be enhanced by having environment branches to represent each deployment environment, or release branches for particular releases.
* Computershare has decided to use GitLab flow for projects as we move to Azure Devops, utilising environmental branches where required to handle regional differences.
* Getting onto one of the evangelical arguments in the Git world, when using feature branching what is the best way to incorporate finished work back into the main line of development?
    * Should we adopt a rebase policy where the repository history is kept flat and clean?
    * Should we adopt a merge policy which gives traceability at the expense of readability and clarity?
* To confuse matters even when using an always merge model, rebase is useful to keep your branch up to date with changes on the master branch, for tidying your code ready for review in a pull request, or for creating a tidy set of commits ready to merge into the master branch.
* Initially Computershare is proposing to use a merge policy for all projects as we move to Azure Devops, but feel free to use rebasing to tidy the merges up!

# Git Exercise

* Should have access to the GitDemo repository used previously (need to ensure people have completed that before coming to the new session)
* We need to make changes to the master branch before the session so there is something to merge with.
* Have everybody rebase their branch from the previous session onto the updated master - `git rebase -i <base>`


