# git cub

## create and checkout branch by user.login name

Git alias:

```git
cub = "!f() { git checkout -b $(git config user.login)/$1 $2; }; f"
```

Creates and checkout a branch named <user.login>/<branchname>

Example:

```shell
git cub <branchname>
```
