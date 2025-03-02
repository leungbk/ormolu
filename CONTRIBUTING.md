# Contributing

Issues (bugs, feature requests or otherwise feedback) may be reported in
[the GitHub issue tracker for this project][issues]. Pull requests are also
welcome.

When contributing to this repository, please first discuss the change you
wish to make via an issue, unless it's entirely trivial (typo fixes, etc.).
If there is already an issue that describes the change you have in mind,
comment on it indicating that you're going to work on that. This way we can
avoid the situation when several people work on the same thing.

Please make sure that all non-trivial changes are described in commit
messages and PR descriptions.

## Testing

Testing has been taken good care of and now it amounts to just adding
examples under `data/examples`. Each example is a pair of files:
`<example-name>.hs` for input and `<example-name>-out.hs` for corresponding
expected output.

Testing is performed as following:

* Given snippet of source code is parsed and pretty-printed.
* The result of printing is parsed back again and the AST is compared to the
  AST obtained from the original file. They should match.
* The output of printer is checked against the expected output.
* Idempotence property is verified: formatting already formatted code
  results in exactly the same output.

Examples can be organized in sub-directories, see the existing ones for
inspiration.

Please note that we try to keep individual files at most 25 lines long
because otherwise it's hard to figure out want went wrong when a test fails.

To regenerate outputs that have changed, you can set the
`ORMOLU_REGENERATE_EXAMPLES` environment variable before running tests.

## Formatting

Use `format.sh` script to format Ormolu with the current version of Ormolu.
If Ormolu is not formatted like this, the CI will fail.

[issues]: https://github.com/tweag/ormolu/issues
