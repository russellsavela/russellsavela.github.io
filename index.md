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

The Enhancement Two Artifact is also based upon the client/server application used in Enhancement One.  This enhancement of the artifact showcased my ability to refactor data structures and utilize different data sources to produce useful insight into data.  Appropriate libraries were implemented to do so, in this case the SciPy stats library. The artifact now presents the user with both graphical and textual insight into the data distribution.

The decision to use the same artifact for all three enhancements naturally created dependency issues across the three enhancements.  The most critical being the Data Structures and Algorithms enhancement, as it depends on a functioning database to work, while the database is addressed in the third enhancement.   The database CRUD layer was therefore partially refactored to provide read functionality to support this phase.
The changed database also introduced other incompatibilities.  Data types were not the same, which required type-casting some fields.  Positional notation was used for accessing Pandas DataFrame columns in the original artifact, these positions were therefore updated, typically by naming the columns explicitly, a better coding practice in general.

#### Screenshot

![Enhancement Two Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.two.01.png?raw=true width=800)

#### Gitub Link

The Enhancement Two Artifact code is hosted at:

[Enhancement Two Artifact](https://github.com/russellsavela/cs499-enhancement-two)

### Artifact Three: Database Enhancement

#### Overview

The thrid and final Artifact Enhancement for this course entailed the automated provisioning of a new database, refactoring the database access code, and the creation of unit tests to verify the correct operation of these changes.  The largest challenge in this exercise was the lack of standardization across NoSQL databases.  Relational databases mostly follow the same SQL standards.  DynamoDB has different APIs for database interaction than MongoDB, and therefore all access methods were required to be refactored.  The Read method was completed to support the Enhancement Two requirements earlier, in this enhancement functionality of the Create, Update, and Delete methods was accomplished.  In retrospect, it would have been preferable to complete the database enhancements first.   The data access code was also changed to remove password authentication entirely; this is now done through an IAM role and instance profile created by the CI/CD pipeline in Enhancement One.

#### Screenshot

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.01.png?raw=true width=600)

#### Gitub Link

The Enhancement Three Artifact code is hosted at:

[Enhancement Two Artifact](https://github.com/russellsavela/cs499-enhancement-three)

### Course Outcomes

List course outcomes here, link to more detail.
