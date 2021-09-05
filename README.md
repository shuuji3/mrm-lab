# mrm-lab

experimental playground of [mrm](https://mrm.js.org/)

## How to play

Try to commit a broken file and see let us observe how Prettier, set up by mrm, prevent the commit!

```sh
> git clone https://github.com/shuuji3/mrm-lab && cd mrm-lab/
> npm i
> echo 'bad change' >> hello.js
> git add .
> git commit -m 'Commit a bad change'
✔ Preparing...
⚠ Running tasks...
  ❯ Running tasks for *.{js,jsx,scss,css,html,md}
    ✖ prettier --write --loglevel warn [FAILED]
↓ Skipped because of errors from tasks. [SKIPPED]
✔ Reverting to original state because of errors...
✔ Cleaning up...

✖ prettier --write --loglevel warn:
[error] hello.js: SyntaxError: Unexpected token, expected "," (4:21)
[error]   2 |
[error]   3 |   1 + 2;
[error] > 4 |   console.log("hello";
[error]     |                      ^
[error]   5 |   const x = 1;
[error]   6 |
[error]   7 |
```

## References

- [Mrm: codemods for your project config files | Mrm](https://mrm.js.org/)
- [Pre-commit Hook · Prettier](https://prettier.io/docs/en/precommit.html)
- [Git Hooks without extra dependencies like Husky in Node.js project - DEV Community](https://dev.to/azu/git-hooks-without-extra-dependencies-like-husky-in-node-js-project-jjp)
