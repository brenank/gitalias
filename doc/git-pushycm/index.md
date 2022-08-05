# git pushycm

## Push commit with force and lease

Git alias:

```git
pushycm = "!f() { \
    git push --force-with-lease $1:$(git rev-parse --abbrev-ref --symbolic-full-name @{u}); \
}; f"
```

Push a specific sha commit with a force and lease, which means that you're pushing in order
to forcefully overwrite the remote, and you want a safety check first:
git checks you're current with remote, and only then allows the push.

We name this `pushycm` because its disagreeably aggressive (in general)
or overly assertive (in general), yet still better than just --force.

Example:

````shell
git pushycm <rev>
```
