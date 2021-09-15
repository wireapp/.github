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

