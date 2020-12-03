<!--
https://readme42.com
-->



[![](https://img.shields.io/badge/OS-Unix-blue.svg?longCache=True)]()
[![](https://img.shields.io/pypi/v/github-fullname.svg?maxAge=3600)](https://pypi.org/project/github-fullname/)
[![](https://img.shields.io/npm/v/github-fullname.svg?maxAge=3600)](https://www.npmjs.com/package/github-fullname)[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/github-fullname/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/github-fullname/actions)

### Installation
```bash
$ [sudo] pip install github-fullname
```

```bash
$ [sudo] npm i -g github-fullname
```

#### Examples
```bash
$ cd path/to/repo
$ github-fullname .
owner/repo
```

```bash
$ find ~/git -type d -mindepth 1 -maxdepth 1 -exec github-fullname {} \;
owner/repo1
SKIP (~/git/repo2): .git NOT EXISTS
owner/repo3
...
```

hide errors
```bash
$ find ~/git -maxdepth 1 -exec github-fullname {} \; 2> /dev/null
owner/repo1
owner/repo3
...
```

show github orphaned repos:
```bash
$ python -m github_repos | grep -v "$(find ~/git -maxdepth 1 -exec github-fullname {} \; 2> /dev/null)"
```

delete github orphaned repos:
```bash
$ python -m github_repos | grep -v "$(find ~/git -maxdepth 1 -exec github-fullname {} \; 2> /dev/null)" | xargs python -m github_delete
```

<p align="center">
    <a href="https://readme42.com/">readme42.com</a>
</p>
