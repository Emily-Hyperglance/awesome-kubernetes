# Git and Patterns for Managing Source Code Branches. Merge BOTs
- [Git Distributed Version-Control System](#git-distributed-version-control-system)
- [Design By Contract](#design-by-contract)
- [Git Cheat Sheets](#git-cheat-sheets)
- [Monorepo VS Polyrepo](#monorepo-vs-polyrepo)
- [Patterns for Managing Source Code Branches (Branching Models/Workflows)](#patterns-for-managing-source-code-branches-branching-modelsworkflows)
    - [Git Workflows](#git-workflows)
    - [Trunk Based Development](#trunk-based-development)
    - [Feature Branch Development (aka GitFlow)](#feature-branch-development-aka-gitflow)
        - [Git Flow](#git-flow)
    - [Trunk-based Development vs. Git Flow](#trunk-based-development-vs-git-flow)
    - [Alternative Branching Models](#alternative-branching-models)
        - [Feature Flags (Feature Toggles)](#feature-flags-feature-toggles)
            - [Keystone Interface and Keystone Flags](#keystone-interface-and-keystone-flags)
- [Git Commands](#git-commands)
- [BitBucket](#bitbucket)
- [GitLab](#gitlab)
- [GitHub](#github)
    - [GitHub Actions and OpenShift](#github-actions-and-openshift)
- [Git Tools](#git-tools)
    - [Semantic-release. CI/CD semantic release workflow (semantic Versioning, commit format and releases)](#semantic-release-cicd-semantic-release-workflow-semantic-versioning-commit-format-and-releases)
- [Azure DevOps (formerly known as VSTS)](#azure-devops-formerly-known-as-vsts)
- [Pre Commit Hooks](#pre-commit-hooks)
- [Merge BOTs](#merge-bots)
    - [Tips](#tips)
    - [Jenkins for git merges](#jenkins-for-git-merges)
    - [Bitbucket for git merges](#bitbucket-for-git-merges)
    - [GitLab for git merges](#gitlab-for-git-merges)
        - [Marge GitLab bot](#marge-gitlab-bot)
    - [Jenkins-X bots](#jenkins-x-bots)
    - [Plastic SCM bot](#plastic-scm-bot)
    - [Mergify bot](#mergify-bot)
    - [GitHub bots](#github-bots)
        - [Bors GitHub bot](#bors-github-bot)

## Git Distributed Version-Control System
* [Wikipedia: Git](https://en.wikipedia.org/wiki/Git)
* [Git](https://git-scm.com/)
    * [git-scm.com/book](https://git-scm.com/book)
* [devdocs.io/git/](https://devdocs.io/git/)
* [tutorialzine.com: Learn git in 30 minutes 🌟](https://tutorialzine.com/2016/06/learn-git-in-30-minutes)
* [3 Git Commands I Use Every Day](https://dev.to/gonedark/3-git-commands-i-use-every-day)
* [Git and Github in Plain English](https://red-badger.com/blog/2016/11/29/gitgithub-in-plain-english)
* [opensource.com: How to restore older file versions in Git](https://opensource.com/life/16/7/how-restore-older-file-versions-git)
* [9 awesome git tricks](https://tychoish.com/post/9-awesome-git-tricks/)
* [Awesome Git 🌟](https://github.com/dictcp/awesome-git)
* [dzone.com: intro git 🌟](https://dzone.com/articles/intro-git)
* [dzone.com: Top 20 git commands with examples 🌟](https://dzone.com/articles/top-20-git-commands-with-examples)
* [dzone.com: 8 Useful But Not Well-Known Git Concepts](https://dzone.com/articles/8-useful-but-not-well-known-git-concepts) These lesser-known Git tricks can help you solve problems that are not handled well by the GitHub and BitBucket GUIs
* [dzone.com: Git Commands Tutorial - Part 1](https://dzone.com/articles/git-commands-tutorial-part-1)
* [dzone.com: Git Commands Tutorial - Part 2](https://dzone.com/articles/git-commands-tutorial-part-2)
* [Dzone refcard: Getting started with Git](https://dzone.com/refcardz/getting-started-git)
* [Oh shit, git!](https://ohshitgit.com/)
* [How to Get More Out of Your Git Commit Message](https://datree.io/blog/git-commit-message-conventions-for-readable-git-log/)
* [10 useful Git commands you wish existed – and their alternatives](https://datree.io/blog/useful-git-commands-list/)
* [github.blog: How to undo (almost) anything with Git](https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/)
* [dev.to: Git Explained - The Basics](https://dev.to/milu_franz/git-explained-the-basics-igc)
* [medium: 7 Best Courses to Master Git and Github for Programmers](https://medium.com/javarevisited/7-best-courses-to-master-git-and-github-for-programmers-d671859a68b2) These are the best courses to learn Git from scratch and also advanced concepts like branching and merging. It also includes a free course to learn git.
* [medium: Top 7 Cloud Source Code Management Tools Features and Pricing Plans](https://medium.com/@atif.ramzan89/top-7-cloud-source-code-management-tools-features-and-pricing-plans-105f4eb88a3a)
* [towardsdatascience.com: The 6 Git Commands Data Scientist Should Know](https://towardsdatascience.com/the-only-6-git-commands-you-need-to-know-995065db1ae0) An introduction to using Git for machine learning projects.
* [dev.to: Git Concepts I Wish I Knew Years Ago 🌟](https://dev.to/g_abud/advanced-git-reference-1o9j)
* [opensource.com: 6 best practices for managing Git repos](https://opensource.com/article/20/7/git-repos-best-practices) Resist the urge to add things in Git that will make it harder to manage; here's what to do instead.
* [codeburst.io: Debug your code using git bisect](https://codeburst.io/debug-your-code-using-git-bisect-45db2983cc69)
* [github.blog: Highlights from Git 2.28](https://github.blog/2020-07-27-highlights-from-git-2-28/)
* [codeburst.io: A Resource for all Things Git](https://codeburst.io/a-resource-for-all-things-git-b63d6626beca)
* [Things You Want to Do in Git and How to Do Them](https://stu2b50.dev/posts/things-you-wante9665)
* [Learn Git Branching 🌟](https://learngitbranching.js.org/) An interactive Git visualization tool to educate and challenge!
* [livecodestream.dev: Git Concepts and Workflow for Beginners](https://livecodestream.dev/post/2020-08-21-git-concepts-and-workflow-for-beginners/)
* [thenextweb.com: A beginner’s guide to the most popular Git commands](https://thenextweb.com/syndication/2020/09/02/a-beginners-guide-to-the-most-popular-git-commands/)
* [devroom.io: Git Squash your latests commits into one ](https://www.devroom.io/2011/07/05/git-squash-your-latests-commits-into-one/)
* [julien.danjou.info: Stop merging your pull requests manually 🌟](https://julien.danjou.info/stop-merging-your-pull-request-manually/) -> [mergify 🌟](https://mergify.io/)
* [gitlab.com: How to keep your Git history clean with interactive rebase](https://about.gitlab.com/blog/2020/11/23/keep-git-history-clean-with-interactive-rebase/) Interactive rebase is one of Git’s most versatile tools. Here's how to use it to correct commit messages, fix mistakes, and more.
* [opensource.com: 8 Git aliases that make me more efficient](https://opensource.com/article/20/11/git-aliases) Use aliases to create shortcuts for your most-used or complex Git commands.
* [gitkraken.com: Git Tutorials: Instructional Training Videos 🌟](https://www.gitkraken.com/learn/git/tutorials)
* [github.blog: Token authentication requirements for Git operations](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/)
* [github.blog: Commits are snapshots, not diffs](https://github.blog/2020-12-17-commits-are-snapshots-not-diffs/)
* [github.blog: Get up to speed with partial clone and shallow clone](https://github.blog/2020-12-21-get-up-to-speed-with-partial-clone-and-shallow-clone/)
* [about.gitlab.com: How Git Partial Clone lets you fetch only the large file you need](https://about.gitlab.com/blog/2020/03/13/partial-clone-for-massive-repositories/) 
* [gitkraken.com: How do you rename a Git branch?](https://www.gitkraken.com/learn/git/problems/rename-git-branch)
* [intellipaat.com: Git Tutorial - Learn Git 🌟](https://intellipaat.com/blog/tutorial/devops-tutorial/git-tutorial/)
* [freecodecamp.org: Git Checkout Remote Branch Tutorial](https://www.freecodecamp.org/news/git-checkout-remote-branch-tutorial/)
* [freecodecamp.org: How to Use Multiple Git Configs on One Computer 🌟](https://www.freecodecamp.org/news/how-to-handle-multiple-git-configurations-in-one-machine/)
* [freecodecamp.org: How to Use Branches in Git – the Ultimate Cheatsheet 🌟](https://www.freecodecamp.org/news/how-to-use-branches-in-git/)
* [dev.to: Git for beginners](https://dev.to/purveshshende2/git-for-beginners-3il6)
* [blog.gitguardian.com: Rewriting your git history, removing files permanently - cheatsheet & guide](https://blog.gitguardian.com/rewriting-git-history-cheatsheet/)
* [smashingmagazine.com: Getting The Most Out Of Git](https://www.smashingmagazine.com/2021/02/getting-the-most-out-of-git/)
* [thenewstack.io: Why Open Source Project Maintainers are Reluctant to use Digital Signatures, Two-Factor Authentication](https://thenewstack.io/why-open-source-project-maintainers-are-reluctant-to-use-digital-signatures-two-factor-authentication/)
* [geeksforgeeks.org: How to Write Good Commit Messages in GitHub?](https://www.geeksforgeeks.org/how-to-write-good-commit-messages-in-github/)

## Design By Contract
[Wikipedia: Design by contract (DbC)](https://en.wikipedia.org/wiki/Design_by_contract), also known as contract programming, programming by contract and design-by-contract programming, is an approach for designing software. 

It prescribes that software designers should define formal, precise and verifiable interface specifications for software components, which extend the ordinary definition of abstract data types with preconditions, postconditions and invariants. These specifications are referred to as "contracts", in accordance with a conceptual metaphor with the conditions and obligations of business contracts.

## Git Cheat Sheets
* [Git and GitHub Cheat Sheets](cheatsheets.md)

## Monorepo VS Polyrepo
* [fourtheorem.com: How to end Microservice pain and embrace the Monorepo](https://www.fourtheorem.com/blog/monorepo)
* [medium: The Pros and Cons of Monorepos, Explained](https://medium.com/better-programming/the-pros-and-cons-monorepos-explained-f86c998392e1) Should you keep all of your code in a single directory?

## Patterns for Managing Source Code Branches (Branching Models/Workflows)
* [paulhammant.com: What is Your Branching Model?:](https://paulhammant.com/2013/12/04/what_is_your_branching_model/) Mainline, Cascade, Trunk-Based Development, Short Lived Feature Branches, Continuous Deployment, Subversion noise on branching, etc.
* [adevait.com: Creating a Branching Strategy for Small Teams](https://adevait.com/software/creating-branching-strategy)
* [atlassian.com: Configuring branching models 🌟](https://confluence.atlassian.com/bitbucketserver/using-branches-in-bitbucket-server-776639968.html#UsingbranchesinBitbucketServer-model)
* [git-scm.com: Git Branching - Branching Workflows](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)
* [git-scm.com: Distributed Git - Distributed Workflows](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows#Integration-Manager-Workflow)
    * [Distributed Git - Distributed Workflows - Integration-Manager Workflow](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows#Integration-Manager-Workflow)
    * [Setup Git Integration Manager Workflow in Eclipse](https://stackoverflow.com/questions/26003298/how-to-setup-local-git-with-local-blessed-repo-integration-manager-workflow)
* [Dzone refcard: Git Patterns and Anti-Patterns](https://dzone.com/refcardz/git-patterns-and-anti-patterns) Scaling from Workgroup to Enterprise. Suggests patterns and anti-patterns, including Hybrid SCM, Git champions, blessed repository, per-feature topic branches, and ALM integration.
* [Dzone: Basic Git Branching](https://dzone.com/articles/basic-git-branching) In this article, we walk through the basics of branching with Git to get you started with better managing your versioning during projects.
* [martinfowler.com: Patterns for Managing Source Code Branches](https://martinfowler.com/articles/branching-patterns.html)
    * [Release Branch Pattern:](https://martinfowler.com/articles/branching-patterns.html#release-branch) A branch that only accepts commits accepted to stabilize a version of the product ready for release.
* [medium: Which Git branching model should I select for my project?](https://medium.com/aventude/which-git-branching-model-should-i-select-73aafc503b5f)
* [speakerdeck.com: 10 Git Anti Patterns You Should be Aware of 🌟](https://speakerdeck.com/lemiorhan/10-git-anti-patterns-you-should-be-aware-of)
* [Dzone: Git Branch Naming Conventions](https://dzone.com/articles/git-branch-naming-conventions-1) A primer on naming branches for modern git workflows.
* [gitkraken.com: Branching in Git 🌟](https://www.gitkraken.com/learn/git/branch)

<center>
<script async class="speakerdeck-embed" data-id="1eaed7dabacb4f9b9c96b08de38eb9e1" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>
</center>

### Git Workflows
* ```git help workflows```
* [atlassian.com: Comparing Workflows 🌟](https://www.atlassian.com/git/tutorials/comparing-workflows)
* [GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)
* [GitHub Flow](https://guides.github.com/introduction/flow/)
* [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/)
* [Git DMZ Flow](https://gist.github.com/djspiewak/9f2f91085607a4859a66)
* [kubernetes.dev: GitHub Workflow](https://www.kubernetes.dev/docs/guide/github-workflow/) An overview of the GitHub workflow used by the Kubernetes project. It includes some tips and suggestions on things such as keeping your local environment in sync with upstream and commit hygiene.

### Trunk Based Development
* [Trunk Based Development](https://trunkbaseddevelopment.com/)
* [paulhammant.com: What is Trunk-Based Development?](https://paulhammant.com/2013/04/05/what-is-trunk-based-development/)
* [The Origins of Trunk Based Development](https://dzone.com/articles/origins-trunk-based)
* [quora.com: What is trunk based development?](https://www.quora.com/What-is-trunk-based-development)
* [kean.github.io: Trunk-Based Development](https://kean.github.io/post/trunk-based-development)
* [paulhammant.com: Microsoft's Trunk-Based Development](https://paulhammant.com/2014/04/03/microsofts-trunk-based-development/)
* [devblogs.microsoft.com: Release Flow: How We Do Branching on the VSTS Team](https://devblogs.microsoft.com/devops/release-flow-how-we-do-branching-on-the-vsts-team/)

### Feature Branch Development (aka GitFlow)
* [nvie.com: Feature Branches. A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)

#### Git Flow 
* One of the main concepts of **GitFlow** is **feature branches**. The idea is that each feature should be developed in its own branch. When the feature is done, it gets merged into develop branch. 
* [devopszone.info: An Introduction To Git-flow Workflow](https://www.devopszone.info/post/an-introduction-to-git-flow-workflow)
* [atlassian.com: Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
* [gitkraken.com: GitFlow](https://support.gitkraken.com/git-workflows-and-extensions/git-flow/) is a list of rules to keep a repo’s history organized, and is used to make the release process, bug fixes, and feature creation easier.
* [git-flow.readthedocs.io](https://git-flow.readthedocs.io/)
* [medium.com: Gitflow — Branch Guide](https://medium.com/@rafavinnce/gitflow-branch-guide-8a523360c053)
* [medium.com: Git Flow for Beginners](https://medium.com/@thibault60000/git-flow-for-beginners-d7a152b2c1f9)
* [medium.com: What is GitFlow?](https://medium.com/@okandavut/what-is-gitflow-c0be7a659992)
* [gist.github.com/JamesMGreene: A comparison of using `git flow` commands versus raw `git` commands](https://gist.github.com/JamesMGreene/cdd0ac49f90c987e45ac)
* [Git-flow cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/index.html)
* [aprendegit.com: git-flow: la rama develop y uso de feature branches](http://aprendegit.com/git-flow-la-rama-develop-y-uso-de-feature-branches/)

### Trunk-based Development vs. Git Flow
* [toptal.com: Trunk-based Development vs. Git Flow](https://www.toptal.com/software/trunk-based-development-git-flow)
* [victorops.com: Source Code Control: Trunk-Based Development vs. GitFlow](https://victorops.com/blog/source-code-control-trunk-based-development-vs-gitflow)
* [medium: GitFlow VS Trunk-Based-Development](https://medium.com/@vafrcor2009/gitflow-vs-trunk-based-development-3beff578030b)
* [Dzone: Why I Prefer Trunk-Based Development Over Feature Branching and GitFlow 🌟](https://dzone.com/articles/why-i-prefer-trunk-based-development-over-feature) Check out the components of Trunk-based Development as implemented by Facebook and Google, and see how it helps resolve and prevent merge conflicts.
* [team-coder.com: From Git Flow to Trunk Based Development](https://team-coder.com/from-git-flow-to-trunk-based-development/)
* [stridenyc.com/podcasts: Trunk Based Development vs Gitflow](https://www.stridenyc.com/podcasts/30-trunk-based-development-vs-gitflow)

### Alternative Branching Models
* [trunkbaseddevelopment.com: Alternative Branching Models](https://trunkbaseddevelopment.com/alternative-branching-models/)

#### Feature Flags (Feature Toggles)
* [featureflags.io: Flags vs Branching](https://featureflags.io/feature-flags-vs-branching/) Branch better with feature flag driven development.
* [martinfowler.com: Feature Toggles (aka Feature Flags)](https://martinfowler.com/articles/feature-toggles.html)
* [#FeatureFlags](https://twitter.com/hashtag/featureflag)
* [CloudBees Releases Another Industry First: Feature Flagging for On-Premise Use 🌟](https://www.previous.cloudbees.com/press/cloudbees-releases-another-industry-first-feature-flagging-premise-use)
* [cioperu.pe: 5 formas de impulsar la utilización de feature flags](https://cioperu.pe/articulo/30477/devops-5-formas-de-impulsar-la-utilizacion-de-feature-flags/)
* [cloudbees.com: Testing with Feature Flags to Improve Developer Productivity](https://www.cloudbees.com/blog/feature-flags-improve-developer-productivity)
* [cloudbees.com: Goodbye Sleepless Nights: De-Risking Deployments with Feature Flags](https://www.cloudbees.com/case-study/petdesk)
* [thenewstack.io: Wave Goodbye to Release Nights](https://thenewstack.io/wave-goodbye-to-release-nights/)
* [infoworld.com: Why aren’t you using feature flags?](https://www.infoworld.com/article/3600150/why-arent-you-using-feature-flags.amp.html) Software development is changing. If you’re still focused on release management rather than feature management, then you’re doing it wrong.
* [cloudbees.com: How to Grow Continuous Delivery Maturity Using Feature Flags](https://www.cloudbees.com/blog/grow-cd-maturity)
* [cloudbees.com: Feature Flag Best Practices: Change Management in Production](https://www.cloudbees.com/blog/change-management-in-production)
* [cloudbees.com: Feature Flag Best Practices: Understanding the Feature Flag Lifecycle](https://www.cloudbees.com/blog/feature-flag-lifecycle)

##### Keystone Interface and Keystone Flags
* [martinfowler.com: KeystoneInterface](https://martinfowler.com/bliki/KeystoneInterface.html)
* [split.io: Keystone Flags: Feature Flagging With Less Mess](https://split.io/blog/keystone-feature-flags/)

## Git Commands
* Show commit logs:

```bash
git log --oneline --all --graph --decorate
```

* [Removing the last commit](https://gist.github.com/CrookedNumber/8964442):

```bash
git reset --hard HEAD^
git push origin -f
```

## BitBucket
* [bitbucket.org](https://bitbucket.org/)
* [Atlassian Git Cheatsheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
* [Dzone: source control using atlassian bitbucket](https://dzone.com/articles/source-control-using-atlassian-bitbucket)
* [Dzone: how I use bitbucket in my regular routine](https://dzone.com/articles/how-i-use-bitbucket-in-my-regular-routine)

## GitLab
* [gitlab.com](https://gitlab.com/)
* [Dzone: using gitlab API to create projects](https://dzone.com/articles/using-gitlab-rest-api-to-create-projects)
* [gitlab.com: GitLab’s guide to CI/CD for beginners](https://about.gitlab.com/blog/2020/07/06/beginner-guide-ci-cd/) CI/CD is a key part of the DevOps journey. Here’s everything you need to understand about this game-changing process.
* [levelup.gitconnected.com: Automating Integration and Deployment to Remote Server](https://levelup.gitconnected.com/automating-integration-and-deployment-to-remote-server-63a2b6576ebf) GitLab CI/CD
* [about.gitlab.com: Want a more effective CI/CD pipeline? Try our pro tips](https://about.gitlab.com/blog/2020/07/29/effective-ci-cd-pipelines/) Here’s how to take your CI/CD pipeline to the next level with hands on advice about faster builds, better security and more.
* [gitlab.com: How to do GitLab merge request reviews in VS Code](https://about.gitlab.com/blog/2021/01/25/mr-reviews-with-vs-code/)
* [about.gitlab.com: How we used parallel CI/CD jobs to increase our productivity](https://about.gitlab.com/blog/2021/01/20/using-run-parallel-jobs/) GitLab uses parallel jobs to help long-running jobs run faster.
* [about.gitlab.com: How to use GitLab CI to deploy to multiple environments](https://about.gitlab.com/blog/2021/02/05/ci-deployment-and-environments/)
* [about.gitlab.com: Meet Pipeline Editor, your one-stop-shop for building a CI/CD pipeline](https://about.gitlab.com/blog/2021/02/22/pipeline-editor-overview/)
* [about.gitlab.com: A new era of Kubernetes integrations on GitLab.com](https://about.gitlab.com/blog/2021/02/22/gitlab-kubernetes-agent-on-gitlab-com/) The GitLab Kubernetes Agent enables secure deployments from GitLab SaaS to your Kubernetes cluster and provides deep integrations of your cluster to GitLab.

## GitHub
* [githubstatus.com 🌟](https://www.githubstatus.com/)
* [GitHub Codespaces](https://github.com/features/codespaces) Get the full Visual Studio Code experience without leaving GitHub.
* [GitHub CLI](https://cli.github.com/)
    * [github.com/cli/cli](https://github.com/cli/cli)
    * [github.blog: GitHub CLI allows you to close, reopen, and add metadata to issues and pull requests](https://github.blog/changelog/2020-05-11-github-cli-allows-you-to-close-reopen-and-add-metadata-to-issues-and-pull-requests/)
    * [github.blog: Mark pull requests as ready for review, view the diff, review, and merge from GitHub CLI](https://github.blog/changelog/2020-05-26-mark-pull-requests-as-ready-for-review-review-and-merge-from-github-cli/)
* [githubstatus.com/uptime 🌟](https://www.githubstatus.com/uptime)
* [github.blog: How we launched docs.github.com](https://github.blog/2020-07-02-how-we-launched-docs-github-com/)
* [Introducing GitHub’s OpenAPI Description](https://github.blog/2020-07-27-introducing-githubs-openapi-description/)
* [GitHub public roadmap 🌟](https://github.com/github/roadmap)
* [Token authentication requirements for API and Git operations](https://github.blog/2020-07-30-token-authentication-requirements-for-api-and-git-operations/)
* [GitHub Chaos Actions in Your CI/CD workflow](https://blog.mayadata.io/github-chaos-actions-in-your-ci/cd-workflow-part-1)
* [GitHub's OpenAPI Spec Open-Sourced in Beta](https://www.infoq.com/news/2020/08/GitHub-open-api-spec/)
* [Things you didn't know you could diff in GitHub](https://sebastiandedeyne.com/things-you-didnt-know-you-could-diff-in-github/)
* [github.blog: Set the default branch for newly-created repositories](https://github.blog/changelog/2020-08-26-set-the-default-branch-for-newly-created-repositories/)
* [grafana.com: How we use the Grafana GitHub plugin to track outstanding pull requests](https://grafana.com/blog/2020/09/21/how-we-use-the-grafana-github-plugin-to-track-outstanding-pull-requests/)
* [itnext.io: Build & Ship: GitHub Container Registry & Kubernetes](https://itnext.io/build-ship-github-container-registry-kubernetes-aa06029b3f21)
* [grafana: How we use the Grafana GitHub plugin to track outstanding pull requests](https://grafana.com/blog/2020/09/21/how-we-use-the-grafana-github-plugin-to-track-outstanding-pull-requests/)
* [docker.com: Docker Github Actions](https://www.docker.com/blog/docker-github-actions/)
* [itnext.io: Build & Ship: GitHub Container Registry & Kubernetes](https://itnext.io/build-ship-github-container-registry-kubernetes-aa06029b3f21)
* [github.blog: Testing cloud apps with GitHub Actions and cloud-native open source tools](https://github.blog/2020-10-09-devops-cloud-testing/)
* [theregister.com: Passwords begone: GitHub will ban them next year for authenticating Git operations](https://www.theregister.com/2020/12/17/github_bans_passwords/)
* [github.blog: Learn about ghapi, a new third-party Python client for the GitHub API](https://github.blog/2020-12-18-learn-about-ghapi-a-new-third-party-python-client-for-the-github-api/)
* [github.blog: Improving how we deploy GitHub](https://github.blog/2021-01-25-improving-how-we-deploy-github/) 
* [github.blog: Deployment reliability at GitHub](https://github.blog/2021-02-03-deployment-reliability-at-github/)
* [github.blog: Extending GitOps to reliability-as-code with GitHub and StackPulse](https://github.blog/2021-02-04-extending-gitops-to-reliability-as-code-with-github-and-stackpulse/)
* [backhub.co](https://www.backhub.co/) Reliable GitHub repository backup, set up in minutes
* [GitHub public roadmap 🌟](https://github.com/github/roadmap)

### GitHub Actions and OpenShift
- [redhat.com: Red Hat and GitHub Collaborate to Expand the Developer Experience on Red Hat OpenShift with GitHub Actions 🌟](https://www.redhat.com/en/about/press-releases/red-hat-and-github-collaborate-expand-developer-experience-red-hat-openshift-github-actions) Industry’s leading enterprise Kubernetes platform now integrates with GitHub, bringing DevOps automation tools from the world’s largest developer platform into the OpenShift ecosystem
- [openshift.com: Deploying to OpenShift using GitHub Actions](https://www.openshift.com/blog/deploying-to-openshift-using-github-actions)
- [github.com: RedHat Actions 🌟](https://github.com/redhat-actions)
- [github.com: OpenShift GitHub Actions Runner 🌟](https://github.com/redhat-actions/openshift-actions-runner)
- [github.com: OpenShift GitHub Actions Runner Chart 🌟](https://github.com/redhat-actions/openshift-actions-runner-chart)

## Git Tools
* [Atlassian Sourcetree](https://www.sourcetreeapp.com/)
    * [Sourcetree Cheat Sheet](https://kapeli.com/cheat_sheets/Sourcetree.docset/Contents/Resources/Documents/index)
* [gitkraken.com](https://www.gitkraken.com/)
    * [GitKraken Git Cheat](https://www.gitkraken.com/resources/gitkraken-cheat-sheet)
    * [dzone.com: See What's New in GitKraken v4.0](https://dzone.com/articles/see-whats-new-in-gitkraken-v40)
    * [youtube: GitKraken Tutorials and Tips](https://www.youtube.com/watch?v=gjtXTm_TvvE&list=PLe6EXFvnTV78WqGmGSq8JPnafR3lAa55n)
* [gmaster](https://gmaster.io/)
* [Visual Studio Code (Git Extensions)](visual-studio.md)
* [Visual Studio Online](https://visualstudio.microsoft.com/services/visual-studio-codespaces/)

### Semantic-release. CI/CD semantic release workflow (semantic Versioning, commit format and releases)
* [semantic-release.gitbook.io 🌟](https://semantic-release.gitbook.io/semantic-release/) Semantic-release automates the whole package release workflow including: determining the next version number, generating the release notes and publishing the package.
* [css-tricks.com: How to Automate Project Versioning and Releases with Continuous Deployment 🌟](https://css-tricks.com/how-to-automate-project-versioning-and-releases-with-continuous-deployment/)

## Azure DevOps (formerly known as VSTS) 
* [Wikipedia: Azure DevOps](https://en.wikipedia.org/wiki/Azure_DevOps)
    * [wikipedia: Azure DevOps Server](https://en.wikipedia.org/wiki/Azure_DevOps_Server) Collaboration software for software development formerly known as Team Foundation Server and Visual Studio Team System
    * [wikipedia: Azure DevOps Services](https://en.wikipedia.org/wiki/Microsoft_Visual_Studio#Azure_DevOps_Services) Cloud service for software development formerly known as Visual Studio Team Services, Visual Studio Online and Team Foundation Service Preview
* [Azure DevOps Labs 🌟](https://azuredevopslabs.com/)
* [twitter.com/azuredevops](https://twitter.com/azuredevops)
* [Microsoft Visual Studio Team Services (VSTS)](https://www.dotnetcurry.com/visualstudio/1322/what-is-visual-studio-team-system-vsts)
* [Microsoft Visual Studio Team Services (VSTS) Tutorial: The Cloud ALM Platform](https://www.softwaretestinghelp.com/microsoft-vsts-tutorial-1/)
* [slideshare.net: Git version control and trunk based approach with VSTS](https://www.slideshare.net/arunmurughan/git-version-control-and-trunk-based-approach-with-vsts)
* [Microsoft Replacing Visual Studio Team Services with Azure DevOps](https://redmondmag.com/articles/2018/09/10/microsoft-replacing-vsts-with-azure-devops.aspx)
* [How We Use Git at Microsoft](https://docs.microsoft.com/en-us/azure/devops/learn/devops-at-microsoft/use-git-microsoft)

## Pre Commit Hooks
- [pre-commit](https://pre-commit.com/) A framework for managing and maintaining multi-language pre-commit hooks.
- [towardsdatascience.com: CI/CD by Example in Python](https://towardsdatascience.com/ci-cd-by-example-in-python-46f1533cb09d) A simple demonstration of CI/CD in Python with poetry and pre-commit hooks, [poetry-template](https://github.com/edkrueger/poetry-template)

## Merge BOTs
* The Merge Bot is a tool to orchestrate pull requests merging into the stable branches.
* [Wikipedia: Software bot](https://en.wikipedia.org/wiki/Software_bot)

### Tips
* Use bots to accomplish tasks like merging PR's that have been approved and automatically updating dependencies. Usage of one of these bots might allow us to trigger certain builds based off of specific GitHub tags,  it would allow us to only selectively run certain test suites and increase the throughput of the build by only testing changes made in a branch / PR.
* Investigate options that are available and see if we can integrate them with CI.
* We should be able to configure this bot to automatically apply labels to PR's based off of what is changed in a PR. For instance, if a PR contains any documentation changes, the area/Documentation label can be applied.

### Jenkins for git merges
* [**Git Plugin**: Merge Extensions](https://plugins.jenkins.io/git/#merge-extensions)
* [**Validated Merge Plugin** for Git in CloudBees Jenkins Enterprise 🌟](https://docs.cloudbees.com/docs/admin-resources/latest/plugins/validated-merge#chapter-validated-merge_validated-merge)
* [How to configure Jenkins for git merge](https://support.cloudbees.com/hc/en-us/articles/227246387-How-to-Configure-Jenkins-for-Git-Merge-)
* [GitHub Pull Request Builder Plugin](https://plugins.jenkins.io/ghprb/) , [github ref](https://github.com/jenkinsci/ghprb-plugin). You should probably migrate to GitHub Branch Source Plugin.
* [GitHub Branch Source Plugin:](https://plugins.jenkins.io/github-branch-source/) Allows you to create a new project based on the repository structure from one or more GitHub users or organizations.

### Bitbucket for git merges
* [Automatic branch merging](https://confluence.atlassian.com/bitbucketserver/automatic-branch-merging-776639993.html)
* [BitBucket Auto Merge](https://github.com/bluefrg/bitbucket-auto-merge) Automatically create and merge pull request to keep branches in sync.
* [Checks for merging pull requests](https://confluence.atlassian.com/bitbucketserver/checks-for-merging-pull-requests-776640039.html)
* [BitBucket Bot for Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/new-bitbucket-bot-for-microsoft-teams/ba-p/218212)
* [Code Dog](https://code-dog.app/) Merge your Pull Requests sooner. Some of the Slack messages your team sends are critical for productivity.
Automate them.
* [Jenkins Plugin: Bitbucket Push and Pull Request](https://plugins.jenkins.io/bitbucket-push-and-pull-request/)
* [How to Implement the Automerge feature that is missing from BitBucket cloud](https://poolofthought.com/how-to-implement-the-automerge-feature-that-is-missing-from-bitbucket-cloud/)
* [Configure bitbucket-pipelines.yml to automatically merge feature branch to master?](https://community.atlassian.com/t5/Bitbucket-questions/configure-bitbucket-pipelines-yml-to-automatically-merge-feature/qaq-p/793222)

### GitLab for git merges
* [Auto-merge between release branches](https://gitlab.com/gitlab-org/gitlab/-/issues/2785)
* [Provide merge bot functionality](https://gitlab.com/gitlab-org/gitlab/-/issues/14595)
* [lab.texthtml.net: Gitlab Merge Bot](https://lab.texthtml.net/gitlab/merge-bot)
    * [DockerHub: Gitlab Merge Bot](https://hub.docker.com/r/texthtml/gitlab-merge-bot/) Bot assistant for code review and merge requests approval for Gitlab
* [Mergecrush](https://www.mergecrush.com/) A email & slack reminder bot for Gitlab merge requests.
* [stackoverflow.com: How can we programmatically approve merge requests in GitLab?](https://stackoverflow.com/questions/58019605/how-can-we-programmatically-approve-merge-requests-in-gitlab) 
    * Our group has a bot that creates merge requests for certain mechanical changes to our code base. We'd like these MRs to get merged in automatically if/when the CI pipeline succeeds, but our projects require an approval from a member of our group. This means that right now a human has to manually click on "approve" and "merge" for each bot-created MR. Apparently GitLab doesn't have a way to set different approval rules for some users, so I haven't found a way to make the bot's user immune to this requirement.
    * My current idea is to have a separate process that approves each of the merge requests created by the bot. Is there an easy way to do this programmatically? That is, is there an API (or better yet, a command line tool) that, when given the name of the branch for a merge request, approves the merge request associated with that branch?
    * I'm also open to other ways of getting these changes in with minimal human intervention. I do want them to pass the CI pipeline, though (which is currently accomplished by having them use MRs) and the MRs also help in the rare cases where the pipeline fails, so we can debug what went wrong.

#### Marge GitLab bot
* [Marge-bot: A merge-bot for GitLab](https://github.com/smarkets/marge-bot)
* [Example: gitlab.gnome.org/marge-merge-bot](https://gitlab.gnome.org/marge-merge-bot)
* [Example: Smarkets's Marge-bot for GitLab keeps master always green](https://smarketshq.com/marge-bot-for-gitlab-keeps-master-always-green-6070e9d248df)
* [Example: GStreamer Merge Bot](https://gitlab.freedesktop.org/gstreamer-merge-bot)

### Jenkins-X bots
* [Jenkins-X UpdateBOT](https://github.com/jenkins-x/updatebot) A simple bot for updating dependencies in source code and automatically generating Pull Requests in downstream projects.

### Plastic SCM bot
* [Plastic SCM](https://www.plasticscm.com/)
* [blog.plasticscm.com: Add a mergebot to your repo!](http://blog.plasticscm.com/2018/09/add-mergebot-to-your-repo.html)
* [Plastic SCM DevOps Mergebot to implement a trunk-based development cycle ](https://github.com/PlasticSCM/trunk-mergebot)
* [PlasticSCM MergeBot Jenkins Plugin](https://wiki.jenkins.io/display/JENKINS/PlasticSCM+MergeBot+plugin)
* [genbeta.com: Plastic SCM Mergebot: automatizando tu pipeline de desarrollo](https://www.genbeta.com/desarrollo/plastic-scm-mergebot-automatizando-tu-pipeline-desarrollo)

### Mergify bot
* [mergify.io](https://mergify.io/)  
* [medium: Merging Bots’ Pull Requests Automatically](https://medium.com/mergify/merging-bots-pull-requests-automatically-548ed0b4a424)

### GitHub bots
* [github-rebase-bot](https://github.com/nicolai86/github-rebase-bot) A github bot that monitors repository PRs, rebases them and merges them as they pass tests.
* [Bulldozer: GitHub Pull Request Auto-Merge Bot](https://github.com/palantir/bulldozer) 
* [github-merge-bot](https://github.com/depop/github-merge-bot) Automates the process of merging pull requests and keeping them up-to-date.
* [github.com/squalrus/merge-bot: PR Merge Bot](https://github.com/squalrus/merge-bot) A GitHub action that manages pull request integrations
* [Odoo Mergebot](https://github.com/odoo/odoo/wiki/Mergebot)
* [gmaster.io - Mergedroid: Automate merging just by analyzing your GitHub repo.](https://gmaster.io/mergedroid) A BOT that solves conflicts in pull requests without manual intervention.
* [Kodiak](https://kodiakhq.com/) GitHub bot for updating and merging pull requests
* [Rultor](http://www.rultor.com/) A merging bot for Github pull requests
    * [Rultor, a Merging Bot](https://www.yegor256.com/2014/07/24/rultor-automated-merging.html)
* [stackoverflow.com: Bot to automatically reverse GitHub pull request merges](https://stackoverflow.com/questions/27820309/bot-to-automatically-reverse-github-pull-request-merges). Maybe it's best to not allow the merges instead of reverting them:
    * [help.github.com: Configuring protected branches](https://help.github.com/en/github/administering-a-repository/configuring-protected-branches)
    * [help.github.com: Enabling required status checks:](https://help.github.com/en/github/administering-a-repository/enabling-required-status-checks)
        * Select Require status checks to pass before merging 
        * Choose (create) a status check, that always fails

#### Bors GitHub bot
* [Bors Bot](https://bors.tech/)
* [Bors - Readme](https://bors.tech/devdocs/bors-ng/readme.html)
* [Bors-ng: A merge bot for GitHub Pull Requests](https://github.com/bors-ng/bors-ng)
* [Example: CockroachDB's Bors Merge Bot](https://wiki.crdb.io/wiki/spaces/CRDB/pages/73204099/Bors+Merge+Bot)

---
<center>
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Today&#39;s <a href="https://twitter.com/code?ref_src=twsrc%5Etfw">@code</a> tip: the git stash commands<br><br>Create, apply, and manage <a href="https://twitter.com/hashtag/git?src=hash&amp;ref_src=twsrc%5Etfw">#git</a> stashes using VS Code commands.<br><br>Stashes let you quickly save off your workspace changes and restore them when they are needed again<a href="https://twitter.com/hashtag/code2020?src=hash&amp;ref_src=twsrc%5Etfw">#code2020</a> <a href="https://t.co/VPursGdRka">pic.twitter.com/VPursGdRka</a></p>&mdash; Matt Bierner (@mattbierner) <a href="https://twitter.com/mattbierner/status/1276915695788470273?ref_src=twsrc%5Etfw">June 27, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Writing good Git commit messages matters!<br><br>A thread about how to write clean commit messages:<br><br>🧵 👇</p>&mdash; Deni Moka⚡ (@dmokafa) <a href="https://twitter.com/dmokafa/status/1351152452179996682?ref_src=twsrc%5Etfw">January 18, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</center>
