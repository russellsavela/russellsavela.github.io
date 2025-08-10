### CS-499 Enhancement One Narrative

The Enhancement One Artifact is a simple client/server application written in Python.  It was created from templates for the CS-340 course in the early summer of 2025.


The CS-340 Artifact was selected for inclusion in the ePortfolio due to the many opportunities to improve upon its functionality.  Specifically, as a web application, it was appropriate to improve the architecture, deployment, hosting, and security posture of this software artifact.  The improvements showcased skills in software automation, problem solving, and a security mindset.  The artifact is now deployed via a commit to the main branch on Github, which triggers a Github Action defined in `.github/workflows/deploy.yaml` to execute a Terraform apply.   Terraform is configured to maintain the state of the infrastructure in HCP Cloud.  The deployment creates an AWS EC2 instance, which is bootstrapped from the `terraform/user-data/config-deps.sh` script.  This script installs dependencies on the instance, clones the application code from Github, and then runs the refactored application code.  


This enhancement meets the course outcome of building a collaborative environment by demonstrating an appropriate way to automate the production deployment of a collaborative application.  It does so with technically sound, professional documentation, using well-founded, industry standard techniques, such as defining infrastructure as code and implementing pipelines to accomplish the goals.  The security outcome was met by refactoring secrets out of the codebase, implementing security roles that follow the principle of least privilege, and by following security best practices.
Several challenges were encountered during the process of enhancing and modifying the artifact.  One time-consuming challenge to overcome was a change made to the Terraform AWS authentication model which required hosting security credentials in the Terraform secrets environment, rather than Github Actions.  Identifying this change required review of the Terraform Github issues pages to find a viable workaround.


Because this artifact is also being used for other enhancements in this course, there are dependency issues that arose in planning the architectural enhancements for the first phase.   Successful automated deployment also required that the Database layer be in place, which was to be completed in a subsequent enhancement.  Therefore, sufficient changes to the database code were implemented as well to allow the Deployment components to work correctly.


The value of current documentation was learned during this process, as well as the value of detailed changelog notes when software releases change basic behaviors.  Having access to these saved considerable time in debugging the CI/CD issues that were encountered.  It was also learned that reverse engineering dependencies manually is desirable before implementing any automation, as the troubleshooting can be completed far more quickly.
 
