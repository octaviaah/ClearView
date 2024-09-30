## Core requirements
After analyzing the client's requirements, we identified the following features of the system:
* ClearView must leverage AI to re-construct job seeker resumes into a S.M.A.R.T. goal format and quantifiable align their experience to open roles posted by the hiring manager
* The AI tool is proving resume tips and eliminating any racial, lifestyle, cultural indicators
* ClearView should provide a similarity Score/Match on job descriptions
* ClearView should offer the option to reveal the profile of a candidate if the recruiter paid a fee.


## Project Constraints
* Integration with AI tool
* Ability to integrate with different systems from multiple clients
* Integration with payment system for unlocking the candidate profiles

## Architecture characteristics
Based on the core requirements, we identified the following architectural characteristics:
* Confidentiality - ClearView must comply to the highest security standards and regulations to protect the data of its users.
* Observability - ClearView provides statistics and metrics in real time, by logging information related to interaction, it becomes easier for us to identify areas of improvement and ensure seamless functionality.
* Cost - A key strategy for our system is a pay-as-you-go model to align costs with user demand, and leverage automation to minimize manual processes.
* Data integrity/consistency - This characteristic is vital to ensure reliable and accurate information throughout the hiring process. The job postings, candidate profiles and the statuses of the applications need to be accurate at all times on the platform.
* Performance/scalability - The hiring process is maximized using effective AI matching algorithms, connecting qualified candidates to relevant job postings, improving the quality of hires
* Elasticity - As ClearView is planned to be used by numerous recruiters, it needs to have the ability to adapt to varying loads and user demand without compromising performance.
* Agility - As the requirements are in a continuous change, we want to adopt the Agile methodology while developing the ClearView system
