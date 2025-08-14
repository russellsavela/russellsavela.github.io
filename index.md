---
layout: default
---

## Russ Savela CS-499 Portfolio

This is the portfolio site created by Russ Savela for the CS-499 portfolio project.

### Professional Self Assessment

I have acquired new skills in 

### Artifact Code Review

The CS-340 Client/Server final project was used as the orgininal artifact for all three of the enhancement developed for this course.  In this informal code review, the source code was examined in the scope of the three enhancement areas for



[![CS 499 Russ Savela Code Review](https://img.youtube.com/vi/NZknNQFUsXk/0.jpg)](https://www.youtube.com/watch?v=NZknNQFUsXk)


### Artifact One: Software Engineering and Design Enhancement

#### Overview
The CS-340 Artifact was selected for inclusion in the ePortfolio due to the many opportunities to improve upon its functionality.  Specifically, as a web application, it was appropriate to improve the architecture, deployment, hosting, and security posture of this software artifact.  The improvements showcased skills in software automation, problem solving, and a security mindset.  The artifact is now deployed via a commit to the main branch on Github, which triggers a Github Action defined in `.github/workflows/deploy.yaml` to execute a Terraform apply.   Terraform is configured to maintain the state of the infrastructure in HCP Cloud.  The deployment creates an AWS EC2 instance, which is bootstrapped from the `terraform/user-data/config-deps.sh` script.  This script installs dependencies on the instance, clones the application code from Github, and then runs the refactored application code. 
#### Screenshot
The screenshot below demonstrates the application being deployed successfully via a Github Action.

![Enhancement One Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.one.04.png?raw=true width=800)

#### Gitub Link
The Enhancement One Artifact code is hosted at:

[Enhancement One Artifact](https://github.com/russellsavela/cs499-enhancement-one)

And the orignal code is available at:

[Enhancement One Orignial Artifact]()

### Artifact Two: Algotrithms and Data Structures Enhancement

#### Overview

#### Screenshot

#### Gitub Link

### Artifact Three: Database Enhancement

#### Overview

#### Screenshot

#### Gitub Link

### Course Outcomes

List course outcomes here, link to more detail.
