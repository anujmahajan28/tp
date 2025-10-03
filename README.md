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
