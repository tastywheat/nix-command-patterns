# nix-command-patterns

### Search and replace
```
grep -rl baby . | xargs sed -i '' 's/baby/BABY/g'
```
### Find by file extension

Recursive
```
find . -name "*.js"
```

Non-recursive
```
ls . | grep .js
```
