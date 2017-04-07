# nix-command-patterns

### Search and replace
```
grep -rl baby . | xargs sed -i '' 's/baby/BABY/g'
```
- grep, (r) recursive, (l) pathname only
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
echo "fooBar" | perl -pe 's/([A-B])/\l$1/'
```
