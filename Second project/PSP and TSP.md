# The Personal Software Process

The Personal Software Process (PSP) provides engineers with a disciplined personal framework for doing software work. The PSP process consists of a set of methods, forms, and scripts that show software engineers how to plan, measure, and manage their work. This assists in the further improvement of their performance by tracking their predicted and actual development of code. 

### Origin

Since the times of the Industrial Revolution the quality strategy in most industries was based almost entirely on testing. Typically, established special quality departments were created to find and fix problems after their products had already been produced. This method kept being used until, in the late 70s, W. Edwards Deming and J.M. Juran convinced U.S. industry to focus on improving the way people did their jobs. This change was responsible, in the succeeding years, for an improvement in the quality of almost any kind of product. This step consequently led to the progress of this method throughout the years, expanding it to every kind of industry or company.

One of these steps was taken in software engineering with the Personal Software Process (PSP) created by **Watts Humphrey** in 1995. The PSP extends the improvement process to the people who actually do the work — the practicing engineers. The PSP concentrates on the work practices of the individual engineers. The principle behind it is that to produce quality software systems, every engineer who works on the system must do quality work.

### Principles

The PSP design is based on the following planning and quality principles:
* Planning
* Well-defined and measured processes
* Quality work
* Low cost development
* Efficient development
* Simplicity

All these principles need to be tailored to each specific individual. It is expected that every engineer who uses this method plans and executes the process in his own way.


### Process Structure

The first step in the PSP process is planning. There is a planning script that guides this work and a plan summary for recording the planning data. While the engineers are following the script to do the work, they record their time and defect data on the time and defect logs. At the end of the job, during the postmortem phase (PM), they summarize the time and defect data from the logs, measure the program size, and enter these data in the plan summary form. When done, they deliver the finished product along with the completed plan summary form.

<p align="center">
 <img src="https://jjegonzalezf.files.wordpress.com/2010/12/sshot-5.png"  alt = "structure">
  <br>
  Img. 1 - The PSP Structure
</p>

Since the PSP process has a number of methods that are not generally practiced by engineers, the PSP methods are introduced in a series of seven process versions. These versions are labeled PSP0 through PSP3, and each version has a similar set of logs, forms, scripts, and standards. Each one of these versions will be briefly explained below.

#### PSP0 : Personal Measurement

* Engineers gather data on the time they spend by phase and the defects they find
* Generates real, personal data and provides the base benchmark for measuring progress
* 3 phases: planning, development and postmortem
* Adds a coding standard, size measurement and a process improvement proposal

#### PSP1 : Personal Planning

* Introduces a method for estimating sizes and development times for new programs based on personal data 
* The methods employed are usually based on linear regression with prediction intervals to indicate size and estimate quality 
* Adds schedule and task planning

#### PSP2 : Personal Quality

* Introduces defect management 
* Construction and usage of checklists for design and code review
* Adds design specification and analysis techniques along with defect prevention, process analyses and process benchmarks

#### PSP3 : Scaling Up

This final step shows how engineers can couple multiple processes in a cyclic fashion to scale up to developing systems with many thousands of lines of code (LOC). It uses an iterative enhancement approach.

A team software process should be developed as the next step for systems larger that 10K LOC.

### Pros and Cons

The PSP was praised at the time it was created because it aided software engineers solve some of the most common mistakes. Improve their estimating and planning skills, make commitments they can keep, manage the quality of their projects and reduce the number of defects in their work.

However, over time and as some other softwares processes started being developed, the PSP started getting some criticism. Some believed it was a good idea in theory but not in practice, other that it wasn't flexible enough, due to the strict forms you had to fill. For that reason, it was also said that the PSP was too time consuming.

The PSP is only a framework of common sense ideas and suggestions which engineers are encouraged to think about as they learn from experience. The PSP fails, when it is used by the team to criticise individuals. This risk occurs when the PSP is used, rightly, to give feedback to the team-wide process.

---

Despite this last negative opinion regarding the PSP, this method is not to be used alone. In the real world, software is developed by a team and that is why Watts Humprey also created the Team Software Process. This method tightly depends on the PSP and they cannot be used separately.

---

# The Team Software Process

