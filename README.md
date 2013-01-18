MoinMoin on OpenShift
=====================

This git repository helps you get up and running quickly with Python 3 on OpenShift.


Quickstart
----------------------------

Create an account at http://openshift.redhat.com/

Create a Openshift application with a cartridge of your choice.

    rhc app create -a python3 -t diy-0.1

Add this upstream repo

    cd python3
    git remote add upstream -m master git://github.com/EddyRespondek/python3-openshift-example.git
    git pull -s recursive -X theirs upstream master
    
Then push the repo upstream

    git push

That's it, just ssh into your application and run command

    export PATH=${OPENSHIFT_DATA_DIR}bin/:$PATH

and make sure everything is working

    python -V


Packages
----------------------------

For convenience the following packages will also be installed

    distribute
    easy_install
    pip
    virtualenv
