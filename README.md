# Shadow Dexterous Hand software

Updated version of the original repository.

Revised: 30/11/2023

## Original GitHub repository

 - [shadow-robot](https://github.com/shadow-robot/aurora) (v2.1.6)

## Installation Document

 - Document in Google Drive (SYSTEC-FoF/02.Projects/01.Finished/CiberToque/Info ShadowHand/Instalação_Software_Shadow.pdf)

## Changes

### - run-ansible.sh [CHANGE]

 - File path: `bin/run-ansible.sh`
 - Line: `238`
 - OLD: `git clone --depth 1 -b ${aurora_tools_branch} https://github.com/shadow-robot/aurora.git $aurora_home`
 - NEW: `git clone --depth 1 -b ${aurora_tools_branch} https://github.com/BrunoSantosCode/aurora.git $aurora_home`

### - ansible.cfg [ADD]
 - File path: `bin/ansible.cfg`
 - Content:
```bash
   [galaxy]  
   server = https://old-galaxy.ansible.com/
```

### - nvidia-container-toolkit.yml [CHANGE]

 - File path: `ansible/roles/installation/nvidia-docker/tasks/nvidia-container-toolkit.yml`
 - Lines: `22` and `29`
 - OLD: `ubuntu_version: "XX.04"`
 - NEW: `ubuntu_version: "18.04"`
