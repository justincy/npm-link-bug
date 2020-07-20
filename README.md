# npm-link-bug

Minimum reproducible example for an [npm bug](https://github.com/npm/cli/issues/1542).

The error will print this mesage in the console:

```
npm ERR! Cannot read property '0' of undefined
```

Steps to reproduce:

1. Clone and install this repo.
2. Clone and install [the dependency](https://github.com/justincy/npm-link-bug-dep) of this repo.
3. `npm link` the dependency.
4. Run `npm i`. This will show the error.
5. Run `npm ls`. This shows an unrelated error.
6. Delete `package-lock.json`
7. Run `npm ls` again to see the error we're interested in.
8. Note that `npm i` continues to error with `package-lock.json` deleted.
