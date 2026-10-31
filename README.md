![Banner](banner.png)

# misconfig-ConfigBaselineComparator
Compares the current configuration against a known good baseline (e.g., from a golden image or approved template), flagging deviations. Uses `diff` and `pyyaml` or `json` for formatted output. - Focused on Check for misconfigurations in configuration files or infrastructure definitions

## Install
`git clone https://github.com/ShadowGuardAI/misconfig-configbaselinecomparator`

## Usage
`./misconfig-configbaselinecomparator [params]`

## Parameters
- `-h`: Show help message and exit
- `-o`: Output format, `diff` or `json`. Defaults to `diff`.

## Exit codes and errors
- Exit 0: the two configurations are the same.
- Exit 1: the configurations differ, or the comparison did not happen. A missing file, a path that is not a file, a parse failure, a lint failure, and an empty input file all exit 1 with an error line. They are never reported as "No differences found".
- An empty configuration file holds nothing to compare, so it is an error at exit 1, including when both inputs are empty.
- If the optional `yamllint` or `jsonlint` binary is not installed, the warning names that binary and linting is skipped. That skip is the only non-critical path.

## License
Copyright (c) ShadowGuardAI
