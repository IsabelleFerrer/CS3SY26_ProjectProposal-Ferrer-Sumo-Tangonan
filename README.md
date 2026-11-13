# CS3SY26_ProjectProposal by AlMendoza


## Project Proposal Template

### Project Title or Name of the Application	: TaSched (Task Scheduler)
### Section			   	      : Beryllium
### Group Members			    : Be09 Ferrer, Be24 Sumo, Be25 Tangonan
### Date (Proposal Date)  : Nov 13, 2026

### Project Description:

**Summary and the Need for the Project:** Some students struggle to balance multiple assignments with overlapping deadlines and varying importance. Ineffective scheduling and prioritization may lead to academic stress/burnout, procrastination, and decreased learning results. Existing scheduling tools often base prioritization on deadlines or rely on self-judgment and discipline rather than a system that converts task attributes into a well-structured schedule. TaSched is an application that addresses these needs by providing a formula-driven system that automatically generates optimized schedules/plans, helping students effectively manage and organize their tasks. It allows the user to input their assignments, projects, quizzes, and other academic-related tasks to monitor deadlines and their progress. It incorporates mathematical calculations to determine which tasks to prioritize.


**Target Users:** TaSched is designed for students who are looking for scheduling support to help manage their complex academic workloads and achieve work-life balance along with higher levels of performance. Specifically, it targets:
- Students with a heavy workload: Students with several subjects and competencies daily who are prone to feeling overwhelmed if their time-management skills are poor.
- Procrastinators: People who have no fixed schedule yet and thus put off doing tasks to the last minute.
- Students with learning differences: People who have difficulties in estimating time, regulating attention, executive function, organization, and task organization.
- Self-paced students: Learners who lack a fixed classroom schedule and learn at their own pace.


**System Components, Features and Expected Outputs:**

Classes, Attributes, and Methods:

Task Class
- Attributes: task_name (String), task_desc (String), task_deadline (Integer - minutes before due), task_duration (Integer - in minutes), task_importance (Integer - using a likert scale), task_difficulty (Integer - using a likert scale), task_complete (Boolean), task_priorityIndex (Float), assigned_schedule (String).
- Methods: calculate_priorityIndex(), get_taskDetails(), update_taskName(new_name), update_taskDesc(new_desc), update_taskDeadline(new_deadline), update_taskDuration(new_duration), update_taskImportance(new_importance), update_taskDifficulty(new_difficulty).

Weights Class
- Attributes: w1_deadline (Float), w2_duration (Float), w3_importance (Float), w4_difficulty (Float).
- Methods: set_w1Deadline(custom_deadline), set_w2Duration(custom_duration), set_w3Importance(custom_importance), set_w4Difficulty(custom_difficulty), resetWeights(), get_w1Deadline(), get_w2Duration(), get_w3Importance(), get_w4Difficulty().

Schedule Class
- Attributes: task_list (List), generatedSchedule (Dictionary List).
- Methods: rankTasksByPriority(), delete_task(task_obj), add_task(task_obj), complete_task(task_obj), generateSchedule(), refreshSchedule().

Time Class
- Attributes: mon_time (Integer - in mins), tue_time (Integer - in mins), wed_time (Integer - in mins), thu_time (Integer - in mins), fri_time (Integer - in mins), sat_time (Integer - in mins), sun_time (Integer - in mins).
- Methods: set_monTime(new_time), set_tueTime(new_time), set_wedTime(new_time), set_thuTime(new_time), set_friTime(new_time), set_satTime(new_time), set_sunTime(new_time), get_monTime(), get_tueTime(), get_wedTime(), get_thuTime(), get_friTime(), get_satTime(), get_sunTime().


Class Interactions & Expected Outputs: When a user inputs task details, the Schedule class instantiates a Task object. The task object uses the current coefficients from the Weights class to calculate its Priority Index (PI) using a formula, then sorts all tasks in descending order of their PI, and using the Time class, maps them into user-defined time availability daily. The expected output should be a clear, daily schedule, displaying each task’s name, description, deadline, assigned schedule, and computed Priority Index.

**Class Diagram:**

<img width="1310" height="485" alt="TaSched Class Diagram" src="https://github.com/user-attachments/assets/14e4399f-2cf4-4f51-832e-a7a0778fb9f0" />

### Goals:

In the long run, this project aims to reduce academic burnout and stress among students by using a mathematical formula to automate task prioritization and scheduling rather than relying on personal judgment. This helps address common problems among students, such as missed deadlines, difficulty deciding which task to start first, and cramming several tasks into one day—all major factors in burnout and stress. It also aims to develop better time-management skills as students internalize personal scheduling skills that work for them. This integrates a disciplined approach of decomposing tasks and staying on top of deadlines into their system — important skills that will prove handy to them in their professional lives. Overall, optimized scheduling makes sure that tasks rated highest on the importance scale are done at the best possible time to utilize resources and have ample allowance to finish. This systematic approach combined with consistency will lead to improved academic performance seen through higher retention and higher quality submissions.

- Objective 1: Account for variables such as deadline proximity, estimated task duration, importance, and cognitive difficulty.
- Objective 2: Consider time blocks when students cannot work (e.g., meals, rest, travelling)
- Objective 3: Adaptability if inaccuracies are found in the original factors entered (e.g., underestimating task duration, deadline change), a refresh button is available to redo the formula based on the updated factors.
