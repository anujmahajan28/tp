Subject: Update on Test Case Slicing and Current Challenges

Hi Ashish,

I wanted to share a quick update regarding the test case slicing activity and the challenges I’m currently facing:
	•	While working on the test case slicing, I observed that there are additional possible scenarios that need to be covered to ensure complete analysis.
	•	I am rechecking the entire flow to confirm that all cases, including availability and mandatory fields, are properly captured.
	•	For better clarity, I’m also adding tables in the description section to give a detailed view of each page, which helps in easy understanding and verification.
	•	The test cases were returned to me mainly because a few business rules and variations were not fully aligned or clearly defined in the Gherkins.
	•	I am now aligning all scenarios with the business rules and ensuring the Gherkins are written properly.
	•	I’m continuously taking reviews and suggestions from Taher, who is helping me identify missing parts and improve the structure.
	•	I’m focusing on being more accurate, positive, and detail-oriented while implementing these changes to make the test cases comprehensive and clear.

Please let me know if there’s anything specific you’d like me to focus more on.

Thanks & Regards,
[Your Name]


SELECT

    R.REQUEST_ID,
    R.STATUS,
    COUNT(CPV.VERSION_TYPE) AS TOTAL_VERSIONS,
    CASE 
        WHEN R.STATUS = 'Draft' AND COUNT(CPV.VERSION_TYPE) = 0 THEN '✅ PASS - No versions persisted'
        WHEN R.STATUS = 'Draft' AND COUNT(CPV.VERSION_TYPE) > 0 THEN '❌ FAIL - Versions should NOT be persisted'
        ELSE '⚠️ Not a Draft request'
    END AS RESULT
FROM CREDITPROTECTION.REQUEST R
LEFT JOIN CREDITPROTECTION.CREDIT_PROTECTION_VERSION CPV 
    ON R.CREDIT_PROTECTION_ID = CPV.CREDIT_PROTECTION_ID
WHERE R.REQUEST_ID = :REQUEST_ID
GROUP BY R.REQUEST_ID, R.STATUS;


SELECT 
    R.REQUEST_ID,
    R.STATUS,
    COUNT(CPV.VERSION_TYPE) AS TOTAL_VERSIONS,
    LISTAGG(DISTINCT CPV.VERSION_TYPE, ', ') WITHIN GROUP (ORDER BY CPV.VERSION_TYPE) AS VERSION_TYPES,
    CASE 
        WHEN R.STATUS = 'Submit to CC' 
             AND ('LAST_DECIDED' IN (SELECT VERSION_TYPE FROM CREDITPROTECTION.CREDIT_PROTECTION_VERSION WHERE CREDIT_PROTECTION_ID = :CREDIT_PROTECTION_ID)
              AND 'CURRENT' IN (SELECT VERSION_TYPE FROM CREDITPROTECTION.CREDIT_PROTECTION_VERSION WHERE CREDIT_PROTECTION_ID = :CREDIT_PROTECTION_ID)
              AND ('WORKING' IN (SELECT VERSION_TYPE FROM CREDITPROTECTION.CREDIT_PROTECTION_VERSION WHERE CREDIT_PROTECTION_ID = :CREDIT_PROTECTION_ID)
                   OR 'PROPOSED' IN (SELECT VERSION_TYPE FROM CREDITPROTECTION.CREDIT_PROTECTION_VERSION WHERE CREDIT_PROTECTION_ID = :CREDIT_PROTECTION_ID))
             )
        THEN '✅ PASS - Versions persisted correctly'
        WHEN R.STATUS = 'Submit to CC' AND COUNT(CPV.VERSION_TYPE) < 3 
        THEN '❌ FAIL - Versions not fully persisted'
        ELSE '⚠️ Not a Submit to CC request'
    END AS RESULT
FROM CREDITPROTECTION.REQUEST R
LEFT JOIN CREDITPROTECTION.CREDIT_PROTECTION_VERSION CPV 
    ON R.CREDIT_PROTECTION_ID = CPV.CREDIT_PROTECTION_ID
WHERE R.REQUEST_ID = :REQUEST_ID
GROUP BY R.REQUEST_ID, R.STATUS;


Hi Ashish, good morning.
i have not been feeling well for the past few days due to viral, so I have a doctor’s appointment around 10:30 AM today.
Is it okay if I step out for a while and log back in by 11:15 AM?

