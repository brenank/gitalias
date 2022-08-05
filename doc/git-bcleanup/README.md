# git bcleanup

## Prune tracking branches and delete any associated local branches

Git alias:

```git
bcleanup = "!f() { \
    git fetch -p && for branch in $(git branch -vv | grep ': gone]' | grep -v '*' | awk '{print $1}'); \
      do git branch -D $branch; \
    done; \
}; f"
```

This is a DESTRUCTIVE action, and may remove branches with local changes. Be careful running this.
Prunes existing tracking branches. For any that were gone, we remove the associate local branches as well.

Example:

````shell
git bcleanup
```
