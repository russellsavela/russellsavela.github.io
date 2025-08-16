### CS-499 Enhancement Two Narrative

The Enhancement Two Artifact is based upon the same client/server application used in Enhancement One.  It was created from templates for the CS-340 course from the early summer of 2025.


The CS-340 Artifact was selected for inclusion in the ePortfolio because it is a good example of the use of data structures and algorithms used in a real-world application aligned with the course outcomes, and because it builds on the work accomplished in Enhancement One. This enhancement of the artifact showcased my ability to refactor data structures and utilize different data sources to produce useful insight into data.  Appropriate libraries were implemented to do so, in this case the SciPy stats library. The artifact now presents the user with both graphical and textual insight into the data distribution.


This enhancement met the goals for the course outcomes as planned in Module One, as it successfully implemented all design goals established there.  There are no changes planned to the course outcome goals established previously.
Minor challenges were encountered while modifying this artifact.  The decision to use the same artifact for all three enhancements naturally created dependency issues across the three enhancements.  The most critical being the Data Structures and Algorithms enhancement, as it depends on a functioning database to work, while the database is addressed in the third enhancement.   The database CRUD layer was therefore partially refactored to provide read functionality to support this phase.
The changed database also introduced other incompatibilities.  Data types were not the same, which required type-casting some fields.  Positional notation was used for accessing Pandas DataFrame columns in the original artifact, these positions were therefore updated, typically by naming the columns explicitly, a better coding practice in general.


A separate Github submodule was created to store the code for this enhancement, though it is still deployed via the first enhancement’s CI/CD pipeline via a branch.  This was done to minimize the number of pipeline configurations.

### Screenshots

These screenshots demonstrate the implmentation and testing of this Enhancement.

![Enhancement Two Artifact Screenshot](https://github.com/russellsavela/russellsavela.github.io/blob/main/assets/artifact.two.01.png?raw=true width=800)

