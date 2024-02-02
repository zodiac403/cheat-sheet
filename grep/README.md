# Grep

A custom cheat sheet for `grep`? Well, just the commands I look up too often.

## Find in files

Find in files, but exclude node modules.

```sh
grep -r --exclude-dir node_modules foobar .
```

Flags:

- `-r`, `-R`, `--recursive`
- `--exclude-dir pattern` accepts a pattern to exclude

