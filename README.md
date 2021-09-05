# mrm-lab

experimental playground of [mrm](https://mrm.js.org/)

## How to play

Try to commit a broken file and see let us observe how Prettier, set up by mrm, prevent the commit!

```sh
> git clone https://github.com/shuuji3/mrm-lab && cd mrm-lab/
> npm i
# Uncommit the latest commit and put it to the staged area
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
