infection
=========

This is a work in progress github based package manager. It's like a cross between npm and pathogen. Features are implemented as needed and when there is time.

example infection.json
----------------------

(note: checking out from tags is not implemented yet, just include them for future proofing)

    {
        "infect": "ProjectFolder/src",
        "with: {
            "githubuser/github-project": "HEAD",
            "anothergithubuser/another-github-project": "v1.4"
        }
    }

Currently implemented
---------------------

    infect-checkout

Reads infection.json and pulls dependencies from github nonrecursively

(You'll have to include your dependencies' dependencies in your own infection.json for now)

    infect-unpack

Unpacks all packages into the "infect" folder described in infection.json.

    infect-pack [package name]

Re-packages a modified package into its package folder for committing back to github.

Needs implementing
------------------

* freezing versions (use git tags)
* recursive dependencies
* the ability to diff unpacked and packed copies of all packages
* the ability to make certain folders only unpack on development packages (i.e. test folders)
* an install script
* a warning if .gitignore does not ignore the packages directories (where to even put this? pre-commit hook?)
* JSON.sh is just sitting in the bin folder right now, do we even care?