कालः अपि प्रतिकूलगमनं आरब्धवान्!”
(Even time has started moving in the opposite direction!

Yesterday, I worked further on the design part and shared some cases with Taher for review. I also reviewed the folder and worked on the NRT part in both UAT and China environments. Today, I’ll continue with the same tasks and review any feedback or changes that come up.

This video, "JavaScript Functions Crash Course" by freeCodeCamp.org, is 1 hour, 36 minutes, and 54 seconds long. It covers a comprehensive range of JavaScript function topics, from fundamentals to advanced concepts like closures and recursion.
Here's a suggested plan to finish the video in 2 days:
Day 1: Fundamentals and Core Concepts (Approx. 48 minutes of video)
 * Watch up to the section on Arrow Functions/Nested Functions/Function Scope. This would cover:
   * Introduction and course overview [00:00:00 - 00:03:17]
   * Fundamentals of JavaScript functions [03:17]
   * Clarifying terminologies (functions vs. methods, parameters vs. arguments) [03:30]
   * Function declarations and executions [03:48]
   * Call stack [03:55]
   * Arrow functions [03:55]
   * Nested functions and function scope [03:55]
 * Review and Practice: After watching, take some time to review the concepts and try out the code examples on your own.
Day 2: Advanced Concepts and Application (Approx. 48 minutes of video)
 * Watch the remainder of the video, starting from Closures. This would cover:
   * Closures [03:59]
   * Callback functions and higher-order functions [03:59]
   * Pure functions [04:03]
   * Immediately Invoked Function Expressions (IIFE) [04:03]
   * Recursion [04:08]
 * Review and Practice: Again, review the concepts and practice implementing them in your own code.
Stand-up Call Details for the Next 2 Days:
Here's a template for your daily stand-up calls, focusing on your progress with the video:
Day 1 Stand-up (e.g., Friday morning):
 * What I did yesterday (or plan to do today): "Today, I plan to watch the first half of the 'JavaScript Functions Crash Course' video, focusing on the fundamentals, function declarations, and arrow functions. I'll also spend time practicing the code examples."
 * What I'll do today (if applicable, for a morning stand-up): (Same as above, or if you already started, describe what you've completed.)
 * What I'll do tomorrow (for an evening stand-up): "Tomorrow, I'll continue with the second half of the video, covering closures, callbacks, and recursion, and then dedicate time to practice."
 * Any blockers: "No blockers currently, but I'll reach out if I get stuck on any of the concepts."
Day 2 Stand-up (e.g., Saturday morning):
 * What I did yesterday: "Yesterday, I completed watching the first half of the 'JavaScript Functions Crash Course' video, covering up to arrow functions and function scope. I also practiced some of the basic function examples."
 * What I'll do today: "Today, I will finish the video by watching the sections on closures, callback functions, pure functions, IIFE, and recursion. My goal is to understand these advanced concepts and then practice implementing them."
 * Any blockers: "No blockers at the moment. I'll focus on understanding the more complex topics today."
Remember to adjust the details based on your actual progress and any challenges you encounter.

Today, I watched the remaining part of the JavaScript video, starting from Closures. It covered closures, callback functions, higher-order functions, pure functions, IIFEs, and recursion. I also continued working on the NRT cases and have almost completed them.
=IF(AND(ISNUMBER(D2), ISNUMBER(E2)), E2 - D2, "")

I’ve started with the basics—focusing on core recommended locators like getByRole, getByText, and getByLabel. I’m also learning how Playwright handles dynamic elements with auto-wait and retry logic. I’ve planned to finish this documentation in 2 days, with hands-on practice to better understand their usage.

<img width="612" height="408" alt="image" src="https://github.com/user-attachments/assets/bffe75d0-0bcd-4ef4-9a75-4d793403c60a" />


🐞 Bug Title

[GREENLIGHT] [Auto Approval] Greenlight not auto-approved after reaching auto approval date when Informal

⸻

📝 Description

In a Greenlight request where the Greenlight status is Submitted and marked as Informal, once the configured auto-approval date is reached, the system does not auto-approve the Greenlight as expected. This causes the workflow to remain stuck at the submitted stage.

⸻

🔁 Steps to Reproduce
	1.	Create a Greenlight Request and fill in required details.
	2.	Ensure the Greenlight status is set to Submitted.
	3.	Set the Greenlight Formal/Informal field to Informal.
	4.	Wait until the auto-approval date is reached.
	5.	Check the status of the Greenlight.

⸻

✅ Expected Result

Once the auto-approval date is reached, the Greenlight should automatically transition to Approved, especially for Informal requests.

⸻

❌ Actual Result

