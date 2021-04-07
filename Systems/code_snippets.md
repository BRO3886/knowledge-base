# Code Snippets
Random Bash scripts or smth

## Table of Contents
- [Code Snippets](#code-snippets)
  - [Table of Contents](#table-of-contents)
  - [Get git loc stats for user](#get-git-loc-stats-for-user)

## Get git loc stats for user
```bash
authstat(){
  git log --shortstat --author="$1" | grep -E "fil(e|es) changed" | awk '{files+=$1; inserted+=$4; deleted+=$6} END {print "files changed: ", files, "lines inserted: ", inserted, "lines deleted: ", deleted }'
}
```

```bash
authstat BRO3886
> files changed:  135 lines inserted:  708 lines deleted:  160
```
