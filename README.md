# Obviated?
Seems to be coming to a script bundled in IntelliJ: https://confluence.jetbrains.com/display/IDEADEV/Command-Line+Source+Code+Formatter

# Headless IntelliJ Code Formatter

We had a need to reformat multiple projects and branches using IntelliJ's code style. Rather than do this manually this
little repo provides some scripts to do this automatically.

## Prerequisites

1. JDK 1.8
2. jq (brew install jq)
3. wget (brew install wget)

## To reformat all platform modules do the following:

1. git clone git@bitbucket.org:atlassian/intellij-headless-formatter.git
2. ./bin/build.sh
3. ./bin/batchstyle.sh

This will checkout all platform modules, and for each branch will format them and submit the changes on issue branches
for the given version.

## To reformat a single workspace do the following:

1. git clone git@bitbucket.org:atlassian/intellij-headless-formatter.git
2. ./bin/build.sh
3. ./bin/codestyle.sh path/to/workspace/root/directory

This will simply run the formatter on what is already present there. It will not check out or commit changes. This is
useful for catching up a feature branch you're resurrecting, or for projects not yet part of the platform but following platform
styles.