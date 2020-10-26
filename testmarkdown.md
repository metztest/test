# GFM Fenced Code Block Diff Lang

MarkDown supports fenced code blocks:

```
like this
```

They can be decorated with a language tag to enable syntax highlighting:

(`sh`)
```sh
echo "like this"
```

The list of languages supported can be found here:
https://github.com/github/linguist/blob/master/lib/linguist/languages.yml

One of the supported "languages" is "diff" which highlights additions and removals:

(`diff`)
```diff
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

It doesn't appear to be possible to mark a fenced code block using multiple language tags,
like using `diff` and `sh` both to make the fenced code block highlight additions and
removals but also syntax highlight.

(`diff sh`)
```diff sh
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

(`sh diff`)
```diff sh
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

(`diff,sh`)
```diff sh
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

(`sh,diff`)
```diff sh
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

Interestingly, all of these highlight as if just `diff` was passed in.

(`sh diff`)
```sh diff
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

(`sh diff`)
```sh-language diff
-echo "old stuff"
+echo "new stuff"
echo "unchanged"
```

