# clang-tidy-diff-hook
A [pre-commit](https://pre-commit.com/) hook for clang-tidy.

It does `git diff [origin/main | PRE_COMMIT_FROM_REF] -U0 --no-prefix | clang-tidy-diff -quiet -fix -path build`.

## Usage

```yaml
-   repo: https://github.com/ksh1102/clang-tidy-diff-hook
    rev: v0.1.0
    hooks:
    -   id: clang-tidy-diff
        args: ['-clang-tidy-binary', 'clang-tidy-14', '-path', 'build']
    # Do whenever to add headers to build/compile_commands.json
    -   id: add-headers
        # path to directory containing compile_commands
        args: ['-path', 'build']
        stages: [manual]
```
