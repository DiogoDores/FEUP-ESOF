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

