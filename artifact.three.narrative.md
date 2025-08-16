### CS-499 Enhancement Three Narrative

The Enhancement Two Artifact is based upon the same client/server application used in Enhancements One and Two.  It was created from templates for the CS-340 course from the early summer of 2025.


The CS-340 Artifact was selected for inclusion because it is fundamentally a database application.  
This enhancement of the artifact showcased my ability to refactor database code, migrate to a different database adapting it to different data types and access methods.  Additionally, automation was implemented both in a CI/CI deployment, and in the creation of automatic Unit Tests to verify the functionality of the database access code.  This enhancement allows the application to use a more scalable database offering a high availability configuration, including replication.
The most consequential design decisions were made in this feature enhancement.  In the other enhancements, all code and infrastructure were deployed via the same Github Actions CI/CD pipeline.  While it is generally best practice to deploy both infrastructure and application code from the same repository, this is not generally true for a dependent database layer.  In a deployed application, code changes being deployed should not normally trigger a redeployment of the database.  Considering this, the database is deployed via its own Terraform code.  


The largest challenge in this exercise was the lack of standardization across NoSQL databases.  Relational databases mostly follow the same SQL standards.  DynamoDB has different APIs for database interaction than MongoDB, and therefore all access methods were required to be refactored.  The Read method was completed to support the Enhancement Two requirements earlier, in this enhancement functionality of the Create, Update, and Delete methods was accomplished.  In retrospect, it would have been preferable to complete the database enhancements first.   The data access code was also changed to remove password authentication entirely; this is now done through an IAM role and instance profile created by the CI/CD pipeline in Enhancement One.


The Unit Tests are contained in testAnimalShelter.py, and these must be run from an instance with an appropriate instance profile granting it permission to access the database.  This is a secure way to implement authentication, as there is no possibility of credentials such as passwords or keys being lost, they don’t exist at all.  
This Enhancement closely followed the course outcomes identified in Module One.   It delivers value for a common industry-specific goal by implementing replication for the database deployment.  The refactoring of the application improved the security posture by avoiding the use of hard-coded credentials, consistent with the outcome of having a security mindset. 
 
 
### Screenshots

These screenshots demonstrate the implmentation and testing of this Enhancement.

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.01.png?raw=true width=800)

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.02.png?raw=true width=800)

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.03.png?raw=true width=800)

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.04.png?raw=true width=800)

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.05.png?raw=true width=800)

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.06.png?raw=true width=800)

![Enhancement Three Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.three.07.png?raw=true width=800)