### Origins
The Team Software Process, which we'll refer to as TSP from now on, was designed by Watts Humphrey in the late 1900s. Its technical report was published in November 2000.  
In 1996, Humphrey attempted TSP0, a simple process for teams whose members who had received no previous guidance other than PSP. It was solely attempted on two teams and over the course of two years it evolved to its current state.

### Design
According to the creator, the TCP was designed for use with teams of 2 to 20 members. It aims to help build and provide guidance to teams of skilled and effectively trained members. The teams are led by a certified or provisional coach, who has been specially trained.
It is mandatory that engineers have already learnt about the Personal Software Process (PSP), intended to improve estimating and planning skills as well as project improvement.

### Conditions for teamwork
Humphrey describes that each team member must have roles, given that they provide a sense of ownership and belonging. Roles prevent conflicts, duplicate work and wasted effort.  
Interdependency is also crucial as each team member depends to some degree on the performance of others. It **improves** individual performance as members will generally make a special effort to meet their obligations to the rest of the team.  
For a team to be effective, some common characteristics are required such as disciplined and motivated members as well as its goal being defined, visible and realistic. They must strive to meet demanding schedules whilst adjusting to change.

### The principles
These are the major values of the TSP method
* Commitment
* Aggressive plans
* Quality ownership
* Project goals
* Plan ownership
* Plan detail
* Team roles
* Team resources

### The process
The TSP development cycle starts with a four-day planning process called the **team launch** to develop the project's strategy, process and plan with a three to four month expectancy.  
The team launch lasts about 9 meetings over the course of 4 days and do follow scripts.  
* On day 1, team members are assigned team roles and backup roles and the project's strategy and products to use is set.
* On day 2, size estimates and allocation of work to team members is processed.
* On day 3, project's risks are evaluated and risk assessment checkpoints are defined.
* On the final day, the project's plans are discussed and reviewed by the management.

<p align="center">
 <img src="https://i.imgur.com/6qlGFir.png"  alt = "TSP meeting process" height=400px>
  <br>
  Img. 2 - TSP's meeting process
</p>

After 9 meetings, the development cycle ends with a **final postmortem step** aimed to review the launch process and submit process improvement proposals (PIPs).   
Following its iterative design, TSP teams are relaunched periodically to assess on the knowledge gained on the previous cycle and to update the engineers' detailed plans.

### Key pros and cons
According to a study by Capers Jones published on May 2013, TSP ranks 3rd from the list of most efficient software development strategies, only surpassed by Scrum and XP. On average, its use results on a development schedule of just over a year for applications of 1000 function points.  

<p align="center">
 <img src="https://i.imgur.com/cIE4k4k.png"  alt = "Rating speed" height=200px>
  <br>
  Img. 3 - Software processes rating based on development months
</p>

The study also lists TSP as first on its ability to detect and correct software defects and also first on the matter of Total Cost of Ownership and Cost of Quality. These refer to the costs of maintenance which end up being very low as a result of TSP's quality-related methods instead of speed-related methods.  

<p align="center">
 <img src="https://i.imgur.com/gzrs11l.png"  alt = "Rating defects" height=150px>
  <br>
  Img. 4 - Software processes rating based on TCO and COQ
</p>

On average, TSP can provide you the fewest defects at the cost of an extra development month period. Strategies like Agile and Scrum do tend to be faster but result on more software flaws and, therefore, higher maintenance costs.

<p align="center">
 <img src="https://i.imgur.com/eY3ukLd.png"  alt = "Rating defects" height=175px>
  <br>
  Img. 5 - Software processes rating based on defects found
</p>

### References

**PSP**

https://www.sei.cmu.edu/reports/00tr022.pdf
http://www.eng.auburn.edu/files/acad_depts/csse/csse_technical_reports/csse10-08.pdf
https://stackoverflow.com/questions/28197/do-you-follow-the-personal-software-process-does-your-organization-team-follow
http://www-public.tem-tsp.eu/~gibson/Teaching/CSC5524/CSC5524-PSP.pdf

**TSP**

https://en.wikipedia.org/wiki/Team_software_process
https://web.archive.org/web/20130629005257/http://namcookanalytics.com/evaluating-ten-software-development-methodologies/
https://www.sei.cmu.edu/reports/00tr023.pdf
