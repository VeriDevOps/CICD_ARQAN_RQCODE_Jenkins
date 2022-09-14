# Jenkins Pipeline for RQCODE

![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white)
![Apache Groovy](https://img.shields.io/badge/Apache%20Groovy-4298B8.svg?style=for-the-badge&logo=Apache+Groovy&logoColor=white)
[![GitHub license](https://shields.io/badge/license-Apache%202-green?style=for-the-badge)](https://github.com/VeriDevOps/Jenkins-security-requirements-analysis/tree/main/LICENSE)

This is a Jenkins Declarative pipeline written on Groovy to assist requirements tagging and STIGs and tests suggestions. Requirements are managed in GitHub Issues. When a requirement is opened, the pipeline detects whether it is related to security and sets a tag ("security"/"non-security"). If a requirement is related to sequrity, next steps of pipeline manage [STIGs](https://www.stigviewer.com/stigs) and [RQCODE tests](https://github.com/VeriDevOps/RQCODE) suggestion.

## Table of Contents

Make sure this is updated based on the sections included:

- [Installation](#installation)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [Support + Feedback](#support--feedback)
- [License](#license)


## Installation

- Prerequisites for use
    - Groovy
    - Jenkins + Github connection
    - Docker support in Jenkins
- Installation:

```bash
git clone https://github.com/VeriDevOps/project-example.git
```

## Getting Started

- Copy **Jenkinsfile-security-requirements-analysis** to your project's repository
- Set up a project in Jenkins pointing at this Jenkinsfile
    ![](https://i.imgur.com/fu6n40D.png)
    - In repository set up a webhook triggered on Issue event
    ![](https://i.imgur.com/kFZkvtu.png)

- Install list of prerequisite plugins (**plugins.txt**) to Jenkins
- Change variables at the top of **Jenkinsfile-security-requirements-analysis**



| Variable name| Type | Default |Meaning |
| -------- | -------- | -------- |---------|
| **ISSUE_SECURITY_LABEL**| String    | "SECURITY"     | what label to set if a requirement is related to security     |
| **ISSUE_NON_SECURITY_LABEL** | String | "NON-SECURITY" | what label to set if a requirement is not related to security |
| **SEND_STIG_SUGGESTIONS_TO_RQCODE** | Boolean | true | if set to true, STIGs implementation suggestion will be sent to VDO-Patterns repository |
|**ARQAN_CLASSIFICATION_API_ENDPOINT** | String | "http://51.178.12.108:8000" | URL of the ARQAN classification service |
| **VDO_PATTERNS_REPO** | Dictionary | [owner: "anaumchev", name: "VDO-Patterns", url: "https://github.com/anaumchev/VDO-Patterns.git"] | Access details for the repo with tests implementation |


## Contributing

We appreciate feedback and contribution to this repo! Before you get started, please see the following:

- [Contribution guidelines](CONTRIBUTING.md)
- [Code of conduct guidelines](CODE-OF-CONDUCT.md)


## Support + Feedback

- Use [Issues](https://github.com/VeriDevOps/project-example/issues) for code-level support, usage, questions, specific cases
- Feel free to reach us


