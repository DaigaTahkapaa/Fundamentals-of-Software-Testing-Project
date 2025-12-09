## 1. How was your experience testing the given Webapp?
I would have loved to have some requirements to be exactly sure what is the expected behaviour when doing certain things. Felt more like documenting observed behavior than actually testing if something is behaving as it should. 
It also felt intrusive to do it on a live webpage. For Login page it started to ask me if I am a robot, and had to solve little visual puzzles to be able to proceed. 
     

## 2. How did you write or manage your test case? Describe the process.
I followed the provided template structure while adapting it to the actual webpage behavior. The process involved:
- Examining the GitLab webpage structure and UI elements - saved HTML pages locally for detailed inspection
- Used GitHub Copilot in VS Code to analyze the locally saved HTML files looking for potential error messages and edge cases by identifying where validation messages appear, how modals are trigegred, and how different UI elements behave
- Inspected the registration form’s POST request in the browser DevTools Network tab to verify server‑side responses for fields not covered by frontend validation when registering a new user
- Reading GitLab's documentation (https://docs.gitlab.com/user) to understand expected functionality
- Defining clear scope - what to test and what to exclude, like only CRUD for issues
- Writing precise step-by-step instructions with unique identifiers extracted from the HTML analysis
- Organizing tests logically by CRUD operations with Positive/Negative subsections
- Using variables consistently to avoid hardcoding values throughout test cases
- Considering edge cases like empty inputs, very long names, duplicate names, special characters, and reserved keywords
    

## 3. Do you recommend any other tools or styles for Test case management. 
I am not really in a position to recommend any other tools. My only other expereince with testing - we used Confluence to write test cases and Jira boards for bug reports. I cannot say I recommend that combination, or at least the way it was implemented for us. Rbot framework actually seems to be like something worth learning more about, and actually trying on some small personal project.    


## 4. Which IDE (Visual Code or Atom or else) have you used to edit files?
I have used Visual Studio Code with RobotCode extension. 
I know these were not true test suits for robot, but it was easier to write the test cases when the "code" was colorcoded (e.g. variables in different color and standing out). This required me to change file extensions to . robot, in the end I changed back to .txt.

     
## 5. Did you find any trouble? how did you solve the trouble?
The main trouble was the feeling that I do not fully know if something is an expected behaviour or not. 
In the end I assumed that all the behaviour I can observe is as per design/requitrements/specifications, yet I made 2 recommendations that maybe could be considered low priority bugs.
When testing, it felt as if different parts of the site had been built by different people, because their behaviour and style didn’t fully match.
I also did not quite figure how to best document pre-conditions in this case where, for example testing of the Issues Page requires a project to be created. Should it be created at the end of Project testing suite  (assuming they are run in sequential order)? Should it be at the start of the Issues test suite? How detailed should the description be? I opted for putting quite detailed description in the Issues suite, bet maybe I should have simply assumed it exists as test data.

## 6. Did you find any trouble using Github? have you used Github before? where?
No, I did not find use of GitHub problematic for this particular project, or for any personal projects that do not require collaboration.
GitHub has been used before in classes like Fundamentals of Programming or Dynamic Web Applications with JavaScript. 
Dynamic Web Applications with JavaScript have even made me comfortable with using Git Bash. Yet I still need lots of practice when it comes to collaboration, and projects that would have branches. 
      

## 7. If in the future if you need to automate these test cases, which framework or language will you use? and describe why (Robot Framework, Cypress, Selenium, or any other )
I cannot answer this at this point. I would need to learn about Cypress, Selenium, and other frameworks to be able to draw meaningful comparisons. Would also likely depend on what I need to test, and what language the testing object is written in, and what testing level it is. 


## 8. Kindly search the term `Tester` `Automation Tester` glassdoor and LinkedIn or any other job search website. Currently, list the skills and competencies that are most in-demand in software testing

Instead of relying on Glassdoor or LinkedIn job ads, I used ESCO (European Skills, Competences, Qualifications and Occupations), an official EU classification system. ESCO provides a much clearer overview of the essential/optional skills required for the Software Tester occupation (code 2519.7).

### Soft skills
[Työmarkkinatori](https://tyomarkkinatori.fi/en/personal-customers/professional-information/professions/software-tester) had a nice description of soft skills that a tester should possess including:
- Precision and attention to detail
- Problem‑solving skills
- Analytical thinking
- Communication skills
- Cooperation and teamwork skills
[ESCO](https://esco.ec.europa.eu/en/classification/occupation_main) [software tester][def]
lists additional skills like:
- Ability to follow structured processes
- Critical thinking
- Adaptability in changing project environments
- Ability to document findings clearly
- Collaboration with developers and stakeholders


### Technical skills
[ESCO][def] also mentions a myriad of technical skills, divided into essential and optional categories:

#### Essential Skills and Knowledge
- Execute software tests
- Perform software unit testing
- Provide software testing documentation
- Report test findings
- Levels of software testing
- Software anomalies
- Software architecture models
- Software metrics

#### Optional Skills and Knowledge
- Debug software
- Develop ICT test suite
- Develop automated software tests
- Execute integration testing
- Perform software recovery testing
- Perform software usability testing
- Use software design patterns
- Knowledge of programming languages (for example: Python, Java, JavaScript, C#)
- Test automation frameworks (for example: Selenium, Robot Framework, Cypress)
- Agile development practices such as Scrum or DevOps
- Understanding of software components interaction (frontend, backend, APIs)


### Skill share
What I found interesting was the skill share diagram for the software tester on ESCO, which showed working with computers being only 50%, when one might think it is much larger share 
![Skill share - software tester](/Image/software_tester_skillshare.png)

## 9. **Let's assume** that if you are going to continue with the career in Software Testing, which technical and soft skills do you need to fill up the blank in your resume?
If I were to continue building a career in Software Testing, the main blanks I would need to fill are on the technical side. In fact, I would need to work on essentially all of the technical skills listed for the Software Tester role.

My previous work experience has required me to use and develop nearly all of the soft skills associated with software testing. That is where I actually feel confident as I have already applied these skills in real projects workingin cross-functional, cross-boundaries teams.

Example from my experience
In the ISTQB‑2025 Fundamentals of Software Testing training the Percipio platform, there was a section about how testers and developers often perceive each other. The assignment asked for a reflection, and it made me think about my own experience.
My collaboration with developers has always been very positive. This might be because I worked in a role closer to a business analyst–type tester, where part of my job was clarifying requirements and identifying issues that came from ambiguous or incomplete specifications—not from developer mistakes. In practice, this meant I could help bridge the gap between business needs and technical implementation, which made it feel like a cooperation and not criticising ones work.


## 10. Write short Learning Reflection and  Free words Do you think that project helped in putting theoretical knowledge into practice? Describe? (is there anything else that you would like to share with us concerning the current study module). e.g. regarding the quality of content and your learning (or) improvement ideas? 
In my opinion the study unit would be greatly improved if the project was something that actually trully applied robot (or some other) framework. 
While the theoretical material was solid, I do not feel this course really advanced my skills as a tester - systematically writing down step by step instructions that will be executed by a human is not new to me, in fact it is a task I thrive with, but I still do not trully know how to write any automated test. It would great if testing course could be "integrated" into something like Dynamic Web Applications with JavaScript, because in that class on one of my projects I got a comment that I should start to integrate testing in my roject, but I still do not really know how to start with something like that. 




 







[def]: https://esco.ec.europa.eu/en/classification/occupation?uri=http%3A%2F%2Fdata.europa.eu%2Fesco%2Foccupation%2F106f79e4-6264-45f1-9e7a-297435cd684b