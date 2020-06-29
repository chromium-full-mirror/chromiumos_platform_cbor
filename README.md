# `cbor`: Concise Binary Object Representation

This library is a partial implementation of the RFC 7049 Concise Binary Object
Representation standard.

The source code was fetched from `chromium/src`
(https://chromium.googlesource.com/chromium/src/+/242df8b64d2a0ab5f057d1d4c76ea8537fdbb789)
in order to avoid code duplication.

The cros/upstream/master branch is a mirror of the components/cbor directory
from upstream. It is automatically updated to reflect the latest changes
in upstream.

## How to update the source

To pull in updates from `chromium/src`, do the following:

*   `git checkout -b upstream cros/upstream/master`
*   `git checkout master`
*   `git merge --allow-unrelated-histories upstream`
    *   Expect merge conflicts, because of the difference in header paths.
    *	OWNERS should use the version from master.
    *	BUILD.gn should mostly use the version from master, unless the upstream changes
        the files to be built.
    *	The #include paths should use the version from master (without "components/"). This
        should be the majority of the merge conflicts.
    *	In the commit message of the merge, list the changes from upstream that are merged,
        with original commit hash from upstream.
    *	Check the changes introduced by your merge by doing a diff against the commit
        before the merge. The difference should be the same as the changes in the upstream.
