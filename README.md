# .github
Github Organisation Workflows

## Generate Changelog Workflow

This workflow will automaticaly attach a changelog to a Github release whenever a new [Semantic Versioning](https://semver.org) tag starting with `v` is created in a repository.

### Usage 

The changelog is built from [Semantic Commit Messages](https://sparkbox.com/foundry/semantic_commit_messages).
Therefore, your commit messages have to be in this format:

```
type(category): description [flags]
```

Where type is one of the following:

- `breaking`
- `build`
- `ci`
- `chore`
- `docs`
- `feat`
- `fix`
- `other`
- `perf`
- `refactor`
- `revert`
- `style`
- `test`

Where flags is an optional comma-separated list of one or more of the following (must be surrounded in square brackets):

- `breaking`: alters `type` to be a breaking change

And category can be anything of your choice. If you use a type not found in the list (but it still follows the same format of the message), it'll be grouped under other.

E.g.:

`feat(messaging): Add support for sending images [breaking]`


### Set up

To add this action click on `Actions` in the top bar of the target repository, scroll to `Workflows created by Wire Swiss GmbH` and click `Set up this workflow`.

## Label Pull Request Workflow

This workflow will automaticaly add labels to a pull reques based on it's title. Therefore the title must follow [Semantic Commit Messages](https://sparkbox.com/foundry/semantic_commit_messages).

### Set up

#### Step 1

Add this action but clicking on `Actions` in the top bar of the target repository, scroll to `Workflows created by Wire Swiss GmbH` and click `Set up this workflow`.

### Step 2

In the `.github` folder in your repo, create a file called `labeler.yml` like the following:

```yml
# Types. This are lables such as `type: feature` 
'type: refactoring 🛠':
  title: '^refactor(\(.+\))?:.*'
'type: bug / fix 🐞':
  title: '^(run)?fix(\(.+\))?:.*'
'type: chore 🧹':
  title: '^chore(\(.+\))?:.*'
'type: documentation 📋':
  title: '^docs(\(.+\))?:.*'
'type: feature / request ✨':
  title: '^feat(\(.+\))?:.*'
'type: test 👷':
  title: '^test(\(.+\))?:.*'

# Sizes. Based on the amount of line changed
'👕 size: XS':
  size-below: 10
'👕 size: S':
  size-above: 9
  size-below: 100
'👕 size: M':
  size-above: 99
  size-below: 300
'👕 size: L':
  size-above: 299
  size-below: 500
'👕 size: XL':
  size-above: 499
  size-below: 1000
'👕 size: XXL':
  size-above: 999

# Components. Depens on the files that are changed.
'comp: FooBar':
  files:
    - 'bin/foobar/.*'
'comp: Readme':
  files:
   - 'README.md'
```

### Step 3

Add Otto-the-bot as "triage" to the target repository, make sure someone in the Web Chapter accepts the request.
Otto's github token, shared as organization secret, also needs to be made available to the target repo.





