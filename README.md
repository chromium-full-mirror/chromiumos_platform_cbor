# `cbor`: Concise Binary Object Representation

This library is a partial implementation of the RFC 7049 Concise Binary Object
Representation standard.

The source code was fetched from `chromium/src`
(https://chromium.googlesource.com/chromium/src/+/242df8b64d2a0ab5f057d1d4c76ea8537fdbb789)
in order to avoid code duplication.

## How to update the source

To pull in updates from `chromium/src`, do the following:

*   `git remote add upstream https://chromium.googlesource.com/chromium/src`
*   `git fetch upstream master`
*   `git checkout -b staging-branch upstream/master`
*   `git subtree split -P components/cbor -b synthetic-branch`
    *   This could take ~2 hours
*   `git checkout master`
*   `git merge --allow-unrelated-histories -s subtree synthetic-branch`
    *   Resolve merge conflicts, if any.
    *   In the commit message of the merge, describe what changes are added,
        with original commit hash in chromium/src.
        E.g. using "git checkout staging-branch && git log --oneline components/cbor"
*   `git branch -D staging-branch synthetic-branch`
*   `git remote remove upstream`

