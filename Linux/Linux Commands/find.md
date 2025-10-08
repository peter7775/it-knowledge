### remove file by some pattern

`find . -name '*_*' -exec rm -rf {} \;`

If you only want regular files:

```
find . -type f -name '*_*' -exec rm -f {} \;
```




`find . -type f -regex ".*_.*" | xargs rm -f`

explanation
-type f finds only files
-regex ".*_.*" selects only files that have an underscore in them
xargs rm -f then removes the selected file forcefully (never prompts before deleting)
