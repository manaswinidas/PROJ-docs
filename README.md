# PROJ-docs

This project requires git subtrees. Make sure you have it configured before running. Type git subtree in your terminal to check whether it is already supported in your git. Follow the instructions in the link in references to configure git subtree if you don't have it yet.

# Run 

First go to the `doc-content/drools-docs/src/main/asciidoc` folder and run `sudo sh split.sh`. This `split.sh` in the asciidoc folder is responsible for splitting, naming and categorising the doc-fragments. Now, a `DMN` folder is created upon which the assemblies will run.

<!-- In order to run the product-docs, you need to install [ccutil](https://pantheon.cee.redhat.com/#/help/ccutil-install) and follow the instructions in [proposal-d](https://gitlab.cee.redhat.com/red-hat-jboss-bxms-documentation/proposal-d/tree/master). -->

In order to run the community docs, you need to have Maven installed. If yes, goto `doc-content/drools-docs`, run `mvn clean install` and view the `index.html` in `target/generated-docs/html_single`.

<!-- In order to run the PROD docs in gitbook, go to the `assemblies/assembly_dmn-models/dm/build/tmp/en-US/html-single` folder and run `gitbook serve`. You can see the documentation at `localhost:4000`. It may ask you to run `gitbook install`. You also may need to install gitbook CLI, if you don't have it already. Just run `npm install gitbook-cli -g` and run the commands again. -->

In order to fetch from all subtrees in the root repository, run `git subtree pull-all`. 
In order to push all changes in subtrees to the original projects from the root repository, run `git subtree push-all`.

# Steps to reproduce

If you go to the `.gittrees` file, you can see a "DMN" subtree. The DMN repository has been added as a subtree for test purposes. Following are the steps to add a subtree:

`git remote add -f DMN git@github.com:manaswinidas/DMN.git`

`git subtree add --prefix=doc-content/drools-docs/src/main/asciidoc/DMN git@github.com:manaswinidas/DMN.git master`

The latter adds a subtree to `.gittrees` and adds a folder in the given path.

References: 
[https://ruleant.blogspot.com/2013/06/git-subtree-module-with-gittrees-config.html](https://ruleant.blogspot.com/2013/06/git-subtree-module-with-gittrees-config.html)