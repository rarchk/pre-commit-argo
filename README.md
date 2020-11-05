# A pre-commit hook for argo workflows lint

This is the Argo lint ([argo lint](https://angular.io/cli/lint)) hook for [pre-commit](https://pre-commit.com). This hook will prevent git commits if argo lint does not pass.

## Usage

- Install pre-commit (see links below).
- Create a pre-commit config file (`.pre-commit-config.yaml`).
- Run `pre-commit install` from the root of your project.

Finally add this to your `.pre-commit-config.yaml`:

```yaml
    -   repo: git://github.com/rarchk/pre-commit-argo/
        sha: ''  # Use the sha or tag (e.g. 'stable') you want to point at
        hooks:
        -   id: argo-lint
```

When making a commit, the hook will run `argo lint` on the staged files and if errors or warnings are raised, the commit will be blocked.

## Caveats

If `args` are provided in the pre-commit configuration, the final element must be '--' in order to distinguish between `ng lint` options and the filenames to be linted.


## Copyright and License Information

Copyright (c) 2020 Ronak Kogta, and individual contributors. All rights reserved.

See the file "LICENSE" for information on the history of this software, terms & conditions for usage, and a DISCLAIMER OF ALL WARRANTIES.
