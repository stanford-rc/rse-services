---
title: Software Checklist
tags: 
 - badge
 - software
---

# Software Checklist

The following checklist is to ensure reproducible software. This will be converted to a tool.

## Repository Checks

 - [ ] **Repository:** The source code is available at a public url.
 - [ ] **Version:** The software has a method to support versioning.
 - [ ] **Contributing:** A statement is included about how to contribute to the software. 
 - [ ] **Issues:** An issues board is available for a user to ask a question, or request support.
 - [ ] **Maintainer:** At least one primary maintainer is indentified.
 - [ ] **License:** An appropriate plain-text LICENSE file is included, ideally [OSI approved](https://opensource.org/licenses/alphabetical)

## Documentation

 - [ ] **Installation:** The repository includes instructions for installation in the README, including dependencies and operating system requirements.
 - [ ] **Purpose:** A clear purpose or statement of need is defined. A reader knows what the software does.
 - [ ] **Getting Started:** After installation, there is a clear "Getting Started" tutorial or similar.
 - [ ] **Examples:** Are included (via scripts or docu
 - [ ] **Docstrings:** If appropriate for the language, docstrings are rendered into code documents.
 - [ ] **Functionality:** All functions, client interactions, and if appropriate, API endpoints, are documented. 
 - [ ] **Living Documentation:** A user can easily jump from any documentation page to ask for help, or contribute changes [[1](https://vsoch.github.io/2018/interactive-posts/)]. 

## Artifacts

 - [ ] **Containers** The repository provides one or more container recipes (Dockerfile, Singularity) or a pre-built container.
 - [ ] **Publications:** Any relevant citations for papers or external resources are linked in the README.
 - [ ] **Data:** Any required data or similar artifacts are linked.

## Continuous Integration

 - [ ] **Automated Testing:** is done with any request for change to the main (typically master) branch.
 - [ ] **Operating Systems:** testing is done across operating systems and environments that cover 80% of use cases.