The Greenlight remains in Submitted status, and does not get auto-approved, even after the auto-approval date is reached.


Also verified if the cases are properly aligned with the test case design rules, and planned updates if any further changes are needed.

🔹 Tempo Log Update 1 – E2ECC-64072
Time: 4h
Task: Sanity – Facilities
Performed high-level sanity for Facility/Sublimit types (New, Renewal, etc.).
Validated field details, error highlights, copy-to-proposed, and summary updates.
Tested duplication, deletion, rearrangement, and submit validations.

⸻

🔹 Tempo Log Update 2 – EZECC-61047
Time: 3h
Task: Sanity – Compliance
Tested compliance tab visibility based on request type.
Validated section-wise data entry, edit, signature actions, and signing flow.
Checked “Back to Draft” and conditional field behaviors.


Then I check that creator of request is by default added as stakeholder and their details displayed in the “Stakeholder” fields


Hi [Manager’s Name],
Just wanted to inform you that I have training scheduled on the following dates:
	•	24th July – 10:00 AM to 6:00 PM
	•	25th July – 10:00 AM to 6:00 PM
	•	1st August – 10:00 AM to 6:00 PM

Please let me know if anything is required from my side in advance.

Thanks!

Thank you for reaching out. I will be unavailable today due to a full-day scheduled training and may not be able to respond promptly. For any urgent matters, please contact RANE Nikhil.
Hi team, I’m currently attending an in-person meeting and will be unavailable until 12:00 PM. I’ll get back to you upon my return. Thank you for your understanding.


✅ Summary:

Verify visibility of the “For Decision” toggle on the Legal Entities page immediately after creating a new request, without adding any legal entity.

⸻

🎯 Objective:

To ensure the “For Decision” toggle is available on the Legal Entities page even when no legal entities are added.

⸻

🔁 Steps to Reproduce:
	1.	Given I created a new Request
	2.	When I navigate to the Legal Entities section
	3.	Then I check the presence of the “For Decision” toggle

⸻

✅ Expected Result:

The “For Decision” toggle should not be visible until at least one legal entity is added.

⸻

❌ Actual Result:

The “For Decision” toggle is visible even when no legal entity has been added.


Subject: Correction Required for Training Attendance – Selenium & BDD (24/07/2025)

Dear [Recipient Name/HR/Training Team],

I hope you are doing well.

I noticed that my training record for “Selenium & BDD” (24/07/2025, 10:00 AM) is showing as “No Show”, even though I had accepted the invitation and attended the session.

Could you please review and update the attendance status in the system to reflect my participation? I can provide any additional details or confirmation if required.

Thank you for your assistance.

Kind regards,
Anuj Mahajan



Subject: Request to Review Training Attendance for 24–25 July 2025

Dear [Recipient Name],

Thank you for sending the login details.

I see that attendance is based on the total time logged in for both days. On 24th July, I joined at 11:25 AM, and on 25th July, I joined at 1:26 PM because I had an urgent task that needed my immediate attention to avoid delays in the project.

Even with the late start, I attended the rest of the training sessions and made sure to cover all the material. I kindly ask if you could reconsider my attendance record to reflect my participation. I promise this won’t happen again, and I’ll make sure to attend fully in future trainings.

Thanks for your understanding and help.

Best,
Anuj Mahajan

