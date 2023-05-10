# Requirements
## Functional
### Mandatory
#### General
- Each faculty member owns zero or one accounts
- Each member can act as an author as well as a reviewer
- A member has an overview of all reviews that have been requested from him and have not yet been reviewed by him
- When submitting a review request, the author can can and must designate a deadline, the pdf of the paper, the author of the paper, the list of assignees for that
review request
- Each paper is associated with a deadline after which no more reviews can be submitted and only the author can view the paper anymore
- The author can delete papers after their review deadline has expired
- The author is notified when a new review was submitted
    
#### Review
-...
<!-- TODO: Check which criteria a review has to cover-->

##### External Review
- external papers are distributed equally between the faculty members using a rating algorithm 
- grouping of external papers in conference groups

##### Internal Review
- After a deadline has expired, the paper can be viewed by the author alongside all feedbacks the paper has received
- assigned reviwers can either accept or reject a review request
- the author can assign reviewers, which in turn will be notified about their assignment 
- 

### Optional
- live notfications of assigments, submits usw
- categorization of papers (topic groups?)
- Review counter + leader board ;D
- Uploading papers in batches 
- Profile status (reviewing, free, blocked ...)

### Non-Functional
- Neither the number of accounts, nor the number of papers in the system is limited
- The number of reviews any member can do and request is not limited
- The number of papers per authors is unlimited
<!-- TODO: Are these functional or not? -->

## Diferentiation criteria
- there will only be one distribution mechanism implemented
- There will be no tracking or history of past reviews
- After a submission is created, it can't be changed. This includes, the paper file, the deadline and the assignees
- There wont be an extra pdf editor


# Definitions
LOESCHEN 1. **Researcher**: A member of the scientific community who writes research papers.
1. **Faculty**: The administrative entity that the system is deployed for
1. **(Faculty) Member**: A researcher of the faculty the system is deployed under
1. **Account**: Virtual representation/identity??? of a faculty member that only the corresponding member can access.
1. **(Research) Paper**: A research paper, written by either a faculty member or a an external researcher
1. **Abstract**: The official summary of a paper. The abstract is part of the paper itself.
1. **Author (of a paper)**: The person who wrote the paper
    1. **Member author**: An author who is also a member
    1. **External author**: An author who is not a member
1. **System**: The parts of the application that are under development. Includes the accounts as well as the servers, database systems and the deployed website.
1. **Review Process**: The process of reading a paper and forming a diverse opion on aspects of the quality of the paper. A review ends in feedback by the reviewer to the author.
1. **Review**: The representation of an opinion formed during the review process. For the purposes of this app, this constitutes the filled-out feedback form and an attachment to this form.
1. **Deadline**: A date before which a review has to be completed by an assignee.
1. **Assignee of a paper**: A Member which was asked by the author of the paper to review that paper
1. **Reviewer of a paper**: A member who intends to review a given paper
1. **Feedback Form**: A standartized form for given feedback. It constitutes of standardized questions which must be scored.
1. **Feedback**: A filled-out Feedback Form which resembles the opinion formed after a review
1. **Review Request**: The request of an author to one or more assignees for a paper he has written.
1. **Submit a review request**: The process of an author of a paper uploading this paper and creating a review request for that paper, notifying the list of assignees of that request
1. **Internal Review**: A review that is requested of a faculty member by another faculty member for a paper which he has written
1. **External Review**: A review that is requested by a conference from a faculty member. During external review, the members don't have the option to deny review requests.
Therefore, in this context, the assignee and the reviewer of a paper are always identical
1. **Conference Associate**: A person at the faculty who receives the batch of papers from any particular conference
1. **External Review Process**: The process of a conference requesting external review of a batch of papers from a faculty
1. **Conference**: An entity which receives papers and distributes those papers to faculties, requesting external reviews of all the papers they send to a faculty
1. **Batch of papers (for external review)**: A group of papers which have been collectively sent to a faculty by a conference for external review
1. **Paper Distribution**: A phase of an external review process which comes after the batch of papers was sent to the faculty and before the papers have been assigned.
The goal of this phase is to assign the papers in a way which satisfies as many assignees as possible
1. **Paper Distribution Mechanism**: An algorithm which calculates the assignment of a batch of papers to the reviewers. This mechanism ends, i.e. executes the paper distribution

# Questions
1. How to handle admin
1. Can we get access to a gitlab instance please???
1. Should internal reviewers accept or reject reviews? -> Dictates the definition of assignee and reviewer
1. Exemplary functional specification, website is down
1. Observation: What entity should a conference resemble? Possibilities:
    1. A conference could be registered along the associate who receives batches of papers for that conference
    1. A conference could semantically just be a string which is attached to a batch of papers when an associate (who is just a member to the system) uploads a batch of papers for distribution
1. Can we mix diagrams and the requirements section? E.g. Could we write under mandatory requirements: The sysmem supports this activity diagram for the external review use case
1. Should be track reviews et cetera after their deadlines have expired
1. How should the associate receive the reviews of the batch of papers. In what form should they be downloadable
1. Reminder notifications if a deadline is approaching
1. Ability to add full-text comments to a Feedback?
1. Changable deadlines?
1. Is it ok if Repos are public?
1. Was laedt man beim Review hoch? Auch das kommentierte PDF oder nur das Feedback Form?