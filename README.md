# Liberator

> The official tool you'll use to publish the work you've done (during sprints) at Hack Reactor.

## Table of Contents

- [Overview](#overview)
- [Guidelines](#guidelines)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
  - [All At Once](#all-at-once)
  - [One by One](#one-by-one)
    - [Single Repo](#single-repo)
    - [Multiple Repos](#multiple-repos)
  - [Eligible Repos](#eligible-repos)

## Overview

Liberator publishes your Hack Reactor sprint repositories, doing the following in the process:
- Fixes your repositories' git history so that you get full credit for all commits made by the `hackreactor-students` account on a Hack Reactor workstations (This fills in your GitHub commit history in the process.)
- Adds a basic readme explaining to the world what this repository is.
  - NOTE: This will delete any existing readme.md file in the repo.
- Deletes your old, private repository.
- Publishes your private sprint repository as a public repository.
- Deletes all branches except 'master'
  - You probably don't want a potential employer comparing your code with a branch on your repo labeled 'solution' :D

## HOTFIX

Due to some recent changes in the way the GitHub API authorizes requests, we've needed to change the way liberator works. To allow you to continue liberating repos, we've changed the type of information that liberator asks for. Instead of asking for your GitHub password, liberator now asks you to create a GitHub Personal Access Token and input that information instead. A guide to how to create one of these tokens can be found [here](https://help.github.com/articles/creating-an-access-token-for-command-line-use/). In addition to repo access, you'll want to grant this token the privilege to `delete_repo`. Once you've generated the token, you'll want to paste it into the prompt when liberator asks you to. Everything else should work as expected.

## Guidelines

- **DO** publish any repository you did any work on, even if it's incomplete or
  sloppy by your current high standards. Employers will see these repositories
  will care about one thing: that you've been writing code for three solid
  months.
- **DO NOT** publish any curriculum outside of (or otherwise circumvent)
  Liberator. Hack Reactor's curriculum represents thousands of hours of work put in by many different individuals, and not all of it is public domain.
  (Curriculum does not, of course, include personal projects, group projects,
  etc. Those should be public already, unless the particular constraints of your project dictated that it be private.)
- **DO** publish your repositories before graduating. You don't have to publish your sprints in 'real time' if you don't want to. You're welcome to publish them all at once during the second half of the course instead. Just know that Hack Reactor will delete your cohort's
  master curriculum repositories twelve weeks after your graduation. If you do
  not publicize your repositories before then, your work will be lost forever.

## Installation

__NOTE__: You do not need to fork this repo to install/use the liberator tool.

Run the following (you'll be prompted for you github username and password):

  ```sh
  npm install -g git+https://github.com/hackreactor/liberator.git
  ```

## Configuration

The first time you run use the tool via `liberator`, you will be prompted for your github email, github username, and github password. The tool uses these to generate an OAuth token that is saved locally and used for all subsequent requests.
  - NOTE: You must use the e-mail that you use on GitHub. It determines what is counted as _your_ commit, so make sure it is right.

## Usage

### All At Once

If you want to liberate _all_ of your eligible repositories (see below), run `liberator all`

### One By One

You can also liberate them one at a time (or a few at a time), by listing the repositories in a space-separated list after the tool:

#### Single Repo

`liberator 2014-04-databases`

#### Multiple Repos

`liberator 2014-04-chatterbox-client 2014-04-chatterbox-server` will also work

## Troubleshooting

#### Trouble installing

If `npm install -g git+https://github.com/hackreactor/liberator.git` does not work, you may have installed npm in a non-standard way. You can try to fix it by installing `n`.

__NOTE__ that installing `n` will cause anything you've already globally installed to become unavailable - you'll need reinstall them globally. Also, don't use `sudo` to install things, as it will create similar permissions problems down the line. To install `n` use:


```sh
npm install -g n
n stable
```

If this doesn't work, you'll need to ask for [halp](http://bookstrap.hackreactor.com/).

#### Trouble writing to `config.json`

You may have the wrong file permissions where you install global `node_modules`, if you receive this error message:

```sh
Error: EACCES, permission denied '/usr/local/lib/node_modules/liberator/config.json'
```

In this case, you'll need to give your node process permissions to write the configuration file by running the following command:

```sh
sudo chmod 777 /usr/local/lib/node_modules/liberator
```

You'll probably also want to follow the steps as if you'd had [trouble installing](trouble-installing) so you don't have permissions issues in the future.

#### Trouble writing to `archive`

Run:

```sh
sudo chown -R `whoami`  /usr/local/lib/node_modules/liberator/archive
```

#### Anything else

[Halp](http://bookstrap.hackreactor.com/).

## Eligible Repos

Liberator will only work on the following repos (whether run with the 'all' flag or individually):
- blackjack
- chatterbox-client
- chatterbox-server
- data-structures
- databases
- javascript-koans
- layout
- looper
- middleware
- mvp
- mytunes
- n-queens
- oath
- recursion
- shortly-angular
- shortly-deploy
- shortly-express
- solo
- subclass-dance-party
- taxonomy
- timecop
- twittler
- underbar
- watchout
- web-historian
