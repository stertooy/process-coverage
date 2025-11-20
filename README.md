# process-coverage

This GitHub action prepares coverage data for GAP packages for upload
to [Codecov](https://www.codecov.io/).

Note that this does not perform the actual upload. For that we recommend using
the [`codecov/codecov-action`](https://github.com/codecov/codecov-action) action.

## Usage

The action `process-coverage` has to be called by the workflow of a GAP
package.
By default it processes the coverage data gathered during the action
[gap-actions/run-test-for-packages](https://github.com/gap-actions/run-pkg-tests).

### What's new in v3

This action now requires `gap-actions/setup-gap@v3`.

### Example

The following is a minimal example to run this action.

```yaml
name: CI

on:
  push:
  pull_request:

jobs:
  # The CI test job
  test:
    name: CI test
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v5
      - uses: gap-actions/setup-gap@v3
      - uses: gap-actions/build-pkg@v2
      - uses: gap-actions/run-pkg-tests@v4
      - uses: gap-actions/process-coverage@v3
      - uses: codecov/codecov-action@v5
```

## Contact
Please submit bug reports, suggestions for improvements and patches via
the [issue tracker](https://github.com/gap-actions/process-coverage/issues).

## License
The action `process-coverage` is free software; you can redistribute
and/or modify it under the terms of the GNU General Public License as published
by the Free Software Foundation; either version 2 of the License, or (at your
opinion) any later version. For details, see the file `LICENSE` distributed
with this action or the FSF's own site.
