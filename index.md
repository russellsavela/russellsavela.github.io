---
layout: default
css: "assets/css/custom.scss"
---

## Russ Savela CS-499 Portfolio

This is the portfolio site created for the CS-499 portfolio project. This Computer Science Capstone Course was an opportunity to implement and showcase the tools and techniques learned throughout the SNHU Computer Science curriculum.  This portfolio website seeks to illustrate the alignment of the accomplishments achieved during this course with the five course outcomes.  Choosing these enhancements was both a demonstration of judgement in selecting features that are relevant to industry, and an enjoyable chance to engage in the areas of Computer Science that I most enjoy.

### Professional Self Assessment

I have worked in the technology industry in various roles for over two decades, including software development, consulting, technical support and various sales support positions.  In this Computer Science curriculum, there has been opportunity to expand on the skills I have used in these roles and gain new skills and insights into fields I have had limited exposure to in the past.   

Choosing the enhancements to implement during this course required professional judgement to determine which features would deliver the most relevant impact, within the constraints of a short timeline.    These decisions were made after much research and thought, only after establishing that they were both impactful and feasible to accomplish.
A single software artifact, the CS 340 Client/Server application, was chosen to implement all three enhancement areas in this course.   There were several reasons for this.  By using a single code base, more time was available to implement more substantial feature sets.  Using a single artifact allowed for demonstrating the flexibility and variety of improvements related to the course outcomes that can be identified in a single project. And finally, this artifact contained many disparate components, common in modern software projects.

One common theme across the enhancements was the importance of automation.  Each was refactored to be deployed as infrastructure as code through a pipeline.   Doing so has many advantages, chief among them, fostering teamwork and collaboration among stakeholders.  By architecting a product to both build itself and deploy itself from a single repository, development and operations teams must work together during almost all project lifecycle phases.  This leads to faster deployment, better integration, repeatability, and better testing.  I have used these techniques to deploy enterprise telephony systems, machine learning models, and many other solutions for many verticals.

Each of the enhancements incorporate data structures and algorithms inherently.  The Terraform code responsible for each is implemented via declarative data structures defining how each will be instantiated.  This is also done securely, by using security credentials that are maintained in the environment, not in the code itself.  The Artifact Two Enhancement addresses data structures most directly, by leveraging the Pandas DataFrames to compute more sophisticated statistics on the underlying data.
Software Engineering practices were also a focus across each enhancement.   Continuous Integration and Continuous Delivery (CI/CD) was implemented for each, and automated Unit Tests were also developed to prove that the products met their specifications.  Documentation was created, in the form of appropriate comments, relevant README files, and narratives that served as Software Design Documents.

Taken as a whole, these enhancements demonstrate the processes taken by a software engineer to refactor prototype code into a production quality software product.  The first enhancement artifact focuses on the overall theme of automation.  The second adds functionality useful to users, and third makes substantially improvements to the database underling the original artifact.  The individual enhancements are examined below and show what can be accomplished with abilities I have gained in the Computer Science program.

### Course Outcomes

Throughout the course, work on each enhancement was aligned with one or more of the course outcomes.  The overall goal of the enhancements as a whole was to adapt the original artifact into a more collaborative form.  This was accomplished for several audiences.  The developers are better able to collaborate with the adoption of a continuous integration and deployment architecture.  This also facilitates collaboration with an operations team.  And finally, end users are better able to engage with an application that is now accessible without a Jupyter notebook, requiring no specific skills to access.

Documentation was created to describe the operation and functionality of the enhancements.  The narratives each serve as software design documents, informing the motivation for each feature.  The code review includes graphics and visuals to emphasize the deficiencies identified, and the proposed feature sets to be implemented.  While each artifact is deployment automatically, appropriate README documentation is also provided in each enhancement repository to clearly specify intended use for a technical audience.

Several design trade-offs were evaluated in the development of the overall project. One example was the cost of deployment time verses development time in choosing instance or container-based compute, instances were ultimately chosen to simplify debugging. The choice of data structures in the infrastructure deployment templates used environmental variables to promote code re-use.  The choice of SciPy stats to implement statistical analysis was an appropriate tool, allowing the use of optimized libraries.

The well-founded practice of deploying immutable infrastructure was adopted for each artifact enhancement.  Any change to the underlying application results in the impacted compute or storage resource being entirely reprovisioned, as appropriate.  This also improves documentation, by versioning every change throughout the software lifecycle.

During the code review, several security weaknesses were identified.  These have been mitigated through the refactoring of the artifact code during the course. Hard-coded passwords were removed entirely and replaced with industry-standard role-based authentication.  The creation of these roles is also managed in code, providing both an audit trail and easing compliance with security standards.


### Artifact Code Review

The CS-340 Client/Server final project was used as the orgininal artifact for all three of the enhancement developed for this course.  In this informal code review, the source code was examined in the scope of the three enhancement areas for

[![CS 499 Russ Savela Code Review](https://img.youtube.com/vi/NZknNQFUsXk/0.jpg)](https://www.youtube.com/watch?v=NZknNQFUsXk)

### Artifact One: Software Engineering and Design Enhancement

#### Overview
The CS-340 Artifact was selected for inclusion in the ePortfolio due to the many opportunities to improve upon its functionality.  Specifically, as a web application, it was appropriate to improve the architecture, deployment, hosting, and security posture of this software artifact.  The improvements showcased skills in software automation, problem solving, and a security mindset.  The artifact is now deployed via a commit to the main branch on Github, which triggers a Github Action defined in `.github/workflows/deploy.yaml` to execute a Terraform apply.   Terraform is configured to maintain the state of the infrastructure in HCP Cloud.  The deployment creates an AWS EC2 instance, which is bootstrapped from the `terraform/user-data/config-deps.sh` script.  This script installs dependencies on the instance, clones the application code from Github, and then runs the refactored application code. 

The full narrative can be found here:
[Enhancement One Narrative](artifact.one.narrative.md)

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

The full narrative can be found here:
[Enhancement Two Narrative](artifact.two.narrative.md)

#### Screenshot

![Enhancement Two Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.two.01.png?raw=true width=800)

#### Gitub Link

The Enhancement Two Artifact code is hosted at:
[Enhancement Two Artifact](https://github.com/russellsavela/cs499-enhancement-two)

### Artifact Three: Database Enhancement

#### Overview

The thrid and final Artifact Enhancement for this course entailed the automated provisioning of a new database, refactoring the database access code, and the creation of unit tests to verify the correct operation of these changes.  The largest challenge in this exercise was the lack of standardization across NoSQL databases.  Relational databases mostly follow the same SQL standards.  DynamoDB has different APIs for database interaction than MongoDB, and therefore all access methods were required to be refactored.  The Read method was completed to support the Enhancement Two requirements earlier, in this enhancement functionality of the Create, Update, and Delete methods was accomplished.  In retrospect, it would have been preferable to complete the database enhancements first.   The data access code was also changed to remove password authentication entirely; this is now done through an IAM role and instance profile created by the CI/CD pipeline in Enhancement One.

The full narrative can be found here:
[Enhancement Three Narrative](artifact.three.narrative.md)

#### Screenshot

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.01.png?raw=true width=600)

#### Gitub Link

The Enhancement Three Artifact code is hosted at:
[Enhancement Two Artifact](https://github.com/russellsavela/cs499-enhancement-three)


