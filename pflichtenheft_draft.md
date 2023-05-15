# Requirements
## Functional
### Mandatory
#### General
- Neither the number of accounts, nor the number of papers in the system is limited
- Keep track of notifications
- Aggregations like this paper was created, that many users were notified
- Edit paper details
- Details of the paper: Add authors

##### Users
- Each faculty member can own one accounts
- Each member can act as an author as well as a reviewer
- Can log in by using their email and password
- Can logout by pressing a "logout" button
- Can reset their password?
- Can delete their account?
- A member has an overview of all reviews that have been requested from him and have not yet been reviewed by him
- The author can delete papers after their review deadline has expired
- The author is notified when a new review was submitted
- The assignee is notified when the review request for him is created
- No one except for the author can see the submitted reviews
- Have an inbox where they get an overview of their notifications
- Receive each notifiaction also per e-mail
- 

##### Papers
- Each paper is associated with a deadline after which no more reviews can be submitted and only the author can view the paper anymore
- Papers can be uploaded as pdf 
- Papers are in correaltion with the author
- Papers are downloadable as pdf
- Each internal paper has an abstract attached to it
- When submitting a paper, the author can and must designate a deadline, the pdf of the paper, the author of the paper, the list of assignees for that review request
- The number of papers per authors is unlimited
- A paper has only exactly 1 author
- The author is automatically assigned when uploading the paper and is the uploader
-  

##### Reviews
- The number of reviews any member can do and request is not limited
- Can be accepted or rejected by the assignee
- Each member is only to be assgined once to a given paper


###### External Review
- external papers are distributed fairly between the faculty members using a rating algorithm
- grouping of external papers in conference groups

###### Internal Review
- After a deadline has expired, the paper can be viewed by the author alongside all feedbacks the paper has received
- assigned reviwers can either accept or reject a review request
- the author can assign reviewers, which in turn will be notified about their assignment 

### Optional
- live notfications of assigments, submits usw
- categorization of papers (topic groups?)
<!-- boah weiss ich nicht leute... -->
- Review counter + leader board ;D
- Uploading papers in batches 
- Profile status (reviewing, free, blocked ...)
- There exists an algorithm to read paper title and abstract out of the pdfs
- overview over notifications
- Optimized for mobile
- Fix typos in the pdf or something (dont know if i got that correctly)

### Non-Functional
- Resilience against mailicious and 
- Confidentiality

## Diferentiation criteria
- there will only be one distribution mechanism implemented
- There will be no tracking or history of past reviews
- After a submission is created, it can't be changed. This includes, the paper file, the deadline and the assignees
- There wont be an extra pdf editor
- Only pdf

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
1. **Review Form**: A standartized form for given feedback. It constitutes of standardized questions which must be scored.
1. **Deadline**: A date before which a review has to be completed by an assignee.
1. **Assignee of a paper**: A Member which was asked by the author of the paper to review that paper
1. **Reviewer of a paper**: A member who intends to review a given paper
1. **Review Request**: The request of an author to exactly one assignee for a paper he has written.
1. **Uploading a (batch of) paper(s)**: Submitting the pdf (or other artifact) of a paper to the sysmtem and supplying additional information such as deadline and comment. This does not yet send review requests. In external review, this starts the distribution phase. TODO: Who gets the notification/ is everyone included or only selected
1. **Create a review request**: The author of an uploaded paper selects a new assignee and sends a review request to this assignee
1. **Internal Review Request**: A review that is requested of a faculty member by another faculty member for a paper which he has written
1. **External Review Request**: A review that is requested by a conference from a faculty member. During external review, the members don't have the option to deny review requests.
Therefore, in this context, the assignee and the reviewer of a paper are always identical
1. **Conference Associate**: A person at the faculty who receives the batch of papers from any particular conference.
1. **External Review Process**: The process of a conference requesting external review of a batch of papers from a faculty
1. **Conference**: An entity which receives papers and distributes those papers to faculties, requesting external reviews of all the papers they send to a faculty
1. **Batch of papers (for external review)**: A group of papers which have been collectively sent to a faculty by a conference for external review
1. **Paper Distribution**: A phase of an external review process which comes after the batch of papers was sent to the faculty and before the papers have been assigned.
The goal of this phase is to assign the papers in a way which satisfies as many assignees as possible
1. **Paper Distribution Mechanism**: An algorithm which calculates the assignment of a batch of papers to the reviewers. This mechanism ends, i.e. executes the paper distribution

# Questions
1. How to handle admin
-> keycloak
1. Can we get access to a gitlab instance please???
-> gitlab.scc.kit.edu
1. Should internal reviewers accept or reject reviews? -> Dictates the definition of assignee and reviewer
-> Yeah thats fine
1. Exemplary functional specification, website is down
1. Observation: What entity should a conference resemble? Possibilities:
    1. A conference could be registered along the associate who receives batches of papers for that conference
    1. A conference could semantically just be a string which is attached to a batch of papers when an associate (who is just a member to the system) uploads a batch of papers for distribution
<!-- 1. Can we mix diagrams and the requirements section? E.g. Could we write under mandatory requirements: The sysmem supports this activity diagram for the external review use case -->
1. Should be track reviews et cetera after their deadlines have expired
-> Its possible to delete stuff and requests
1. How should the associate receive the reviews of the batch of papers. In what form should they be downloadable
1. Reminder notifications if a deadline is approaching
-> No / optional
1. Ability to add full-text comments to a Feedback?
1. Changable deadlines?
1. Is it ok if Repos are public?
-> Everything is editable
1. Other groups always have kann/muss criteria instead of mandatory and optional
1. Deadline optional
yes
1. Bell in the frontend which displays the notifications?
1. Feedback form? How does it look? What questions are there, exactly? Do you attach a commented pdf/an artifact to it? Whats different between internal and external review?
1. Should you be able to edit submissions? Reviews?
    - Should you be able to save work in progress feedback forms?
1. Was laedt man beim Review hoch? Auch das kommentierte PDF oder nur das Feedback Form?
1. Wie sollen die Definitionen funktionieren
1. Nur PDF oder auch andere File Types
1. Soft or hard deadline?
1. Only Darius will do the phase presentation

# Design
- Creation of the conference should be separate of the paper upload
- Menu / Breadcrumbs / site direction

# Feedback
Presentation: 10 minutes-ish, short summary

