<!--
SPDX-FileCopyrightText: 2021 German Aerospace Center (DLR)
SPDX-License-Identifier: MIT
-->


# GitLab-Corpus
This tool creates a corpus for accessible repositories in a GitLab instance. 
The corpus will primarily contain information about software projects.

Relevant information could be:  
* number of authors or commits
* merge requests
* programming languages used
* CI usage  
…
and more.  

The output corpus is in the JSON-format, as it is widely used and because of its compatibility with [neo4j](https://neo4j.com/).

## Install

We assume that you installed Python >= 3.8 and a recent Git client.

Please follow these steps to install the required dependencies and to make available the `corpus` command line tool:

```bash
git clone <URL of this Git repository> corpus
cd corpus
pip install --editable .
```  

**NOTE**
- The required dependencies to use this tool are listed in the `install_requires` section of the [setup.cfg](setup.cfg) file.
- The [requirements.txt](requirements.txt) lists additionally recommended development tools.

## Usage
**NOTE** To use this tool, you first need to write a `config-file` in which you provide information about the GitLab instance you want to run this tool on. 

Here is an example:

```
[global]
default = gitlab-1
ssl_verify = true
timeout = 15

[gitlab-1]
url = https://gitlab.example.com
private_token = 123abc
api_version = 4
```
 
The tool can be run using the command `corpus`.

Running the command using the `--help` parameter or without any parameter, will print the help page.

## Documentation
The documentation is available in the [docs](docs/source) directory.
