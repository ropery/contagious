Overview
========

_contagious_ boosts your download speed by pulling the target from multiple
mirrors around the world.

A simple example goes like this:

    $ contagious firefox
    [#1 SIZE:2.5MiB/49.0MiB(5%) CN:40 SPD:971.0KiBs ETA:49s]

contagious uses _profiles_ provided by the user. See below.

Requirements
============

* contagious is written in [BASH][].
* The actual tool used is [aria2][].

  [bash]: http://www.gnu.org/software/bash/
  [aria2]: http://aria2.sourceforge.net/

Profiles
========

Profiles, or modules, are shell scripts that defines variables, including all
the mirrors you want to use for the profile.

By default, contagious looks in ${XDG\_CONFIG\_HOME}/contagious.d for profiles.

The following variables are defined in a profile:

*   filename: the file name. Required.
*   filepath: the file path on the servers.
*   hashtype: the type of the file hash. (md5, sha1, sha256, ...).
*   hashsum:  the value of the file hash.
*   mirrors:  the array of mirrors. Required.
*   aria2\_opts: additional (overriding) aria2c options.

Normally, the final URI of the target is constructed like this:

    mirror + filepath + filename

But when you set `filepath` to `/`, the mirror _is_ the URI. This is designed
for the less consistent mirrors.

`hashtype` and `hashsum` are optional, but recommended so that aria2 ensures
correct download by integrity check.

`aria2c_opts` is for fine-tuning download options per profile.

contagious ships with sample profiles under the `contagious.d` directory.

- - -

See Also
========

* aria2c man page: [aria2c(1)][]

  [aria2c(1)]: http://aria2.sourceforge.net/aria2c.1.html

