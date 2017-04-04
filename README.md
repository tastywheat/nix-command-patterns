# nix-command-patterns

## Search and replace
grep -rl baby . | xargs sed -i '' 's/baby/BABY/g'
