# <a name="contributing">Contributing Overview</a>
Please do! Thanks for your help improving the project! 🎈

All contributors are welcome. Please see the [newcomers welcome guide](https://layer5.io/community/newcomers) for how, where and why to contribute. This project is community-built and welcomes collaboration. Contributors are expected to adhere to our [Code of Conduct](CODE_OF_CONDUCT.md).

Not sure where to start? First, see the [newcomers welcome guide](https://layer5.io/community/newcomers). Grab an open issue with the [help-wanted label](../../labels/help%20wanted) and jump in. Join the [Slack account](http://slack.layer5.io) and engage in conversation. Create a [new issue](/../../issues/new/choose) if needed.  All [pull requests](/../../pulls) should reference an open [issue](/../../issues). Include keywords in your pull request descriptions, as well as commit messages, to [automatically close issues in GitHub](https://help.github.com/en/github/managing-your-work-on-github/closing-issues-using-keywords).

**Sections**
- <a name="contributing">General Contribution Flow</a>
  - <a href="#prerequisites">Prerequisites</a>
  - <a href="#set-up-your-local-development-environment">Set up your Local Development Environment</a>
  - <a href="#commit-signing">Developer Certificate of Origin</a>

Relevant coding style guidelines are the Go Code Review Comments and the Formatting and style section of Peter Bourgon's Go: Best Practices for Production Environments.

# <a name="contributing">General Contribution Flow</a>

In order to contribute to Layer5 docs, please follow the fork-and-pull request workflow described [here](./CONTRIBUTING-gitflow.md).

## Prerequisites

Make sure you have the following prerequisites installed on your operating system before you start contributing:

- [Nodejs and npm](https://nodejs.org/en/)

  To verify run:

  ```
  node -v
  ```

  ```
  npm -v
  ```

- [Go](https://go.dev/doc/install)

  To verify run:

  ```
  go version
  ```

- [Hugo](https://gohugo.io/installation/) 


  - Install a recent release of the Hugo "extended" version. If you install from
    the [Hugo release page](https://github.com/gohugoio/hugo/releases), make sure
    you download the `extended` version, which supports SCSS.

    To verify run:

    ```
    hugo version
    ```

  - Install `PostCSS` so that the site build can create the final CSS assets. You
    can install it locally by running the following commands from the root
    directory of your project:

    ```sh
    npm install --save-dev autoprefixer
    npm install --save-dev postcss-cli
    ```

    Starting in
    [version 8 of `postcss-cli`](https://github.com/postcss/postcss-cli/blob/master/CHANGELOG.md),
    you must also separately install `postcss`:

    ```sh
    npm install -D postcss
    ```

**Note:** If you're on a _Windows environment_ then it is highly recommended that you install [Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/en-us/windows/wsl/install) both for performance and ease of use.


## Set up your Local Development Environment

Follow the following instructions to start contributing.

**1.** Fork [this](https://github.com/layer5io/exoscale-academy) repository.

**2.** Clone your forked copy of the project.

```
git clone --depth=1 https://github.com/<your-username>/exoscale-academy.git
```

**3.** Navigate to the project directory.

```
cd exoscale-academy
```

**4.** Add a reference(remote) to the original repository.

```
git remote add upstream https://github.com/layer5io/exoscale-academy.git
```

**5.** Check the remotes for this repository.

```
git remote -v
```

**6.** Always take a pull from the upstream repository to your master branch to keep it at par with the main project (updated repository).

```
git pull upstream master
```

**7.** Create a new branch.

```
git checkout -b <your_branch_name>
```

**8.** Install the dependencies for running the site.

```
make setup
```

**9.** Make the desired changes.

**10.** Run the site locally to preview changes.

```
make site
```

This will run a local webserver with "live reload" conveniently enabled. ( **NOTE**: while using the make command on Windows, there sometimes arises an error in identifying the command even after it is installed (unrecognized command), this is because the PATH for the binary might not be set correctly ).

**11.** Track your changes.

```
git add .
```

**12.** Commit your changes. To contribute to this project, you must agree to the [Developer Certificate of Origin (DCO)](#signing-off-on-commits) for each commit you make.

```
git commit --signoff -m "<commit subject>"
```

or you could go with the shorter format for the same, as shown below.

```
git commit -s -m "<commit subject>"
```

**13.** While you are working on your branch, other developers may update the `master` branch with their branch. This action means your branch is now out of date with the `master` branch and missing content. So to fetch the new changes, follow along:

```
git checkout master
git fetch origin master
git merge upstream/master
git push origin
```

Now you need to merge the `master` branch into your branch. This can be done in the following way:

```
git checkout <your_branch_name>
git merge master
```

**14.** Push the committed changes in your feature branch to your remote repo.

```
git push -u origin <your_branch_name>
```

**15.** Once you’ve committed and pushed all of your changes to GitHub, go to the page for your fork on GitHub, select your development branch, and click the pull request button. Please ensure that you compare your feature branch to the desired branch of the repo you are supposed to make a PR to. If you need to make any adjustments to your pull request, just push the updates to GitHub. Your pull request will automatically track the changes in your development branch and update it.

## <a name="commit-signing">Signing-off on Commits (Developer Certificate of Origin)</a>

To contribute to this project, you must agree to the Developer Certificate of
Origin (DCO) for each commit you make. The DCO is a simple statement that you,
as a contributor, have the legal right to make the contribution.

See the [DCO](https://developercertificate.org) file for the full text of what you must agree to
and how it works [here](https://github.com/probot/dco#how-it-works).
To signify that you agree to the DCO for contributions, you simply add a line to each of your
git commit messages:

```
Signed-off-by: Jane Smith <jane.smith@example.com>
```

In most cases, you can add this signoff to your commit automatically with the
`-s` or `--signoff` flag to `git commit`. You must use your real name and a reachable email
address (sorry, no pseudonyms or anonymous contributions). An example of signing off on a commit:
```
$ commit -s -m “my commit message w/signoff”
```

To ensure all your commits are signed, you may choose to add this alias to your global ```.gitconfig```:

*~/.gitconfig*
```
[alias]
  amend = commit -s --amend
  cm = commit -s -m
  commit = commit -s
```
Or you may configure your IDE, for example, Visual Studio Code to automatically sign-off commits for you:

<a href="https://user-images.githubusercontent.com/7570704/64490167-98906400-d25a-11e9-8b8a-5f465b854d49.png" ><img src="https://user-images.githubusercontent.com/7570704/64490167-98906400-d25a-11e9-8b8a-5f465b854d49.png" width="50%"><a>

## <a name="contributing-docs">Documentation Contribution Flow</a>
Please contribute! Layer5 documentation uses Jekyll and GitHub Pages to host docs sites. Learn more about [Layer5's documentation framework](https://docs.google.com/document/d/17guuaxb0xsfutBCzyj2CT6OZiFnMu9w4PzoILXhRXSo/edit?usp=sharing). The process of contributing follows this flow:

1. Create a fork, if you have not already, by following the steps described [here](./CONTRIBUTING-gitflow.md)
1. In the local copy of your fork, navigate to the docs folder.
`cd docs`
1. Create and checkout a new branch to make changes within
`git checkout -b <my-changes>`
1. Edit/add documentation.
`vi <specific page>.md`
1. Run site locally to preview changes.
`make site`
1. Commit, [sign-off](#commit-signing), and push changes to your remote branch.
`git push origin <my-changes>`
1. Open a pull request (in your web browser) against the repo.


#### Tests
Users can now test their code on their local machine against the CI checks implemented using `make run-tests`.

To test code changes on your local machine, run the following command:
```
make run-tests
```

#### Building Docker image
To build a Docker image of the project, please ensure you have `Docker` installed to be able to build the image. Now, run the following command to build and serve the files locally.:

> [!IMPORTANT]  
> This requires Docker Desktop version **4.24** or later, or Docker Engine with Docker
> Compose version [**2.22**](https://docs.docker.com/compose/file-watch/) or later.
```sh
make docker
```

### UI Lint Rules

Layer5 uses ES-Lint to maintain code quality & consistency in our UI Code.

# <a name="maintaining"> Reviews</a>
All contributors are invited to review pull requests. See this short video on [how to review a pull request](https://www.youtube.com/watch?v=isLfo7jfE6g&feature=youtu.be).

# New to Git?
Resources: https://lab.github.com and https://try.github.com/

### License

This repository and site are available as open source under the terms of the [Apache 2.0 License](https://opensource.org/licenses/Apache-2.0).

### About Layer5

**Community First**
<p>The <a href="https://layer5.io/community">Layer5 community</a> represents the largest collection of service mesh projects and their maintainers in the world.</p>

**Open Source First**
<p>At Layer5, we champion developer-defined infrastructure, giving engineers the power to reshape application delivery. We empower operators in reimagining how they manage modern infrastructure: collaboratively.</p>