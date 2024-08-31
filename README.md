[<img src="./images/company-logo.jpeg" width="180" height="180">](https://www.starbase.agency/)
# Project Guidelines

- [Understanding Requirements and Tech Analysis](#understanding-requirements)
- [Task Organization in Jira: Creation and Estimation](#task-organization)
- [Git](#git)
  - [Some Git rules](#some-git-rules)
  - [Git workflow](#git-workflow)
  - [Writing good commit messages](#writing-good-commit-messages)
- [Coding Standards](#coding-standards)
  - [HTML](#html)
  - [JavaScript](#javascript)
  - [CSS & SCSS](#css-scss)
  - [PHP](#php)
  - [WordPress](#wordpress)
  - [File naming](#file-naming)

<a name="understanding-requirements"></a>

## 1. Understanding Requirements and Tech Analysis

![Understanding Requirements](/images/branching.png)

This phase is the cornerstone of any successful project. Our goal is to deeply understand the client's needs and identify the key tasks that need to be addressed. We actively engage with stakeholders to gather all necessary requirements and clarify expectations. Based on the gathered information, we conduct a detailed analysis of tasks and technologies that we plan to use. This allows us to avoid potential misunderstandings, ensure technical compatibility, and successfully achieve the set goals.

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

<a name="coding-standards"></a>

## 4. Coding Standards
![Understanding Requirements](/images/branching.png)

Files **SHOULD** be indented with spaces, **NOT** tabs.

Files **MUST NOT** mix tabs and spaces.

Files **SHOULD** use UTF-8 encoding.

Files **SHOULD** use Unix (LF) line endings. (Windows developers, set [`git config --global core.autocrlf true`](https://help.github.com/articles/dealing-with-line-endings/#platform-windows))

Files **MUST** end with a newline. ([ref](https://stackoverflow.com/a/729795))

Trailing whitespace **SHOULD** be removed. (exceptions: Markdown, YAML)

Lines more than 80 characters long **SHOULD** be avoided. ([js][crockford80], [php][php80])

Modern tooling makes it easy to deliver clean, appropriately formatted code. Please consider using IOP’s [`.editorconfig`][editorconfig] file as a starting point, most of the coding rules in this document are included in that file.

IOP **RECOMMENDS** the use of linting and code-quality tools like [eslint][].

<a name="html"></a>

## HTML

HTML files **MUST** start with the [HTML 5 doctype][html5]: `<!DOCTYPE html>`

HTML files **MUST** include the [IE Compatibility meta tag][x-ua] as the first meta tag in the `<head>` section, before any conditional comments. References: [1](http://stackoverflow.com/questions/6156639/x-ua-compatible-is-set-to-ie-edge-but-it-still-doesnt-stop-compatibility-mode/9624500#9624500), [2](https://github.com/h5bp/html5-boilerplate/issues/378)

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

HTML files **SHOULD** be formatted consistently with two-space (soft) indents.

Deliverable HTML files **MUST** use the full `.html` file extension, not `.htm`.

All asset references **MUST** be case-sensitive.

**OPTIONALLY** adhere to [Code Guide][codeguide-html]'s HTML recommendations.


**OPTIONALLY** format HTML files with [Prettier][].


Image tags **MUST** include alt-text attributes.

<a name="javascript"></a>

## JavaScript

JavaScript source code **SHOULD** be formatted with [Prettier][].

JavaScript source code using ES2015+ syntax **SHOULD** be transpiled with [Babel][] for distribution.

JavaScript code **SHOULD** run in [strict mode][], production code **SHOULD NOT** display errors, warnings or messages in the console.

**OPTIONALLY** use [JSDoc][] compatible doc blocks.

<a name="css-scss"></a>

## CSS & SCSS

IOP **RECOMMENDS** authoring stylesheets with the [Sass][] CSS preprocessor.

Stylesheet source files **SHOULD** follow the [GitHub CSS coding style guide][github-css].

Stylesheet source files **SHOULD** be indented using two-space indents.

**OPTIONALLY** use our [CSScomb][] dotfile.

**OPTIONALLY** adhere to [Code Guide][codeguide-html]'s CSS recommendations or [Idiomatic CSS][].

<a name="php"></a>

## PHP

PHP code **SHOULD** adhere to [PSR-1][] and [PSR-2][] style guidelines. WordPress projects **MAY** choose to use  [WordPress coding standards][wpcode] instead.

PHP files **SHOULD** be indented using four-space indents. ([PSR-2][])

PHP code **SHOULD** be developed with [`error_reporting`][error_reporting] set to `E_ALL` and **SHOULD NOT** display any errors or warnings. IOP **RECOMMENDS** using [Xdebug][] for additional backtraces.

<a name="wordpress"></a>

## WordPress

A theme's `styles.css` file **MUST** be based on [IOP's boilerplate metadata block][wp-boilerplate].

Theme directories **MUST** be prefixed with `iop-`. E.g. `iop-client-theme`.

Namespaced PHP files **SHOULD** use the `starbase` namespace.

WordPress development servers **SHOULD** enable [`WP_DEBUG`][wp_debug], `WP_DEBUG_LOG` and `WP_DEBUG_DISPLAY`.

<a name="file-naming"></a>

## File naming

IOP **RECOMMENDS** descriptive, self-documenting filenames.

Filenames **SHOULD** be cased logically and consistently. (eg. `file1.jpg` & `file2.jpg`; not `File1.JPG` & `FILE2.jpg`)

Filenames containing multiple words **SHOULD** be joined with [dashes (hyphens), not underscores][-_].

Image files **SHOULD** be descriptively named. (eg. `empire-state-building.jpg` not `bldg-1.jpg`)



[semver]: https://semver.org
[0.1.0]: https://semver.org/#faq

[editorconfig]: https://github.com/StarbaseTeam/project-guidelines/blob/main/editorconfig.txt
[2119]: http://www.ietf.org/rfc/rfc2119.txt

[babel]: http://babeljs.io
[prettier]: https://github.com/prettier/prettier
[airbnb5]: https://github.com/airbnb/javascript/tree/master/es5
[airbnb6]: https://github.com/airbnb/javascript
[strict mode]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode/Transitioning_to_strict_mode
[jsdoc]: http://usejsdoc.org/about-getting-started.html

[github-css]: http://primercss.io/guidelines/#scss
[psr-1]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md
[psr-2]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[wpcode]: https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/
[codeguide-html]: http://codeguide.co/#html
[codeguide-css]: http://codeguide.co/#css
[html5]: http://www.w3.org/TR/html5/syntax.html#the-doctype
[Idiomatic CSS]: https://github.com/necolas/idiomatic-css
[sass]: http://sass-lang.com/
[csscomb]: http://csscomb.com/

[ogp]: http://opengraphprotocol.org/
[twitter cards]: https://dev.twitter.com/cards/overview
[seo framework]: https://theseoframework.com/

[error_reporting]: http://php.net/manual/en/function.error-reporting.php
[xdebug]: https://xdebug.org/
[wp_debug]: https://codex.wordpress.org/WP_DEBUG

[isobar]: http://isobar-idev.github.io/code-standards/#css_css_best_practices
[tmw]: http://tech.tmw.co.uk/code/TMW-frontend-guidelines
[Code Guide]: http://codeguide.co/

[crockford80]: http://javascript.crockford.com/code.html#line%20length
[php80]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md#user-content-1-overview
[pep8]: http://legacy.python.org/dev/peps/pep-0008/#maximum-line-length

[eslint]: http://eslint.org
[phpcs]: http://www.squizlabs.com/php-codesniffer

[-_]: https://www.mattcutts.com/blog/dashes-vs-underscores/
[x-ua]: http://stackoverflow.com/a/6771584/503463

[google analytics]: https://support.google.com/analytics/answer/1008080?hl=en
