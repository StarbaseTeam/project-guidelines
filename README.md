[<img src="./images/elsewhen-logo.png" width="180" height="180">](https://www.elsewhen.com/)

# Project Guidelines

<hr>

- [Understanding Requirements and Tech Analysis](#understanding-requirements)
- [Task Organization in Jira: Creation and Estimation](#task-organization)
- [Git](#git)
  - [Some Git rules](#some-git-rules)
  - [Git workflow](#git-workflow)
  - [Writing good commit messages](#writing-good-commit-messages)
- [Documentation](#documentation)
- [Environments](#environments)
    - [Consistent dev environments](#consistent-dev-environments)
    - [Consistent dependencies](#consistent-dependencies)
- [Dependencies](#dependencies)
- [Testing](#testing)
- [Structure and Naming](#structure-and-naming)
- [Code style](#code-style)
    - [Some code style guidelines](#code-style-check)
    - [Enforcing code style standards](#enforcing-code-style-standards)
- [Logging](#logging)
- [API](#api)
    - [API design](#api-design)
    - [API security](#api-security)
    - [API documentation](#api-documentation)
- [Accessibility](#a11y)
- [Licensing](#licensing)

<hr>

<a name="understanding-requirements"></a>

## 1. Understanding Requirements and Tech Analysis

![Understanding Requirements](/images/branching.png)

This phase is the cornerstone of any successful project. Our goal is to deeply understand the client's needs and identify the key tasks that need to be addressed. We actively engage with stakeholders to gather all necessary requirements and clarify expectations. Based on the gathered information, we conduct a detailed analysis of tasks and technologies that we plan to use. This allows us to avoid potential misunderstandings, ensure technical compatibility, and successfully achieve the set goals.

<hr>

<a name="task-organization"></a>

## 2. Task Organization in Jira: Creation and Estimation

![Understanding Requirements](/images/branching.png)

At this stage, we move on to the detailed organization of the project in Jira. The created task board serves as our primary management tool. Each task is clearly defined and assigned a specific goal. By evaluating each task, we develop a detailed work plan, optimize resource allocation, and mitigate risks.

Depending on the specifics of the project, we apply various project management methodologies:

* Waterfall: A sequential approach, ideal for projects with well-defined requirements.
* Agile: A flexible methodology that allows for adaptation to changes throughout the development process.
* Kanban: A visual method that helps optimize workflows and ensure even team loading.
* Scrum: An iterative approach with short development cycles (sprints), providing high flexibility and adaptability.

By choosing the most suitable methodology, we ensure effective project management, process transparency, and timely achievement of our goals.

<hr>

<a name="git"></a>

## 3. Git

![Understanding Requirements](/images/branching.png)


<a name="some-git-rules"></a>

### 3.1 Some Git rules

There are a set of rules to keep in mind:

- **Perform work in a feature branch.**

  > This approach ensures that all work is performed in isolation on a dedicated branch rather than the main branch. It allows you to submit multiple pull requests without causing confusion and enables you to iterate without contaminating the master branch with potentially unstable or incomplete code. [read more...](https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow)

- **Branch out from `develop`** 
 
    > This ensures that the code in the master branch is consistently buildable and mostly release-ready, though this might be excessive for smaller projects.

- **Never push into `develop` or `master` branch. Make a Pull Request.**

  > It informs the team of a feature's completion, enables peer review, and offers a designated area for discussing the feature.

- **Always update your local `develop` branch to the latest version and do an interactive rebase before submitting a Pull Request.**

  > Rebasing will merge the requested branch (`develop` or `master`) into your local branch and apply your local commits to the top of the history without creating a merge commit (assuming there are no conflicts). This results in a clean and linear history. [read more ...](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

- **Resolve potential conflicts while rebasing and before making a Pull Request.**
- **Delete local and remote feature branches after merging.**
- **Use [this](./.gitignore) `.gitignore` file.**

  > It includes a predefined list of system files that should be excluded from remote repositories. Additionally, it excludes settings folders and files for popular editors and common dependency folders.

<a name="git-workflow"></a>

### 3.2 Git workflow

We use [Feature-branch-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow) with [Interactive Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing) and some elements of [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow) (naming and having a develop branch). The main steps are as follows:

<a name="writing-good-commit-messages"></a>

### 3.3 Writing good commit messages

A clear commit guideline can significantly improve your Git workflow and collaboration with others. Here are some rules of thumb ([source](https://chris.beams.io/posts/git-commit/#seven-rules)):

- **Keep subject lines under 50 characters and wrap the body text at 72 characters.**

  > Commits should be granular and focused, with concise descriptions.

- **Do not end the subject line with a period.**
- **Use the body to explain _what_ and _why_ as opposed to _how_.**