# nix-command-patterns

### Search and replace
```
grep -rl components2 . | grep .js$ | xargs sed -i '' 's/components2/components/g'
```
- grep, (r) recursive, (l) pathname only
- grep only .js files
- xargs to enumerate input
- sed to edit file in place

### Find by file extension
```
find . -name "*.js"
```
- recursive
```
ls . | grep .js
```
- non-recursive

### Interpolate template file
```
// tempalte.txt
${FIRST_NAME} ${LAST_NAME}
...

sed -e "s/\${FIRST_NAME}/tasty/g" \
    -e "s/\${LAST_NAME}/wheat/g" \
    template.txt > DESTINATION_FILE
```

### Inject line into file below target
```
// somefile.txt

/* START_HERE */

...

sed -i '' '/START_HERE/a\
    import _ from 'lodash';\
    ' somefile.txt
```
### Lowercase an uppercase letter with perl
```
echo "fooBar" | perl -pe 's/([A-Z])/\l$1/g'
```
### List files with tr and cut
```
ls -l | tr -s ' ' | cut -d ' ' -f 9
```
- tr will squash spaces
- cut to split on space, and select column 9
