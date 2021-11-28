# Automatic verificator of HTML and MD

[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

## About the project

Automatic verificator of HTML and MD.

* Check for file name and format
* Automate git commit messages
* Validate HTML and MD files

Used tools:

* ls-lint
* commitizen
* html-validate
* markdownlint-cli

### File names

Files must be created in *essays/* directory. Convention is *Name - File name*.\
ls-lint checks all .html and .md file names with this
regex: `regex:[A-Z][a-z]+ - [A-Za-z0-9 -_]+`.\
ls-lint ignores README.md.

### Commit messages

Convention for commit messages.

```text
feat: Add beta sequence
^--^  ^---------------^
|     |
|     +-> Summary in present tense.
|
+-------> Type: chore, docs, feat, fix, refactor, style, or test.
```

Examples:

* chore: Add Oyster build script
* docs: Explain hat wobble
* feat: Add beta sequence
* fix: Remove broken confirmation message
* refactor: Share logic between 4d3d3d3 and flarhgunnstow
* style: Convert tabs to spaces
* test: Ensure Tayne retains clothing

### HTML validator

html-validate is an offline HTML5 validator - does not upload
any data to a remote server, all testing is done locally.
html-validate checks all .html files in root directory.

Example:

```html
<p>
  <button>Click me!</button>
  <div id="show-me">
    Lorem ipsum
  </div>
</p>
```

```text
  1:1  error  Element <p> is implicitly closed by adjacent <div>  no-implicit-close
  2:2  error  Button is missing type attribute                    button-type
  6:4  error  Unexpected close-tag, expected opening tag          close-order
```

### MD validator

markdownlint-cli is command line tool for MD validation.
markdownlint-cli checks all .md files in root directory.

Example:

```md
# Lorem
ipsum
```

```text
Test - test.md:1 MD022/blanks-around-headings/blanks-around-headers 
Headings should be surrounded by blank lines 
[Expected: 1; Actual: 0; Below] [Context: "# Lorem"]
Test - test.md:2:5 MD047/single-trailing-newline 
Files should end with a single newline character
```

## Getting started

### Installation

1. Clone the repository

    ```sh
    git clone https://github.com/cr0c0pk1/Automatic-verificator-of-HTML-and-MD.git
    ```

2. Install NPM packages

    ```sh
    npm install
    ```

### Usage

1. Add or stage files before committing

    For all files

    ```sh
    git add .
    ```

    For one file

    ```sh
    git add <file-name>
    ```

2. Committing

    Use

    ```sh
    npm run commitizen
    ```

## References

* [ls-lint](https://github.com/loeffel-io/ls-lint)
* [commitizen](https://github.com/commitizen/cz-cli)
* [html-validate](https://gitlab.com/html-validate/html-validate)
* [markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli)