![image](https://github.com/user-attachments/assets/11c809ea-3a9a-4fdf-ae2c-43ae9855449e)

Hello, I am engaged in onboarding formalities today and may not be able to respond promptly. Please expect a delay in my response. For any urgent queries, kindly reach out to REBBALA Chandrasekhar or CHOUDHARY Ashish. Thank you.


Thank you for the warm welcome and constant guidance. I’m glad to be part of BNPP and truly appreciate your support. I will make sure to give my best, take ownership of my responsibilities, and perform as per expectations.

Subject: Validation of Code of Conduct and Golden Rules

Hi Ashish,

I confirm that I have received, read, and understood the Code of Conduct and Golden Rules documents. I acknowledge their importance and will adhere to the guidelines as part of my responsibilities in the team.

Regards,
Anuj Mahajan


I am contributing as an Associate Test Engineer by designing and refining test scenarios, ensuring accuracy, clarity, and comprehensive coverage. I am involved in test execution, reporting, and documentation, while also gaining exposure to automation practices that improve efficiency. My strengths include analytical thinking, adaptability, and collaboration, enabling me to support quality delivery and continuous improvement within the Group.


Description:
After adding a new stakeholder with all required fields, the position is not updated when going to Results and back to Stakeholders.

Expected Result:
Stakeholder position should show correctly after coming back.

Actual Result:
Stakeholder position still shows wrong / not updated.


Subject: Leave Notification for Monday

Dear [Manager’s Name],

I would like to inform you that I will be on leave on Monday, [insert date] as I need to visit my college to collect my Leaving Certificate (LC) and Provisional Degree (PD) certificate, which are required for my background check.

Kind regards,
Anuj
Vivan Sankhe’s journey reflects steady growth in technology and innovation. Beginning with strong academics, he pursued Computer Science at MIT-WPU, maintaining a solid CGPA. Early internships at Elite Technosys gave him hands-on experience in data analysis, engineering, and full-stack development. Later, at Tata Steel, he applied machine learning to real-world manufacturing challenges, building scalable ML pipelines. His projects span fitness apps, developer platforms, and IoT-based systems, showing versatility across domains. International research at Texas A&M expanded his problem-solving in traffic systems. Beyond academics, he showcased leadership by coordinating HackMIT’23, balancing technical expertise with organizational skills 


Suniket Khadke’s journey highlights his growth into a skilled DevOps Engineer with expertise in automation, cloud, and CI/CD. After completing his B.Tech at GF’s Godavari College of Engineering, Jalgaon, he built strong foundations in cloud services, containerization, and orchestration. He mastered tools like Jenkins, Docker, Kubernetes, AWS, and Terraform, enabling him to design efficient, automated pipelines. His project work on declarative pipelines in Jenkins demonstrates his ability to streamline builds, testing, and deployments while ensuring scalability and high availability. Through continuous learning via bootcamps and certifications, Suniket has developed a results-driven approach to delivering reliable DevOps solutions 


Saloni Raj Singh is a Computer Science Engineering student at MIT World Peace University with a strong passion for building scalable, AI-driven, and cloud-based solutions. She gained hands-on industry experience during her internship at Piterion India, where she designed and automated systems for drone manufacturing using Teamcenter, ETL pipelines, and CAD workflow automation. Her projects, including an AI-based image captioning model and a dynamic QR code generator, highlight her technical problem-solving and innovative mindset. Saloni has also published research in Springer’s LNNS series, showcasing her academic contributions, while excelling in public speaking and technical writing 


I would like to refer Saloni Raj Singh as she has successfully completed her Computer Science Engineering degree at MIT-WPU and built a strong foundation in scalable technologies and AI-driven solutions. She gained valuable industry experience as a PLM Intern at Piterion India, where she automated workflows and enhanced efficiency in drone manufacturing systems. Her academic projects, including an AI-based image captioning model and a dynamic QR code generator, highlight her innovation and problem-solving skills. With a Springer LNNS publication, strong communication abilities, and proven adaptability, Saloni is a well-rounded candidate ready to contribute meaningfully.


I would like to refer Vivan Sankhe as he has successfully completed his Computer Science Engineering degree at MIT-WPU with strong academic performance and diverse practical experience. He has interned at Tata Steel, where he built machine learning pipelines for automated quality control, and at Elite Technosys, where he worked on data engineering and full-stack development. His projects, including a developer social network and a personalized fitness app, showcase technical versatility. With international research exposure at Texas A&M University and leadership experience organizing HackMIT, Vivan combines innovation, teamwork, and problem-solving skills, making him a strong candidate for this opportunity.


I would like to refer Sahil Ranawde as he has demonstrated strong academic performance, practical skills, and adaptability throughout his journey. A Computer Science Engineering student at MIT-WPU with a CGPA of 8.72, he gained hands-on industry exposure at Harbinger Group, where he contributed to building eLearning platforms with personalized dashboards. His projects, including a Bank Management System and Seminar Management tool, showcase his proficiency in Java, SQL, Node.js, and React. With certifications in Java, MySQL, UI/UX, and product design, along with achievements in sports, Sahil brings a balanced mix of technical expertise, problem-solving, and teamwork to any role.


I would like to refer Umesh Barhate as he brings strong Python expertise, database management, and applied problem-solving experience that align with quantitative research roles. At Cufront Healthcare, he developed scalable APIs, implemented task scheduling with Celery, and worked extensively with PostgreSQL/MySQL, building efficient pipelines to process structured data. He has led a small team, gaining experience in analytical thinking, model integration, and workflow optimization. With hands-on skills in Python, statistics, and automation, combined with the ability to manage data-driven systems and deliver reliable solutions, Umesh has the technical foundation and adaptability to excel in quantitative research projects.


I would like to refer Sarvesh Shimpi as he has built a strong foundation in Computer Engineering at MIT-WPU with a CPA of 8.34 and valuable hands-on experience. He worked as a Game Development Intern at IIT Gandhinagar, implementing AI and pathfinding algorithms to enhance gameplay efficiency. Sarvesh has demonstrated versatility through impactful projects in machine learning, deep learning, and full-stack development, including a disease prediction website, music generator, and e-commerce platform. His achievements at multiple IIT competitions and a published research paper further highlight his innovation and problem-solving skills, making him a promising candidate for this opportunity.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/3ed28e81-78b4-4049-843f-7a011bf71d2a" />

![Uploading image.png…]()


Final Presentation Script (Present Tense, with Sanity Testing)

(Start – 30–40 sec)
“Let me walk you through my project experience on MyCreditApp – the Request Module at BNP Paribas.
This module is used globally to create, structure, and decide on corporate credit requests.
It involves multiple user roles —
the Credit Analyst, who creates and structures the request;
the Relationship Manager, who validates compliance;
the Senior Credit Officer or Delegation Holder, who takes the final credit decision;
and the Middle Office (CTM), which updates all approved data in downstream systems like contracts and records.
In short, it’s the digital workflow for corporate credit approvals.”

⸻

(Testing Strategy – ~1 min)
“Our main goal in testing this module is to make the process faster, more reliable, and easier to maintain.
Initially, most tests are manual, which makes each release cycle lengthy and repetitive.
So our current testing strategy focuses on five key areas:
	1.	Optimizing manual test cases – by removing duplicates and rewriting steps for better clarity.
	2.	Executing Sanity and NRT tests – Sanity Testing helps verify that major functions work after every deployment, while NRT or Non-Regression Testing ensures older features still perform correctly after new changes.
	3.	Integrating Playwright automation – Playwright is a web automation framework that simulates real user actions on browsers to speed up repetitive testing.
	4.	Streamlining documentation – keeping all workflows, test cases, and reports organized and updated.
	5.	Tracking everything via Jira and Excel – Jira helps log defects, assign tasks, and track sprint progress, while Excel is used for execution summaries and defect analysis.

The purpose of this strategy is to improve accuracy, reduce testing time, and make our releases more predictable.”

(Understanding the Requirement – 45 sec)
“My first contribution was studying how the credit workflow operates end-to-end.
I analyzed how each user role interacts with the system and what business logic lies behind every screen.
This helped ensure that the test scenarios I worked on aligned with the real business flow, not just the UI.
Understanding this context early on helped us identify what truly needed validation during testing.”

⸻

(Test Scenario Design – 45 sec)
“Next came Test Scenario Design.
I helped create modular, well-structured test cases for request creation and approval.
A modular approach means each test focuses on a single function, so it’s easier to reuse and maintain.
We also worked on optimizing existing cases to remove redundancies.
This directly improved the speed and clarity of our Non-Regression Testing cycles.”

⸻

(Automation Exposure – 50 sec)
“I also got exposure to Automation using Playwright along with Gherkin syntax.
Gherkin is a language used in Behavior-Driven Development; it describes test scenarios in plain English using the ‘Given–When–Then’ format.
For example:
‘Given the user is on the Request Dashboard, When they submit details, Then the request is created.’
Even though I wasn’t directly coding the scripts, understanding how Playwright executes these Gherkin scenarios gave me a strong foundation for future automation work.”

⸻

(NRT Execution & Reporting – 45 sec)
“I was also responsible for executing Non-Regression Tests after each release.
We validated that all previously working features still behaved as expected.
Any issues found were logged in Jira, assigned to developers, and tracked until resolution.
Finally, I summarized all execution results, coverage, and defects in Excel reports for our testing dashboard.”

⸻

(Challenges & Solutions – 50 sec)
“One of our key challenges was managing a very large set of manual test cases, many of which were outdated or overlapping.
Another was incomplete documentation that made onboarding and reporting slower.
To solve this, I helped reorganize the test repository, updated steps to match the current build, and added proper traceability in Jira.
We also identified which test cases were suitable for future automation using Playwright — laying a foundation for faster testing cycles.”

⸻

(Learnings & Impact – 45 sec)
“This project helped me develop a clear understanding of the entire QA lifecycle — from requirement analysis and test design to execution and reporting.
I strengthened my skills in SQL for backend validation, Python for scripting logic, and Excel for test analysis.
I also learned how to think critically about test efficiency and business impact rather than just pass/fail results.
Overall, my work helped improve testing accuracy, documentation quality, and readiness for automation in upcoming releases.”


Impact on the Project:
Through my involvement in the Request module testing, I helped streamline manual test execution and improve the structure of test scenarios, making them more reusable and easier to maintain.
By ensuring consistent sanity and NRT coverage for every release, I contributed to better release stability and early defect detection.
My documentation updates and tracking via Jira and Excel helped bring more transparency to the testing cycle.
Overall, my contribution supported a smoother test process, reduced effort duplication, and strengthened the foundation for future automation integration.
⸻

(Closing – 20 sec)
“In summary, my time on the MyCreditApp Request Module gave me hands-on experience in real-world QA processes, exposure to automation tools, and a deeper understanding of how quality assurance drives reliability in financial systems.”


![image](https://github.com/user-attachments/assets/f8813990-531f-40e4-b89c-7f194305c8df)



Good afternoon everyone, My name is Anuj Mahajan working as an Analyst at GBIT Corporate credits in MCA project.
I’ll be sharing my experience and contribution to the Request Module of MyCreditApp.

This module is one of the key parts of the application. It provides all the functionalities required to create, structure, and decide a corporate credit request with user roles to ensure each credit request moves through the right review and approval stages.

When I started working on this project, my first step was to understand the entire credit workflow — from how a request is initiated, reviewed, validated, and finally approved.
This stage is important because it helped me see how data flows across roles and what checkpoints are crucial for validation. Once I had that clarity, I began translating these functional steps into test scenarios that covered both business logic and user interactions.

The next step is test case design.
Here, my focus is on creating modular and reusable test cases that could be easily maintained and scaled for future releases.
Each test case is written using Gherkin syntax — Given, When, Then — which helped maintain a clear, behavior-driven format. This structure not only improved readability for manual testers but also ensured our test cases are written in a way that could directly support automation later.

Even I made sure that the cases are aligned with Playwright automation standards. For example, I included selector references, action sequences, and expected outcomes in a way that could be easily converted into Playwright steps by the automation team and saved their time during automation.

Once the design is in place, I worked on optimizing existing manual test cases.
Many scenarios were repetitive or overlapping, so I streamlined them, removed duplication, and merged related cases where possible. This improved test coverage while keeping the documentation lean and effective.

During every sprint and release, I am actively involve in executing Non-Regression Tests and Sanity checks.
Each cycle involved validating critical functionalities, logging defects in JIRA, and maintaining detailed reports in Excel for analysis and traceability.
These reports helped the team identify recurring issues and track how fixes were performing across builds.

Alongside this, I also contributed to streamlining the documentation process.
We structured the repository in a way that anyone new joining the project could quickly understand the test flow, business logic, and execution order.
This made our testing process faster and more consistent, especially during tight release timelines.

One thing I particularly enjoyed was how closely this work connected testing with business understanding. Every test scenario reflected an actual use case from the credit lifecycle. It wasn’t just about clicking through screens — it was about ensuring that every approval, validation, and decision aligned with business rules and data accuracy.

Through this project, I got to strengthen both my technical and analytical skills.
Technically, I worked with tools like Python, SQL, JavaScript, JIRA, and Excel, and learned how they fit into the QA workflow.
Analytically, I learned how to think beyond pass/fail — to look at why an issue happens, how it affects downstream processes, and how to prevent it in the future.

Working on this module also taught me the value of collaboration. I regularly interacted with developers, automation testers, and product owners to clarify requirements and align priorities. These discussions helped improve our understanding of dependencies and reduced turnaround time during defect resolution.The experience really helped me grow as a tester.


And I feel the sense of ownership and helped me contribute meaningfully to improving the quality and reliability of MyCreditApp’s credit request process. More importantly, it taught me how thoughtful planning and teamwork can make testing not just a checkpoint, but a reliable part of the delivery process.

Thank you.

We have one person who also has similar experience, so I would like to hand it over to Vishakha to take it further.


Hello everyone,
My name is Anuj Mahajan, and I am working as a Test Analyst at Banking Platform IT Corporate Credits for the MyCreditApp application. I’ll be sharing my experience and contribution to the Request Module of MyCreditApp.

The purpose of the “Request to Decision” module is to retrieve all the requests that have been created or validated for all coverage and business lines originating sites. It covers end-to-end workflow from request creation to decisions from a credit committee. The legal entities and facilities will have their own data journey with data coming from referential (current), input by the analysts (proposed), and input by decision makers (recommended / decided). And the decided data will be fed to other systems after final decision.

When I started working on this project, my first step was to understand the entire MyCreditApp workflow. Once I had that clarity, I began translating these functional steps into test scenarios that covered both business logic and user interactions.

The next step is test case design. Here, my focus is on creating modular and reusable test cases that could be easily maintained and scaled for future releases. Each test case is written using Gherkin syntax — Given, When, Then — which helped maintain a clear, behavior-driven format. This structure not only improved readability and maintainability but also made it easily understandable by automation testers.

I even made sure that the cases are aligned with automation standards. For example, I included selector references, action sequences, and expected outcomes in a way that could be easily converted into steps by the automation team and saved their time during automation.

Once the design is in place, I work on optimizing existing manual test cases. Many scenarios were repetitive or overlapping, so I streamlined them, removed duplication, and merged related cases where possible. This improved test coverage while keeping the documentation lean and effective.

I am actively involved in the NRT cycle, validating critical functionalities, logging defects in JIRA, and maintaining detailed reports in Excel for analysis and traceability. These reports helped the team identify blocker or critical issues and track how fixes were performed across builds.

Alongside this, I also contributed to streamlining the documentation process. We structured the repository in a way that anyone new joining the project could quickly understand the test flow, business logic, and execution order. This made our testing process faster and more consistent, especially during tight release timelines.

One thing I particularly enjoyed was how closely this work connected testing with business understanding. Every test scenario reflected an actual use case from the credit lifecycle. It wasn’t just about clicking through screens — it was about ensuring that every approval, validation, and decision aligned with business rules and data accuracy.

Through this project, I have strengthened both my technical and analytical skills.
Technically, I worked with tools like Python, SQL, JavaScript, JIRA, and Excel, and learned how they fit into the QA workflow. Analytically, I learned how to think beyond pass/fail — to look at why an issue happens, how it affects downstream processes, and how to prevent it in the future.

Working on this module also taught me the value of collaboration. I regularly interacted with developers, automation testers, and product owners to clarify requirements and align priorities. These discussions helped improve our understanding of dependencies and reduced turnaround time during defect resolution. The experience really helped me grow as a tester.

And I feel the sense of ownership and helped me contribute meaningfully to improving the quality and reliability of MyCreditApp’s credit request process. More importantly, it taught me how thoughtful planning and teamwork can make testing not just a checkpoint, but a reliable part of the delivery process.

Thank you.
We have one person who also has a similar experience, so I would like to hand it over to Vishakha to take it further.


1. CONTRACT MODULE

The Contract module represents the legally binding agreement created after a credit request is approved. It defines the relationship between the bank and the borrower, along with all financial and legal terms of the loan or credit facility.

Each contract starts from a validated Request and captures the essential details required before execution.

Key Terms and Meanings:
	•	Contract ID: A unique identifier automatically generated by the system. It helps track and reference the contract across different applications and audit trails.
	•	Contract Type: Defines what kind of agreement it is — for example, a Loan Agreement, Credit Facility Agreement, or Guarantee Agreement.
	•	Contract Name: The title used to identify the contract (for example, “ABC Ltd Term Loan Agreement”). This is shown throughout the system for easy reference.
	•	Governing Law: Indicates under which country’s or state’s legal system the contract is enforceable.
	•	Jurisdiction: Specifies where any legal disputes will be handled.
	•	Originating Site: The site or business line where the initial credit request originated. This helps in tracking cross-border or regional transactions.
	•	Implementing Site: The entity or branch responsible for executing and maintaining the contract once approved.
	•	Linked Request: Connects the contract to the original approved credit request. This ensures only validated transactions are converted into contracts.
	•	Borrower / Co-Borrower: The legal entities who are taking the loan or credit facility. These names appear in all related documentation.
	•	Facility: Represents the specific loan, credit line, or exposure created under the contract. Each facility has its own amount, tenor, and repayment terms.
	•	Execution Date: The date when the contract becomes legally binding. It marks the start of the contractual obligations.
	•	Contract Status: Indicates the progress of the contract, such as Draft, Under Validation, or Executed.
	•	Summary Tab: Provides a consolidated view of all linked facilities, documents, and covenants before final validation.

Purpose and Use:

The Contract module serves as the foundation of the deal. It transforms a credit request into a legally valid agreement. It also connects downstream modules such as Legal Documents and Covenants, ensuring that all contractual, legal, and compliance requirements are linked in one place.

In the MyCreditApp system, users typically verify key information, link the approved request, and check whether all legal documents and covenants are attached before executing the contract.

⸻

2. LEGAL DOCUMENT MODULE

The Legal Document module captures, monitors, and validates all legal paperwork associated with a contract or facility. It ensures that the bank holds all necessary documents required to make the credit legally enforceable.

Key Terms and Meanings:
	•	Legal Document Checklist: A list of all documents that must be received and validated for the contract (e.g., Termsheet, Credit Agreement, Guarantee Documents).
	•	Document Type: Defines the category of the document such as Credit Agreement, Facility Letter, Guarantee, or Pledge Agreement.
	•	Expected Date: The target date when the document is expected to be received.
	•	Received Date: The actual date on which the document was received.
	•	Reception Status: Shows whether the document has been received, is pending, or is under validation.
	•	Need Hardcopy: Indicates if a physical signed copy of the document is required, as some documents must be physically stored for legal compliance.
	•	Safekeeping Status: Shows whether the document has been securely stored (physically or digitally) in the safekeeping vault or document repository.
	•	Docstore Link / Attachment: A digital storage location or reference where the scanned copy is kept.
	•	Gap (Days): Displays the number of days between the expected and actual received dates, helping monitor document delays.
	•	Comments: Used to capture reviewer notes, clarifications, or exceptions made during validation.
	•	Validation / Review Flag: Marks whether the document has been checked and approved by the legal or credit control team.

Purpose and Use:

This module ensures that every executed contract has complete and verified documentation, which is essential for regulatory compliance, audit trails, and future dispute handling.

Without all mandatory legal documents being received and validated, the contract cannot move to an executed state.
It helps the bank confirm that the credit exposure is legally enforceable and properly recorded.

In the UI, users can navigate through sections like General, Borrowers, Assets, Covenants, and Summary, each reflecting the document’s linkage to different parts of the contract.

⸻

3. COVENANT MODULE

The Covenant module defines the conditions and obligations that the borrower must meet during the life of the contract. These are part of the agreement between the bank and the borrower to ensure continued financial health and compliance.

Covenants act as post-sanction monitoring tools, helping the bank manage credit risk even after funds are disbursed.

Key Terms and Meanings:
	•	Covenant: A condition or clause within the contract that specifies an obligation for the borrower. For example, “The borrower must maintain a debt-to-equity ratio below 2.0.”
	•	Covenant Type: The main classification — Financial, Non-Financial, or Sustainability-linked (SLL KPI).
	•	Financial Covenant: Based on the borrower’s financial performance, such as profitability ratios or leverage. These are quantitative checks.
	•	Non-Financial Covenant: Relates to operational or behavioral obligations like submitting reports or maintaining insurance.
	•	SLL KPI (Sustainability Linked Loan KPI): Linked to ESG or sustainability goals like reducing emissions or improving social impact.
	•	Monitorable Flag: Indicates if the covenant is actively tracked and reported periodically.
	•	Threshold / Trigger: The limit or condition that determines whether a covenant is in compliance or breached.
	•	Periodicity: Defines how often the covenant is checked — for example, quarterly, semi-annual, or yearly.
	•	Due Within (Days): The number of days after the fiscal period within which the borrower must provide compliance information.
	•	Covenant Calendar: An automatically generated schedule that helps track due dates for covenant reporting.
	•	Margin Adjustment: A pricing clause that links covenant performance with interest margin — if the borrower performs better, the interest margin may decrease.
	•	Springing Covenant: A conditional covenant that activates only if a particular event occurs, such as a drop in credit rating.
	•	Covenant Status: Shows whether the covenant is Active, Breached, or Waived.

Purpose and Use:

Covenants are a critical part of credit risk management. They protect the bank by ensuring borrowers remain financially stable and transparent throughout the loan period.
If a covenant is breached, it can trigger actions like additional reporting requirements, interest rate adjustments, or even default procedures.

In the UI, the covenant page includes options to create new covenants, select from pre-defined templates, and configure details like type, thresholds, and periodicity. It also has a Covenant Calendar for tracking due dates and a Comment section for additional notes or explanations.

⸻

Overall Relationship (End-to-End Link)
	•	A Request is raised by the Relationship Manager to seek credit approval.
	•	Once approved, it becomes a Contract, representing the legally binding agreement between the bank and borrower.
	•	The Legal Document module ensures that all required agreements, guarantees, and security papers are received and validated before the contract is executed.
	•	The Covenant module tracks all ongoing conditions and obligations after the contract is active to ensure continuous compliance.

Together, these three modules ensure the deal lifecycle is legally compliant, risk-monitored, and auditable — from approval to post-disbursement monitoring
