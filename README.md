This project demonstrates a simple pre-push hook. No additional modules required.

## Install hook

1) Navigate to .git/hooks and rename "pre-push.sample" to "pre-push"
2) Replace contents of file with below script:

```
#!/bin/sh
grep \(delete\)
if [ $? -eq 0 ]; then
# Do not run tests if deleting remote branch
exit 0
else
npm run lint && npm run test
fi
```

## More Info

"The hooks are all stored in the hooks subdirectory of the Git directory. In most projects, that’s .git/hooks. When you initialize a new repository with git init, Git populates the hooks directory with a bunch of example scripts..."

https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks
