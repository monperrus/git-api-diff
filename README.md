# git-api-diff: list API changes between two branches

Currently suports Java. Help wanted for other languages.

## Installation

Add git-api-diff to your $PATH

```shell
git clone https://github.com/monperrus/git-api-diff
export PATH=$PATH:`pwd`/git-api-diff

# or even better, modify your shell config file (eg .bashrc)
``` 

In you current repo, edit `.git/config` to add

    [diff "added-deleted-new-methods"]
            textconv = java-ls-methods.groovy
            cachetextconv = true
    [diff "java-ls-methods-with-hash"]
            textconv = java-ls-methods-with-hash.groovy
            cachetextconv = true

Dowload Spoon (`spoon-core-*-jar-with-dependencies.jar`), see <https://github.com/INRIA/spoon/>, and modify the path pointing to it in all Groovy files


## Usage

List added and deleted Java methods in the current branch, compared to master:

    git ls-added-deleted-methods

List modified Java methods in the current branch, compared to master:

    git ls-modified-methods

## TODO (contributions and pull-requests welcome)

* add a way to configure the path to `spoon-core-*-jar-with-dependencies.jar`

## See also

* https://stackoverflow.com/questions/46795853/find-methods-with-modified-code-between-two-versions-of-a-java-class
* https://stackoverflow.com/questions/5721447/using-git-to-identify-all-modified-functions-in-a-revision
