# A custom html5bp build script

The build script is a tool that optimizes your code for production use on the web.

It has been customised for use by me in my projects and so as the following configurations

* This should be placed in a subdirectory in html5bp (i.e. /source/build)
* The publsih folder has been set to /public

@todo
* Need to add FTP publishing commands

To build your project use the following commands:

    cd source/build
    ant build


In order to merge this into your own build:

    # Move into your project's git repository
    cd my-project
    # Create and checkout a new feature branch
    git checkout -b ant-build-script
    # Create a new remote called "h5bp-ant-bs".
    # Fetch the build script from the remote repository.
    git remote add -f h5bp-ant-bs git://github.com/dineshraj/ant-build-script.git
    git merge -s ours --no-commit h5bp-ant-bs/master
    # Put the build script into a subdirectory `build/`
    git read-tree --prefix=build/ -u h5bp-ant-bs/master
    # Commit the merge (preserve the build script history too)
    git commit -m "Subtree merge H5BP ant build script"
    # Update the build script subtree if needed
    git pull -s subtree h5bp-ant-bs master
    # Merge back into master branch if everything went according to plan
