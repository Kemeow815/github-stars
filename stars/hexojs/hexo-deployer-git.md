---
project: hexo-deployer-git
stars: 586
description: |-
    Git deployer plugin for Hexo.
url: https://github.com/hexojs/hexo-deployer-git
---

# hexo-deployer-git

[![CI](https://github.com/hexojs/hexo-deployer-git/actions/workflows/ci.yml/badge.svg?branch=master)](https://github.com/hexojs/hexo-deployer-git/actions/workflows/ci.yml)
[![NPM version](https://badge.fury.io/js/hexo-deployer-git.svg)](https://www.npmjs.com/package/hexo-deployer-git)
[![Coverage Status](https://coveralls.io/repos/github/hexojs/hexo-deployer-git/badge.svg)](https://coveralls.io/github/hexojs/hexo-deployer-git)

Git deployer plugin for [Hexo].

## Notice: Fatal HttpRequestException Error on pushing to GitHub?

Update [Git for Windows](https://github.com/git-for-windows/git/releases) to the latest version. ([Details](https://github.com/Microsoft/Git-Credential-Manager-for-Windows#notice-experiencing-github-pushfetch-problems))

## Installation

``` bash
$ npm install hexo-deployer-git --save
```

## Options

You can configure this plugin in `_config.yml`.

``` yaml
# You can use this:
deploy:
  type: git
  repo: <repository url>
  branch: [branch]
  token: ''
  message: [message]
  name: [git user]
  email: [git email]
  extend_dirs: [extend directory]
  ignore_hidden: false # default is true
  ignore_pattern: regexp  # whatever file that matches the regexp will be ignored when deploying

# or this:
deploy:
  type: git
  message: [message]
  repo: <repository url>[,branch]
  extend_dirs:
    - [extend directory]
    - [another extend directory]
  ignore_hidden:
    public: false
    [extend directory]: true
    [another extend directory]: false
  ignore_pattern:
    [folder]: regexp  # or you could specify the ignore_pattern under a certain directory

# Multiple repositories
deploy:
  repo:
    # Either syntax is supported
    [repo_name]: <repository url>[,branch]
    [repo_name]:
      url: <repository url>
      branch: [branch]
```

- **repo**: Repository settings, or plain url of your repo
  - **url**: Url of your repositury to pull from and push to. If you've configured SSH key authentication for git, ensure you use the SSH protocol format (for example, `git@github.com:`) for your repository URL to avoid password prompts or access denial due to security policies.
  - **branch**: Optional git branch to deploy the static site to.
    - Defaults to `gh-pages` on GitHub.
    - Defaults to `coding-pages` on Coding.net.
    - Otherwise defaults to `master`.
  - **token**: Optional token value to authenticate with the repo. Prefix with `$` to read token from environment variable (recommended). Repo must be a http(s) url. [More details](#deploy-with-token).
  - **repo_name**: Unique name when deploying to multiple repositories.
    * Example:
    ``` yaml
    deploy:
      repo:
        # Either syntax is supported
        github: https://github.com/user/project.git,branch
        gitee:
          url: https://gitee.com/user/project.git
          branch: branch_name
    ```
- **branch**: Git branch to deploy the static site to. Branch name specified in `repo:` takes priority.
- **message**: Commit message. Defaults to `Site updated: {{ now("yyyy-MM-dd HH:mm:ss") }}`.
- **name** and **email**: User info for committing the change, overrides global config. This info is independent of git login.
- **extend_dirs**: Additional directories to publish. e.g `demo`, `examples`
- **ignore_hidden** (Boolean|Object): whether ignore hidden files to publish. GitHub requires the `.nojekyll` in root.
  * Boolean: for all dirs.
  * Object: for public dir and extend dir:
    * `public`: the public dir defaults.
    * [extend directory]
- **ignore_pattern** (Object|RegExp): Choose the ignore pattern when deploying
  * RegExp: for all dirs.
  * Object: specify the ignore pattern under certain directory. For example, if you want to push the source files and generated files at the same time to two different branches. The option should be like
  ```yaml
  # _config.yaml
  deploy:
    - type: git
      repo: git@github.com:<username>/<username>.github.io.git
      branch: master
    - type: git
      repo: git@github.com:<username>/<username>.github.io.git
      branch: src
      extend_dirs: /
      ignore_hidden: false
      ignore_pattern:
          public: .
  ```

### Deploy with token

While this plugin can parse authentication token from the config, only use this method if you are sure the config will not be committed, including to a private repo. A more secure approach is to add it to the CI as an environment variable, then simply add the name of the environment variable to this plugin's config (e.g. `$GITHUB_TOKEN`).

Additional guides:

- Create a GitHub Personal Access Token. [[Link]](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line)
- Add authentication token to Travis CI. [[Link]](https://docs.travis-ci.com/user/environment-variables/#defining-variables-in-repository-settings)

## Important Notice: Force Push Behavior

The `hexo-deployer-git` plugin employs a force push (`git push --force`) strategy when deploying updates to your site. This approach ensures that the remote repository aligns exactly with your local deployment, providing a clean, consistent state for each update. However, it comes with an important consideration regarding custom modifications.

### Impact of Force Push

Using force push means that any changes made directly in the remote repository (e.g., via GitHub's web interface or through a separate git workflow) will be **overwritten** when the next deployment occurs. This is because force push does not merge changes; it replaces the remote content with the local version entirely.

### How to Safely Manage Your Site

To prevent unintended loss of work, we strongly advise adhering to the following best practices:

1. **Centralize Changes in Your Hexo Source:** Make all content and configuration changes within your local Hexo root directory. This ensures all modifications are included in the deployment process and preserved in your source control.

2. **Avoid Direct Remote Modifications:** Refrain from directly editing files in the GitHub repository through the web interface or other git methods. Doing so could lead to these changes being lost on the next deployment.

## Custom Domain Issue with CNAME File

If you are using a custom domain with GitHub Pages, you might have encountered an issue where your custom domain configuration gets lost after deploying updates to your site. This problem occurs due to the overwritten / deletion of the `CNAME` file in the root of the deployed directory during the git commit and push process performed by the `hexo-deployer-git` plugin.

GitHub requires the `CNAME` file to be present in your repository to associate your custom domain with your GitHub Pages site. When this file is missing, GitHub resets the custom domain setting, leading to the site being accessible only through the default `github.io` domain.

### Solution

To ensure your custom domain remains active with each deployment, you need to include the `CNAME` file in your blog's `source/` directory. Here's how you can do it:

1. **Create a `CNAME` File:** In the root of your blog's `source/` directory, create a file named `CNAME`. Inside this file, enter your custom domain name. For example, if your custom domain is `example.com`, the content of the `CNAME` file should be:
   ```
   example.com
   ```
2. **Deploy Your Site:** Use the `hexo-deployer-git` plugin to deploy your site as usual. Run `hexo g -d` command, the plugin will now include the `CNAME` file in the deployment, and your custom domain configuration will remain intact.

## How it works

`hexo-deployer-git` works by generating the site in `.deploy_git` and *force pushing* to the repo(es) in config.
If `.deploy_git` does not exist, a repo will initialized (`git init`).
Otherwise the curent repo (with its commit history) will be used.

Users can clone the deployed repo to `.deploy_git` to keep the commit history.

```
git clone <gh-pages repo> .deploy_git
```

## Reset

Remove `.deploy_git` folder.

``` bash
$ rm -rf .deploy_git
```

## License

MIT

[Hexo]: https://hexo.io/

