FROM ubuntu:latest

#SECTION 1: Install prerequisite utilities
RUN apt-get update && apt-get install git -y && apt-get install wget

#SECTION 2: Install the State Tool
ADD https://platform.activestate.com/dl/cli/d123/install.sh /install.sh
RUN sh /install.sh /opt/ActiveState && ln -s /opt/ActiveState/bin/state /usr/local/bin

#Section 3: Checkout the project from the platform (will also bring in git repo)
RUN state checkout ActiveStateSE/tensorflow-ml-demo

