# Code Review

<!-- TOC -->

- [Code Review](#code-review)
    - [General Information](#general-information)
        - [Why should be reviewed](#why-should-be-reviewed)
        - [Who should review](#who-should-review)
    - [Prerequisites](#prerequisites)
        - [Commit](#commit)
        - [Merge Request / Pull Request](#merge-request-pull-request)
    - [The Review](#the-review)
        - [Checklist](#checklist)
    - [Partnership between Submitter and Reviewer](#partnership-between-submitter-and-reviewer)
        - [Ruleset](#ruleset)
    - [Conclusion](#conclusion)

<!-- /TOC -->

## General Information

A code review is basically a discussion of a number of proposed changes and offers the opportunity to learn and teach at the same time, as well as strengthening relationships with partners and colleagues.

Most developers today are expected to participate in code reviews, yet few are offered training or guidance on how to conduct an effective code review. There are many different possibilities and approaches, but it takes a lot of time and effort for all developers involved to find the most suitable solution for efficient code reviews. 

But why are these guidelines and rules important?
The answer is relatively simple: if the important and day-to-day things are well documented, it is easier for a newcomer to create value. It also reduces the possibility of other developers getting lost and causing confusion within the team or project, thus improving the quality of the discussions.

This article is designed to provide a helpful overview of this topic and at least help unsafe developers with this topic. Note that different tools use different terms for the same process! The best example of this is the typical 'Pull Request'. While GitHub and Bitbucket also call it 'Pull Request', GitLab calls it 'Merge Request'.

### Why should be reviewed

Code Reviews are processes that serve the verification of the developed code and usually fulfill both technical and social purposes: Find bugs before they are integrated, identify security concerns, ensure style consistency with the existing code base, maintain code quality, conduct training, promote a greater sense of responsibility, and allow other developers to become familiar with the code before it is integrated. 

The review improves overall code quality, but is also a perfect way to share knowledge and information.

### Who should review

In every company, the question often arises as to who exactly should conduct the code reviews. Should only senior developers check the code? And what about new developers on the affected project?

The answer to such questions is simple: everyone should do code reviews. Regardless of how long the person has worked on the project and which position the person fills within the company. And here's why:

For example: if a new developer, regardless of experience, joins a team or project, it generally always requires training in special things or the transfer of certain tasks. These can include code and project organization, migrations, testing, build, deployment and the general workflows within the team or project. This can lead to problems, especially with large and long-term projects, because the new developer may not yet have experience with the technologies used and the architecture and design decisions made, as well as the reasons for these.

In the best case, technical details and the typical workflows were and are documented in the project documentation. However, this does not guarantee a smooth implementation of new functions or the elimination of errors. It should never be forgotten that this is still an unknown code base for the new developer. The best way to get to know the project and its structure better is to follow an experienced developer in the project. In this way simple and complex processes can be traced and in case of questions and unknowns a clear and unambiguous contact person is known.

In addition, it is an excellent opportunity for a young developer to have a learning experience when he or she reviews the commits of experienced developers. Thus, clues for design and architecture decisions are visualized and clearer for the junior developer, but it also shows how these are used within the project by the already active developers. These can also be decisions that have been implemented in this way in other projects of the team, creating added value for future work. It is not harmful for the team if the young developer takes an additional look at the code, although it is not experienced. Such a person will most likely look at the project and the circumstances from a new perspective and possibly lead the team from a previous operational blindness. Thus, this process has considerable advantages not only for the junior developer, but also for the team and the project.

Of course, a developer can also train himself independently, but the reviews give a wider and more precise view into the project and it becomes clear in which context the services and technologies used are connected. This increases the chances for young developers to feel accepted and appreciated in the project and team, which gives you a certain security that this developer will remain in the company. In addition, the developer is able to take on complex projects in a timely manner, thus providing a wider and more predictable perspective from the outset. And this is invaluable for a stable team.

It is therefore clear that the review practices have not only technical but also social implications. However, to make it clear that the new developer is accepted by the already established developers as a member of the team and their contributions and opinions are appreciated, a healthy working environment is absolutely necessary. Everyone should be able to give and receive feedback without taking it personally. Therefore, it is a good idea that everyone, from juniors to seniors, are both reviewers and reviewees to enhance this atmosphere.

These reviews can also be applied in teams and to people with different competencies. Why not let backend developers check some frontend changes? Just because something goes beyond a developer's core competency does not mean that they are not able to detect errors or provide feedback. In addition, the reviewer gains experience in other areas and this opens the view to errors and work processes in other areas of competence.

## Prerequisites

In order for a code review to be as understandable as possible and to lead to fewer queries during the review process, some preparations are of elementary relevance.
Basically, there are two phases before a code review which are of immense importance for the review itself:

The commit and the merge request / pull request.

### Commit

It is essential that each commit contains as much detail and annotation as possible about the changes made so that the reviewer can understand and follow the thought processes. Because if something is not clear to the reviewer, this is the first place to go to eliminate it. 

Your commits should be a series of steps and follow the following rules to describe the development in detail as a whole:

1. Use a subject, body and footer for the commit. Separate them with a blank line each.

2. Restrict the subject line to 50 characters and use upper case for the subject line.

3. Do not end the subject line with a dot.

4. Wrap the body at 72 characters.

5. Use the body to explain what and why vs. how.

6. In the footer, insert the reference to the task, such as the ID of the ticket.

### Merge Request / Pull Request

Now the commits have a descriptive and clear format, it's time to describe the PR/MR. This is not to be ignored, since it is usually the initial description of the conversion for the reviewer.

For the description to serve its purpose, it should contain some things:

1. A link to the original issue you’re solving, e.g. GitLab issue or JIRA ticket or other.
 
2. An overview of the thinking process and the approach to the solution.
 
3. How you went about testing this locally, e.g. “I ran this service and the X service and used cURL to confirm the new request behavior was working as expected”.
 
4. Anything you think you might break with this PR, but you’ve checked it hasn’t.
 
5. Anything you’d like the reviewers opinion on specifically, e.g. class names, time complexity of code, etc.

Once you have done this, the reviewer is able to quickly understand the code and focus on the quality and impact of the code. And this without it getting lost and making wrong assumptions.

Make sure, however, that you check the code yourself before submitting the request. Check that your commits look right! Did you leave a debugging code snippet? Does the code diff look the way you expected it to? This 5-minute check can save the reviewers a lot of confusion.

## The Review

Verifying code is difficult, and in fact it is a very extensive and stressful task. To support this process, it is often beneficial to have a checklist that accompanies the reviewer through the process. This not only improves effectiveness, but also increases focus.

The items of this list are not complete and should only point in one direction, in which an own checklist can go. You are welcome to use them, update them, personalize them or simply let them inspire you to develop completely new checklists.

Please note that checklists can be used for all code reviews. If the request is a small bugfix where only one condition is corrected, it is not necessary to check the structure of the entire application.

### Checklist

1. **Scope:** The referenced task has the highest priority. If there were adjustments outside of the task, these have to be referenced with a specific story which contains this topic. If there is no story for it, one has to be created.
 
2. **Correct function:** The specification is correct and has been fully implemented. Tests have been created and/or updated, the master branch has been merged into the request, all changes have been tested and edge cases have been covered. In addition, all paths should be checked to see if the code or changes can be broken.
 
3. **Defensiveness:** All inputs to public methods are validated and fail loudly when used incorrectly. All return codes and any security points have been checked.
 
4. **Easy to read and understand:** Important here is an appropriate and not exaggerated abstraction and problem resolution. The following support is provided: minimal interface usage, no hiding of information, good and meaningful naming, complete documentation and comments, fully optimized code.
 
5. **Style and layout:** All inspections pass the checks, the code formatter does not output any errors, no smelly code design, line length, styling is in line with project guidelines.
 
6. **Final considerations:** You fully understand the code and are aware of the impact of these changes on the application. In addition, you have ensured that the changes and implementations are unbreakable and actually complete. This includes all previous points, such as complete documentation, branch merged with the master, test coverage and referencing in the ticket system. You should be proud of the adjustments and be able to present this code to others.

## Partnership between Submitter and Reviewer

As already mentioned, it is also a human and social task to review and comment on someone else's code. The associated development of a partnership between submitter and reviewer is a long and complex process and should not be underestimated.

If there is a different level of experience between the two persons, this situation should be seen as a mentor by the more experienced developer. For example, if the reviewer has more experience than the submitter, then the reviewer should not only give written but also verbal feedback and talk to the submitter about his proposed changes. This conversation is intended to guide the submitter with less experience and pass on helpful feedback with experience gained so far. This discussion can also be arranged within the team so that the other team members can also benefit from the exchange of knowledge and, if necessary, also add their own experience and knowledge. The following applies to all participants: If you are unsure, always ask nicely and make yourself clear.

A successful code review leads to a higher quality, strengthens the relationship between reviewer and submitter and increases the understanding that all participants have for the project. Code reviews are not just a formality that requires a stamp before they are merged! They are an important aspect of modern software development that offers real added value for projects and teams.

### Ruleset

In the context of communication, simple rules should always be followed to ensure harmonious coexistence. It should also be noted that as a rule not only the reviewer and the submitter can hear and see the comments, but also other participants.

#### Avoid

- Do not refer to personal qualities and judgements.
- Don't make demands, make requests.
- Avoid sarcasm. (Due to other participants)
- Selective possession of the code should be avoided. (e.g. 'mine', 'not mine', 'yours')

#### Can and desired

- Asking questions.
- Ask for clarification.
- Giving explicit questions and answers.
- Try to understand the perspective of the submitter.
- Lead to philosophical or academic discussions offline.
- Identify ways to simplify the code while solving the problem.
- Clearly communicate and identify preferences.

## Conclusion

This is a possible and complex code review. As submitters, developers plan and tell the story and use the review as a learning experience. As a reviewer, developers should slow down, check carefully, automate as much as possible and take the opportunity to improve the team.
With their help you are able to be more open and understanding towards personal challenges and technical struggles that every developer has to handle with. Regardless of whether it is a junior or a senior developer.

Hopefully the ideas collected and presented here will help you expand your community and increase your effectiveness.
