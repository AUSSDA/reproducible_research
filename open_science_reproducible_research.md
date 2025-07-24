<!--
author:   Anita Bodlos & Lisa Hirsch & Franz Eder

email:    info@aussda.at

version:  1.0.1

language: en

narrator: US English Female

comment:  This course gives an introduction to the ideas of Open Science and Reproducible Research, and presents some tools that facilitate open and reproducible workflows. For more information, please refer to the Readme.md file.

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js

-->




# Open Science and Reproducible Research

Welcome to the [Infra4NextGen](https://infra4nextgen.com/) course on Reproducible Research and Workflows!

This course[^1] introduces the topic of reproducibility within an Open Science framework, and gives an overview over different tools to use. You will be able to follow easy step-by-step tutorials and directly apply the content to your own research project. While the principles and workflows may be applicable to various disciplines, we are Social Scientists by training and have created the course with typical challenges in the Social Sciences in mind.

[Section 1](#2): Open Science and Reproducible Research – What is it, and why should I care? 

[Section 2](#6): Collaboration – Challenges and solutions

[Section 3](#9): GIT – Working collaboratively and version control 

[Section 4](#14): Quarto and R-Studio – Dynamic document generation

[Section 5](#18): APIs and the renv package - keep your working environment stable

[Summary](#21)


**Why should you take this course then?** Reproducible research covers a set of practices that are rooted in the idea of Open Science. By taking this course you will be able to think about your research practices in ways that foster reproducibility - for yourself, and others. Increased collaboration, more efficiency and - ultimately - better research are tangible benefits from practicing reproducible research. 

__Objectives and Learning Outcomes__

By the end of the module, you will:  

* Understand the concepts of reproducible and open science 

* Be able to compare frequently used tools and evaluate their applicability 

* Develop a reproducible workflow for your own research projects 

<!-- style="background-color: #6EC7D9;"--> 
> ** Do I need to take any other courses before taking this course?**
>
> You do not need any other courses to take this course. As the main aim is to give an overview of useful tools, you do not need to install any software to complete the course. However, if you would like to try out the software yourself, you might need administrator rights to install some of the programs. We are focussing on non-proprietary software in this course.
>
> It will take about 60 minutes to complete this module. 
>
>In case you are already an expert on Open Science and want to jump right to more information on tools and workflows, you can do that by going to [Section 3](#9), but we encourage you to read all sections! 
 

<!-- style="background-color: #E72E6B; color: white"--> 
> **A note on knowledge checks and quizzes**
>
> We have added some knowledge checks throughout the course so you can test your knowledge after each section. You will not be graded on these quizzes, but we invite you to take them to check if you understood certain sections. 
> You can get some hints by clicking onto the light bulb icon below each quiz, and reveal the solution by clicking on the checkmark. 

Ready to dive into the world of reproducible research? 

Go ahead to the [next section](#2)!

----
![EU Logo](images/EU_logo.jpg "Funded by the European Union") 

[^1]: The content of this course relies on the the workshop "Open science and reproducible research in RStudio and Jupyter Notebook​" by Franz Eder, licensed under a [CC BY SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) license.

# Section 1: Open Science and Reproducible Research - What is it, and why should I care?

Open Science and Reproducible Research are buzzwords that you might have come across already - but what do they actually mean and why are they important to your daily scientific practice?

In this section, you will read up on 

* the principles and drivers of Open Science 
* the principles of reproducible research
* and how these two aspects are interconnected

## 1.1. Principles of Open Science

Open Science can be defined in multiple ways. One such definition is that Open Science is a “collaborative culture enabled by technology that empowers the open sharing of data, information, and knowledge within the scientific community and the wider public to accelerate scientific research and understanding” [Ramachandran, Bugbee, and Murphy 2021](https://doi.org/10.1029/2020EA001562). 

Another definition by the [European Commission](https://data.europa.eu/doi/10.2777/18252) states that "Open science consists in the sharing of knowledge, data and tools as early as possible in the Research and Innovation (R&I) process, in open collaboration with all relevant knowledge actors, including academia, industry, public authorities, end users, citizens and society at large."   

Another definition by the [UNESCO](https://www.unesco.org/en/open-science/about) points out that “Open science is a set of principles and practices that aim to make scientific research from all fields accessible to everyone for the benefits of scientists and society as a whole.”

Foster developed a whole taxonomy of Open Science that picks up various aspects of these definitions:
![Foster Taxonomy of Open Science](https://www.openscience.no/sites/default/files/media/bilder/2021/02/os_taxonomy.png "Taxonomy of Open Science by Ponitka et al 2015, https://doi.org/10.1145/2809563.2809571") 

In recent years, the Open Science movement has shifted away from demanding "open data" and noe emphasises making data "FAIR" (Findable, Accessible, Interoperable, Re-usable; [Wilkinson et al 2016](https://doi.org/10.1038/sdata.2016.18)) because there are good justifications to restrict access to - some - data: In the Social Sciences  protecting the privacy of research subjects (in line with data protection regulations) is important. In order to still make such data FAIR, they do not need to be completely open but the access conditions to the data need to be outlined clearly. 

FAIR data comprises many more aspects and requires researchers e.g. to choose a mature, trustworthy repository to publish their data with a DOI to guarantee that data is findable. Are you interested in knowing more about FAIR data? Find some useful sources in our webinar slides on ["Research data management in the Social Sciences"](https://www.doi.org/10.5281/zenodo.14258222) and ["Data Protection in Research"](https://www.doi.org/10.5281/zenodo.14824581)!

<!-- style="background-color: #E72E6B; color: white"--> 
> **__Quiz I__**
>
>Take a second to read through the definitions of Open Science again! Then tick all correct statements. 
>
>Click on the lightbulb to get some hints!

<!-- data-randomize -->
- [[X]]  Open Science includes all research practices from collecting data to analysis and publications
- [[X]]  Open Science benefits researchers and the general public
- [[X]] Open Science builds on collaboration
- [[ ]] Open Science is only about publishing in Open Access Journals
- [[ ]] Open Science only benefits researchers
- [[ ]] Open Science is an individual effort 
[[?]] Open Science does not occur in a vacuum, think about the social settting researchers work in!
[[?]] There are three correct answers.
***
Solution: Open Science applies to all stages of the research data life cycle, from the planning phase over data collection to analyses and subsequent reuse by researchers and the public. Opennness fosters collaboration.
***

## 1.2. Drivers of Open Science

Why should you care about Open Science then? 

![Open Science](https://www.ncl.ac.uk/mediav8/library/general-x2f-full-width/research/open-research/comic/comic-p3-p1.jpg"[Open Research Comic](https://www.ncl.ac.uk/library/academics-and-researchers/lrs/open-research/comic/page3/) by Kelsey Bezaire and Dr. Helen Gray 2023 [CC BY ND](https://creativecommons.org/licenses/by-nd/4.0/deed.en)" )

Across all fields, Open Science practices advance disciplines, foster collaboration, lead to more citations of individual works, and cater to funders' interests. Current technological developments - the internet, emergence of big data and increased efficiency in both processing and analysing that data due to readily available computational methods - lead to, allow and benefit from collaboration in large, often international teams.   

!?[⏯](video/course1-clip2.mp4 "Extract from the Infra4NextGen workshop on [*Open science and reproducible research in RStudio and Jupyter Notebook*](https://infra4nextgen.com/events/workshop-open-science-reproducible-research/), speaker: [Franz Eder](https://www.franz-eder.info/), University of Innsbruck" )

## 1.3. Principles of Reproducible Research
Reproducibility refers to different aspects in the research process.  

First, it can mean that the goal is to come to the same conclusions using the same data: Imagine you are reading a journal article that sparks your interest. The operationalization of variables is novel to you, and you are wondering how exactly the authors did their analyses. Luckily, the article contains a DOI that leads you to the dataset used in the analyses which is accompanied by the code for the analyses. It is openly accessible and licensed under an open license by a trusted repository, so you can download it from the repository after agreeing to their terms of use ([Rokem, Marwick, and Staneva 2017](http://www.practicereproducibleresearch.org/core-chapters/2-assessment.html)).

Second, it can refer to the effort of using different data but the same methods in order to evaluate the robustness of results, which is usually defined as replicability: Imagine you are reading another journal article, that leads you to wonder whether the results hold up to different model specifications. Again, the article contains a DOI that leads you to the dataset used in the analyses which is accompanied by the code for the analyses. It is openly accessible and licensed under an open license by a trusted repository, so you can download it from the repository after agreeing to their terms of use. Now you can modify the code accordingly and check for the robustness of results and different model specifications ([Rokem, Marwick, and Staneva 2017](http://www.practicereproducibleresearch.org/core-chapters/2-assessment.html)).

What do these scenarios have in common? They both emphasize the difference between trusting and showing: Trusting research results - and trusting others to trust you - is vastly different from *showing* them the way you came to conclusions ([Stark 2017](http://www.practicereproducibleresearch.org/core-chapters/0-preface.html)).  

Then, you might wonder how exactly to reach reproducibility. The following sections will go into more detail on specific tools, but here is a short summary for you before: Reproducibility is directly tied to computational methods and often used synonymously to computational reproducibility - the practice of leveraging computational methods to practice reproducible research. Watch the video below to see how computational methods and reproducibility relate:

!?[⏯](video/course1-clip3.mp4 "Extract from the Infra4NextGen workshop on [*Open science and reproducible research in RStudio and Jupyter Notebook*](https://infra4nextgen.com/events/workshop-open-science-reproducible-research/), speaker: [Franz Eder](https://www.franz-eder.info/), University of Innsbruck" )

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz II__ 
>
>You now know the basic theoretical concepts of Open Science and reproducible research, so how do these relate? Pick which activities match which part of the definitions of Open Science!
> 
>Click on the lightbulb to get some hints!

- [[publish in open access journals] [archive data with certified repositories] [commit scripts to Github for data analysis]]
- [    [X] [X]  [ ]     ]  sharing of data
- [    [X] [X]  [X]     ]  sharing of information
- [    [X] [X]  [X]     ]  sharing knowledge
- [    [X] [X]  [X]     ]  engage with the scientific community
- [    [X] [X]  [ ]     ]  engage with the wider public
[[?]] Sharing of data, knowledge and information can all be done in several ways.
[[?]] Engaging with both the public and the scientific community is fostered by different platforms.
***
Solution: By archiving data with certified repositories you share your data with others!
Sharing information and knowledge occurs when both data and the scripts used for the analyses are openly available.
Engaging with the scientific community can be done by all activities!
The wider public gains access to your work when ypu publish in open access journals and archive your data with certified repsitories!
***

<!-- style="background-color: #6EC7D9;"--> 
> In this section "Open Science and Reproducible Research - What is it, and why should I care?", you learned about the principles and drivers of Open Science and how they relate to reproducible research! 
>
> **Sounds great! How do I go forward from here?**
>
> Go ahead to the [next section](#6) to understand why collaboration and reproducible research go hand in hand!

# Section 2: Collaboration: Challenges and solutions

In this section you will learn about the challenges of working collaboratively and the theory behind solutions to these challenges!

## 2.1. Working collaboratively: Which problems are addressed?

When working collaboratively in any setting, challenges may arise. Coordinating any number of people over an extended period requires a thought through workflow. [Peikert, Lissa, and Brandmaier (2021, 838)](https:\\www.doi.org\10.3390/psych3040053) identify “multiple inconsistent versions of code, data, or both” as the main problem in collaborative work. Additionally, missing documentation and copy-and-paste errors in final products – reports, articles, drafts, etc. - complicate the matter further.  

!?[⏯](video/course1-clip1.mp4 "Extract from the Infra4NextGen workshop on [*Open science and reproducible research in RStudio and Jupyter Notebook*](https://infra4nextgen.com/events/workshop-open-science-reproducible-research/), speaker: [Franz Eder](https://www.franz-eder.info/), University of Innsbruck" )



## 2.2. Solutions to collaborative working

Solutions to the challenges you read are working on code collaboratively and dynamically, in an environment that also allows for version control and accessibility across different machines. 

<!-- style="background-color: #6EC7D9;"--> 
> In this section you learned more about challenges of collaboration and some general solutions: Most importantly, version  control facilitates collaboration. Dynamic document generation further safeguards against common errors that occur when results are copied into another document.  
>
> **Sounds great! How do I go forward from here?**
>
> Go ahead to the [next section](#9) to understand GIT, a commonly used tool for working collaboratively including version control!
>
> Go ahead to [Section 4](#14) if you want to learn more about how to create dynamic reports using Quarto and R Studio. 
>
> Go ahead to [Section 5](#18) if you want to read up on how APIs and the renv package facilitate your reproducible workflow. 

# Section 3: GIT – working collaboratively and version control 

![Git Logo](https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png "[Git Logo by Jason Long](https://git-scm.com/downloads/logos) [CC BY 3.0](https://git-scm.com/downloads/logos)")

In this section, we will take you through what Git is and why it is useful in your reproducible scientific workflow. You will learn how version control works in Git, and how you can use it to work collaboratively. 

Git is a very powerful and popular tool that may require a little bit more initial effort when you start learning to use it. In this section, you will get an overview of the basic workflow and some basic concepts. This very likely will not be enough information to start using Git. Rather, the goal is to let you see if this tool is interesting for you and worth a closer look. You will find a collection of further training material at the end of this module. 

In the following sections we will introduce you to 

* how Git works, 
* how Git uses version control, 
* how you can use Git to work collaboratively 
* and will ultimately show you how to use Git in practice.

Go ahead to the [next section](#10) to learn how Git works!

## 3.1. How does Git work?

**What files can I save in a Git system?** [Git](https://git-scm.com/) was developed as a tool for working on software code collaboratively. For this reason, Git is most useful if you work with syntax files (e.g. R or Python) and non-proprietary files (e.g. csv or tab-delimited for data files, Latex files or Markdown for text), basically all documents that contain plain text. You can store any file in Git systems, although you may not be able to exploit the full potential of a Git system if you use proprietary formats (like Microsoft Word or Excel). 

**Remote repository and local working directory:** The main logic for using Git is that you have a remote Git repository somewhere online (e.g. on your institution’s Gitlab). Then, you can “clone” this repository to your local device, e.g. your laptop. The process also works the other way round: you can also create a new remote Git repository from the files on your device. However, the principle remains the same: you have files on your local device and in a remote Git repository that is accessible by you (e.g. because you can connect to it through the internet).

**Basic workflow: add, commit, push:** Once you have this initial set up, you can save or update files in the remote repository. Imagine, for instance, that you clean your data using R. When you are happy with the result, you “add” the files to the staging area (an obscure limbo that is a step in between your laptop and the online repository). Next, you can “commit” the files you added to the staging area to the repository. You have the possibility of adding a “commit message” to every commit and we highly recommend that you seize this possibility. Commit messages allow you to retrace your steps and identify the changes between versions. Finally, you “push” the files to the Git repository and only then they are saved in your remote repository. So, your files are not only saved locally on your device but also on your remote repository. There are of course a lot more commands and the workflow can get a lot more complicated, but this is the basic concept. 

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz III__ 
>
>In which profession is Git most common?
> 
>Click on the lightbulb to get some hints!

- [[ ]] Arts 
- [[ ]] Marketing 
- [[X]] Software development
- [[ ]] Weather simulation 
[[?]] There is only one correct answer.
***
Solution: Git has its origins in the development of the Linux operating system and is very popular among software developers. 
***


<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz IV__ 
>
>For which kind of files does Git work best?
> 
>Click on the lightbulb to get some hints!

- [[X]] Syntax/code files like R scripts, do-files and python-code  
- [[ ]] FAIR data files 
- [[ ]] Any file as long as it contains mostly text (txt, rtf, word, only office)
- [[ ]] All files that are licensed openly (preferably CC BY) 
[[?]] There is only one correct answer.
***
Solution: Git works best for code files as it implements version control. 
***

## 3.2. Git as version control
!?[⏯](video/course1-clip1.mp4 "Extract from the Infra4NextGen workshop on [*Open science and reproducible research in RStudio and Jupyter Notebook*](https://infra4nextgen.com/events/workshop-open-science-reproducible-research/), speaker: [Franz Eder](https://www.franz-eder.info/), University of Innsbruck" )

One of the main selling points of Git systems is that it offers an inherent version control system: Whenever you save something in a Git system i.e. you “add”, “commit” and “push” your files, a new version of your files is created in the Git. You can go back to previous versions any time (if you make a “checkout” of this version) if you want to. This makes Git a very powerful tool.  

Read this **example** how switching between versions works: Imagine you prepare your data for a regression analysis and find an outlier in the variable “household income in Euro per month” because a billionaire is in your sample. You decide to recode the value to one standard deviation above the second largest value in the sample and run your analyses based on this data. However, later on, you keep wondering if this is indeed the best solution and decide to run several robustness checks. Omitting the entire observation is straight forward but you would also like to run your analysis on the dataset before you recoded the variable. In this case, you can simply “checkout” the non-recoded dataset and run the regression. 

To seize the full potential of version control via Git, it is crucial that you put a little bit of thought in how you **describe the individual versions in the commit messages** and **how often you create new versions** (i.e. how often you commit and push files). In three months from now, “recoded/cleaned variable age to remove unplausible values” as commit message certainly tells you more about the changes you made than “fixed error”. Also, committing frequently after you have completed individual tasks may help you more in terms of version control than committing only occasionally to have an additional backup of your work. In case you still have doubts about the usefulness of commit messages, check out the ultimate source of truth for survival tips in academia, [XKCD comics](https://xkcd.com/1296/):

![[XKCD Comic on commit history](https://xkcd.com/1296/)](https://imgs.xkcd.com/comics/git_commit_2x.png "Source: xkcd Comic [https://xkcd.com/1296/](https://xkcd.com/1296/), licensed under a [CC BY-NC 2.5](https://creativecommons.org/licenses/by-nc/2.5/) license.") 


A downside of this inherent version control mechanism is that **it can be difficult to actually delete files for good** if you work with Git: If you simply delete a file and push the change, the file will be deleted in the latest commit, but will still be part of the previous versions that you can “checkout” any time. Nevertheless, sometimes it is necessary to delete files for good for instance non-anonymized or non-pseudonymized versions of files, or data that you need to delete after a certain period of time for contractual reasons. In this event, you need to take some extra steps to delete the data or ask yourself if alternative storage solutions may fulfil your requirements better. 

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz V__ 
>
>Which statements on version control are true?
> 
>Click on the lightbulb to get some hints!

- [[X]] The basic workflow of Git is that you work locally on your device, then you “add” your files to the staging area, “commit” them and finally “push” them to the remote Git repository. 
- [[X]] Every time you commit/push something to Git, a new version is created. 
- [[ ]] Commit messages are important because it is the only accessible information about changes between versions since Git automatically moves old versions to a secure backup-location where it can only be accessed in case of a major incident. 
- [[X]] Commit messages are important because they can be used to describe changes between the versions. A good description facilitates identifying a version so that you can go back to this version any time and make a “checkout” to look at it again. 
[[?]] There are three correct answers. 
***
Solution: The basic workflow of Git is that you work locally on your device, then you “add” your files to the staging area, “commit” them and finally “push” them to the remote Git repository. Still, there are many more commands and Git offers the possibility to various more complicated workflows (e.g. with different branches). Git has an inherent version control mechanism that allows you to go back to previous versions any time. This requires of course that you know which version is of most interest to you. Commit messages help a lot for identifying the correct versions: whenever you commit something, we recommend that you enclose a short description about the changes you made.
***

## 3.3. Using Git to work collaboratively
Collaboration in Git follows a **different logic as you may know from standard synch-and-share tools** (like Dropbox or Google Drive). As you already know after going through the previous sections, Git was developed for and is still widely used in software development. When multiple programmers work on the same project, they may develop individual features in parallel. Each programmer then saves their work to the common Git repository. If this work is complementary, i.e. each programmer works on a separate file, Git simply merges the information together. If multiple programmers work on the same file, there likely will be a conflict (since both updated the file). In this case, one person has to go over the changes and create a consolidated version:  This way of collaboration may require a little bit more discipline and knowledge compared to synch-and-share tools. This works fine in software development as programmers usually work with syntax/code that is saved in easily accessible files containing plain text. For instance, you may have noticed that you can open R-files, do-files or Python code in any text editor and see the code.

**How do I make sure that I work with the most current version?** Whenever you collaborate with someone else using Git, it is a good idea to make sure that you have the latest version of your project on your device before you start working. You can do this by means of the “pull” command, i.e. you download any changes that may have been made in the meantime by your colleagues. 

Another detail: There is **the possibility to work also online** and make changes directly in the file in the Git repository – like you would in common sync-and-share tools -, but this only works for easily accessible formats like markdown. This may be handy if you just quickly add a comment to a documentation file or if the entire git workflow still causes you some struggling. However, soon you will know your way around Git by heart and pulling, adding, committing and pushing will become standard comments in your work routine. 

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz VI__ 
>
>How does collaboration work in Git? 
> 
>Click on the lightbulb to get some hints!

-[[ ]] Not at all; Git is designed to work as single author.
-[[ ]] Like any sync-and-share platform.
-[[X]] You work locally on your files and then push it to the Git repository. In case there are conflicts due to the work of someone else, someone has to manually create a consolidated version. 
-[[ ]] You work locally on your files and whenever there is a conflict, you have to go back in the existing previous versions and fine one without any conflicts. Then, you have to start working anew. 
[[?]] There is one correct answer.
*** 
Solution: Git is frequently used for collaborative software development and offers different workflows for collaboration (from merging conflicting files to developing features in different “branches”). 
Git works a little bit differently than popular synch-and-share platforms like Google Drive or Dropbox: everyone works on local files and then “pushes” the output to the repository. In case of conflicts, these have to be solved manually. 
When creating consolidated versions you can choose your version, your colleague’s or – probably most reasonable – the best of both versions. 
***

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz VII__ 
>
>Which command allows you to download the most recent version of the Git repository? 
> 
>Click on the lightbulb to get some hints!

-[[ ]] “update” 
-[[ ]] “clone” 
-[[X]] “pull” 
-[[ ]] “getit” 
[[?]] There is only one correct answer.
[[?]] With the command “clone” you can download the entire Git repository to your device.
*** 
Solution: "Pulling" allows you to download the most recent version of the Git repository. With the command “clone” you can download the entire Git repository to your device.

*** 

## 3.4. How to use Git in practice

Now, you might be wondering how to actually use Git in practice. Check the list below for individual steps and more information:  

If you are interested in reading more on Git, a comprehensive guide is offered by: Chacon, Scott, and Ben Straub. 2024. *Pro Git: Everything You Need to Know about GIT*. 2nd ed. New York, NY: Apress. https://github.com/progit/progit2. 

In order to use Git, you need to [install it](https://git-scm.com/downloads).

The default way to use git is via the **command line**. You can use various tools that allow working with the command line (like Visual Studio Code, Pycharm or PowerShell) or you use the  the “git bash” that is included when you download and install git from the link above. If you are not used to working via the command line, this may take some effort in the beginning and you will likely need a tutorial before you can jump in, but it is worth it! 

If you prefer to use Git with a **GUI (Graphical User Interface)**, there are multiple GUIs for Git that let you avoid using the command line. Working with these GUIs may facilitate using Git, but they may not offer an interface for all commands. Examples for Git GUIs are [Sourcetree](https://www.sourcetreeapp.com/) or [Github Desktop](https://desktop.github.com/download/). 

If you work with RStudio, **you can use [Git directly from within RStudio](https://docs.posit.co/ide/user/ide/guide/tools/version-control.html)**. 

You also need an online repository to store your files. Many universities offer Gitlabs for their researchers as part of their storage options. There is also the commercial provider [Github](https://github.com/). 

Github also offers the possibility to **publish your work** (some institutional Git systems may also do so). This can be a very convenient way for sharing your work, especially if you would like others to build upon your work (e.g. if you publish open-source software and open it up for others to contribute) or if you would like to demonstrate your entire workflow including all versions of your data. However, please note that other repositories may be better choices for archiving research output: other repositories may be better suited for long-term archiving, not all funders may consider Git systems as “trustworthy” and Github does not offer persistent identifiers like DOIs (which is an essential aspect of FAIR data). A solution could be to publish your work via a trustworthy repository (e.g. a [CESSDA repository](https://www.cessda.eu/About/Consortium) or [Zenodo](zenodo.org)) as well as via a Git system and cross referencing the two sources. This may allow you to benefit both of the advantages of trustworthy, mature repositories as well as of Git systems with the goal of ongoing development.

Some more practical hints: As explained above, Git is a very powerful tool that offers many advantages but also requires some initial learning. Hence, you may need a while to get used to it. Starting with a project on your own may be an easy first step because you can get used to the workflow while avoiding more complicated situations where you have to merge conflicting files. Also, we would only recommend collaborating with others in Git when you know that they already know Git or are committed to learning this tool and willing to spend some time on it. Else, new users may give up frustrated, you may lose work (if someone forgets to push) or you may end up with various conflicting versions because someone did not respect the workflow. 

<!-- style="background-color: #6EC7D9;"--> 
> **Example for a Git repository**  
>
> Are you curious how a Git repository may look like? In the Infra4NextGen workshop on "Open science and reproducible research in RStudio and Jupyter Notebook”, Franz Eder created a Git repository for the participants as part of the workshop content and minimum example how a project could look like: https://github.com/franzeder/I4NG-workshop. If you have a look at the repository, you can see some files that should be part of any Git repository: 
>
> * a "README.md" with some basic description of the project and 
> * a "LICENSE" file which contains the license, i.e. the conditions under which you can or cannot re-use the repository. 
> * In addition, you see several standard folders like "plots", "scripts" or "documentation". 
> * You may also notice a folder called "renv" -- we will come back to this folder in [Section 19](#19).
> * If you have a look at the top right of the file list, you see that there are currently 12 commits. If you click on them, you can browse through the versions. 

     

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz VIII__ 
>
>What are ways to work with Git?
> 
>Click on the lightbulb to get some hints!

-[[X]] Via the command line 
-[[X]] Via a terminal in Visual Studio Code 
-[[X]] Via R Studio 
-[[X]] Clicking your way around a Graphical User Interface (GUI) like Sourcetree 
[[?]] There are several correct answers.
*** 
Solution: Git can be used via the command line, via GUIs of your choice or via a terminal in Visual Studio Code. If you work with RStudio, you can also use Git directly in RStudio.
***

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz IX__ 
>
>Can you use Git for publishing your work? 
> 
>Click on the lightbulb to get some hints!

-[[ ]] Yes, Git systems are as trustworthy as mature repositories (e.g. CESSDA repositories or Zenodo). 
-[[X]] It depends: Git systems like Github allow you to publish files and others to easily incorporate and build upon your code files. However, there are other, discipline-specific repositories available that offer many advantages for publishing research data data.
-[[ ]] No, Git systems are per definition not built for sharing your work with the public. .
[[?]] Unfortunately, there is only one correct answer. You need to decide!
***
Solution: Git repositories are a well-suited tool for publishing code/syntax files especially if you would like others to re-use your work as a Git repository or build upon it in the same Git repository. E.g. others could “clone” your code files, correct errors or add a feature and add/commit/push their work to your repository. However, especially in the Social Sciences, there is a well-developed infrastructure of trustworthy and sustainable repositories (CESSDA) who cater to the needs of the Social Science community and in general guarantee the highest findability of your research output. In some cases, publishing your research output multiple times may be the best way to go: once in a mature repository for long-term archiving and once via a Git system for easy re-use and the possibility of on-going development.   
***

<!-- style="background-color: #6EC7D9;"--> 
> __Summary: Git in a nutshell__
>
> Git is a very powerful tool with inherent version control that allows for “checkouts” of previous versions. Hence, you can go back to previous versoins any time. 
>You can collaborate using Git via “pushing” your work to a shared repository and allowing others to “pulling” your work from the same repository. Conflicts are to be expected when multiple researchers share a repository and need to be solved manually. 
>Git is most useful when you work with syntax and easily accessible, non-proprietary formats that contain plain text (like R, markdown, csv...). 
>Starting to use Git requires a little bit more effort, time and training than you may expect. However, going through the trouble is worth it! Below, you find a list of helpful training material. 


<!-- style="background-color: #6EC7D9;"--> 
> **Now, I understand the basics of Git and version control. How can I make sure I do not introduce errors when I write up my paper?**
>
> Go ahead to the [next section](#14) to understand how you can create reports using Quarto.



# Section 4: Quarto and R-Studio: dynamic document generation

In this section, you will read up on Quarto, a software that allows you to create documents dynamically and thereby combine your theoretical and empirical work. You will be able to produce a workflow for reproducible science with Quarto.

!?[⏯](video/course1-clip5.mp4 "Extract from the Infra4NextGen workshop on [*Open science and reproducible research in RStudio and Jupyter Notebook*](https://infra4nextgen.com/events/workshop-open-science-reproducible-research/), speaker: [Franz Eder](https://www.franz-eder.info/), University of Innsbruck" )

In a nutshell, [Quarto](https://Quarto.org/) is an open-source tool that allows you to create various forms of publications (articles, books, presentations, websites...) using different programming languages including Python and R. You can write scientific text using markdown and create the output as html or pdf (via Latex). Quarto works with various tools and editors, however, we will focus on using Quarto with R Studio in this section. 

## 4.1 Benefits of dynamic document generation using Quarto
If you use Quarto, you can work with one tool that holds both the theoretical as well as empirical part of your publication. For instance, imagine you are writing an article. When working in Quarto, one file is sufficient for the entire paper: The file contains the discussion of your research question and relevant literature as well as the code for the analysis, figures and tables and the discussion of your results. This means that you do not need to copy-paste figures or tables or results from one document to the other (and wonder if you ever forgot to copy any new versions of tables and figures).  

You can even directly reference your model outcomes and estimates in the text, which are then updated if you rerun the analyses or you render your document. For instance, instead of copy-pasting the mean of a variable, you can include some R code in the text that calculates the mean and includes this figure directly in the text. Thereby you can not only be sure that your estimates are up to date and immune to typing or rounding errors, but others can also easily verify your calculations. You even have the possibility to let others see the code in your output document. In short, you allow others to retrace your steps -- your research becomes reproducible. 

Quarto can also facilitate creating documentation files that accompany your data. For instance, you can use R to create an overview of all variables in your data set including information on summary statistics such as the minimum, maximum or mean. The output can either be a pdf or also an html file that even includes the code. This can be useful both for drafting documentation material for others to make your data re-usable and FAIR (Findable, Accessible, Interoperable, Reuseable) but also if you write a research log only for yourself as you can document in detail the reasons for the decisions you made (e.g. why you omitted specific observations). 

Of course, Quarto also allows you to take advantage of reference management systems ([using e.g. bibtex](https://Quarto.org/docs/get-started/authoring/text-editor.html#citations)).  

You can create different output formats with Quarto, from PDF to html and dashboards. You can use Quarto to write scientific publications like monographies or articles. Quarto uses Latex as a tool for creating PDFs, so your output will look like typical Latex documents. In addition, you can also use Quarto to create websites or dashboard that cater to the general public or journalists. 

Are you eager for an example? The Austrian Foreign Policy Panel Project used Quarto for cleaning and curating data, creating a methods report in pdf as well as html and drafting a codebook including an overview of all variables as well as summary statistics and plots. You can check out all files under the DOI https://doi.org/10.11587/UJJWTG. In addition, the project used Quarto to launch a website that allows for glimpses into the data as well as some general descriptions that you can check out here: https://afp3.at/ .

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz X__ 
>
> What can you do with Quarto?
> 
>Click on the lightbulb to get some hints!

-[[X]] Create documents dynamically, i.e. use one software for all steps of writing a research paper including the theoretical discussion, the analysis of the data, presenting your results as graphs or tables and discussing results. 
-[[X]] Create a PDF document that looks like a Latex document (because Quarto relies on Latex to render PDF documents). 
-[[X]] Create documents as html files or entire websites and dashboards. 
-[[X]] Do some data wrangling (cleaning, recoding data etc.) 
-[[X]] Automatically create bibliographies by using the reference management system. 
-[[X]] Referencing individual estimates or values from your data/analysis as code in the text.
[[?]] Quarto is a very powerful tool. 
[[?]] There are multiple correct answers.

## 4.2 How to start working with Quarto
To use Quarto, you need to install several software products first. Below, you find a list of everything you need to run Quarto with RStudio:  

* Since we use R in our example, R needs also to be installed on your machine via [CRAN](https://cran.rstudio.com/index.html).

* You also need an editor, in our case [RStudio](https://posit.co/download/rstudio-desktop/)

* Of course, you need to [install Quarto](https://Quarto.org/docs/get-started/).  There are also [tutorials for using Quarto with RStudio](https://quarto.org/docs/get-started/hello/rstudio.html). 

* In addition, you need a Latex distribution to compile PDF output. Quarto [recommends to install tinytex](https://quarto.org/docs/get-started/authoring/rstudio.html#format-options) 

Once you get started with Quarto, documents usually consist of three main types of content:  

* a yaml header that defines some general settings (e.g. the output formats including its specifications) 

* Code blocks (e.g. R code for loading your data and running an analysis) 

* Text blocks in markdown (e.g. for describing your data and the results) 

If you have used jupyter labs before, the distinction between code blocs and text blocs for markdown may seem very familiar. Quarto relies on the same principle that you can include both text and code in the same file. 

## 4.3. How to work collaboratively with Quarto

At the time of writing, the easiest way to work collaboratively with Quarto is using a Git system. If you follow this course in a sequential way, you can already picture how a workflow could look like: Researcher A works on her device and then “adds”, “commits” and “pushes” her work to a shared Git repository. When researcher B starts working on the project, he “pulls” the latest version to his device and the cycle starts anew.  

Please note that it is very probable that “conflicts” occur if you collaborate via Git because more than one person works simultaneously on the project or someone forgets to “pull” the latest version before starting to work. Since Git is designed for collaborative work, there are mechanisms in place how to handle these conflicts. However, since the goal of this course is to offer you an overview of possibilities rather than providing a tutorial in actually using these tools, we do not go into detail how you can solve conflicts.  

If you use R Studio for your Quarto documents, you can also use Git directly via R Studio. 

<!-- style="background-color: #6EC7D9;"--> 
> **Congrats**
>
> Go to the [last section](#18) to learn more about how you can retrieve data from a repository via an API and how to use the *renv* package in R. 

# Section 5: APIs and the renv package -- keep your working environment stable
In this section, you will learn how can you use an Application Programming Interface (API) to directly download research data and why that is useful. You will also be introduced to the renv package as a way to keep your research environment stable. Click [here](#19) to continue.

## 5.1. Accessing datasets via an API 

**What does accessing datasets via an API mean?** Many repositories offer access via an Application Programming Interface (API). This means that you do not need to click your way through the repository's website, in contrast, you can directly download a dataset from e.g. within R or Python. Some repositories may also offer the possibility to upload and publish data and documentation material via an API, but we will focus on the download part here.

**Why should you download datasets of a repository via an API?** Incorporating the download of the data file in your code increases the reproducibility of your research: Others can clearly see the origin of your data and download the same file (provided that they have access to the data). Also, you can demonstrate every step of your data wrangling before the analysis, e.g. if you recode variables or cap outliers. Clear documentation of these steps allows others to retrace your reasoning (e.g. why recoding this variable was necessary). Moreover, licenses may not allow you to re-publish a dataset even as part of a replication documentation. Retrieving data via an API can be a solution for this dilemma: you can point  to the data unambigously and whoever is interested in your process can download the data and retrace your steps even if you have not included the data in your replication files.

**Here are a few points to consider:** 

*   If the access to a data file is restricted and tied to your account, you may require a personal access token, a so-called *API key*. This **API key** has to be part of your code to be able to access/download data. Be sure that you do not share this token with others as it is comparable to your account's password. Instead, you can save the API key in a separate file in a separate location that is only accessible by you. 

*   We recommend that you have a look at the **repository's guidelines on how they handle provenance and version control of their data**. Mature repositories have strict and automatic regulations in this regard and publish new versions or updates of data files e.g. under new DOIs or new filenames. Hence, you can be sure that your code for retrieving data always leads to the same version of the data. However, this also means that you do not necessarily have the latest version of the published data and you may need to check manually from time to time if you would like to be sure to work with the most recent version.

* Repositories for research data rely on different repository software. The API is specific to a specific repository software. Hence, if you would like to access data in a specific repository, you need to find out the name of the underlying software in order to research how to exploit the API. For instance, [Zenodo](https://zenodo.org) relies on the software [InvenioRDM](https://inveniordm.web.cern.ch/). You can find a comprehensive description of the API [here](https://inveniordm.docs.cern.ch/reference/rest_api_index/). For the average R user, the more convenient solution likely is the R package [*zen4R*](https://cran.r-project.org/web/packages/zen4R/index.html) by [Blondel and Barde 2024](https://www.doi.org/10.5281/zenodo.2547036). Another popular repository software is [Dataverse](https://dataverse.org/) that has its origins in the [Harvard Dataverse](https://dataverse.harvard.edu/). You can find an extensive description of the Dataverse API [here](https://guides.dataverse.org/en/latest/api/index.html). Again, there is also an R package for easy access called [*dataverse*](https://cran.r-project.org/web/packages/dataverse/vignettes/A-introduction.html).

<!-- style="background-color: #6EC7D9;"--> 
> __Example__
>
> You can find an example of how to retrieve data via an API in the material of the Infra4NextGen Workshop on  "Open science and reproducible research in RStudio and Jupyter Notebook”. In this case, Franz Eder used the R package *dataverse* to access the [AUSSDA Dataverse](https://data.aussda.at): Since AUSSDA (The Austrian Social Science Data Archive) relies on the same software as the Harvard Dataverse, its data is also accessible via the R package *dataverse*. In the script, you can also see that an API token/an API key was necessary to access the data (the key is not valid any more so the code will not run). Here the link to the script: [https://github.com/franzeder/I4NG-workshop/blob/main/scripts/script_workshop.R](https://github.com/franzeder/I4NG-workshop/blob/main/scripts/script_workshop.R).

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz XI__ 
>
>Which statements about APIs are true? 
> 
>Click on the lightbulb to get some hints!

-[[X]] APIs are interfaces that allow you to access repositories from within R or Python scripts.
-[[X]] APIs can increase the reproducibility of your research.
-[[ ]] You can access all repository with one universal R package (*getAPI*).
-[[X]] APIs are tailored to the specific repository software. Consequently, you need to find the name of the repository software to search for appropriate R packages (e.g. *dataverse* or *zen4r*).
[[?]] There are multiple correct answers.


## 5.2. The renv package -- keep your programming environment stable

Have you ever tried running syntax from a couple of years ago and noticed any differences? Have you ever tried running your colleague's code on your machine and you got different results? In both scenarios, you may have noticed:

* ... that results running on two different machines or obtained at two different points in time differed although there was no obvious reason for it: no error message, simply different figures and in the worst case, differences in whether or not the results met conventional levels of statistical significance. 
* ... that code did not run because the syntax changed or packages changed.

How can this be? Computers as well as statistical software change underlying algorithms from time to time. This means that regression results obtained by the most recent R version are not necessarily the same as results obtained by the R version from ten years ago. The changes can be marginal or clearly noticeable e.g. if they affect whether or not a coefficient reaches conventional levels of statistical significance.

At the same time, packages/libraries (for R or Python) may change over time: The syntax may change, algorithms may change or dependencies may change. Hence, if you work with multiple machines or try to run old code, the code may run fine in once case but you may get an error in a second case -- although you did not change a thing.

The R [*renv* package](https://rstudio.github.io/renv/) by Kevin Ushey and [Hadley Wickham](https://hadley.nz/)  is short for "reproducible environments" and offers a solution for these problems. The authors promise three benefits for R scripts: 

* "Isolated" -- which means that different versions of R packages do not interfere with each other "because renv gives each project its own private library". 
* "Portable" -- renv captures all the necessary information to re-create the exact environment at different devices.
* "Reproducible" -- "renv records the exact package versions you depend on, and ensures those exact versions are the ones that get installed wherever you go."

How does this work? The [package description](https://cran.r-project.org/web/packages/renv/index.html) states: "Using 'renv', you can create and manage project-local R libraries, save the state of these libraries to a 'lockfile', and later restore your library as required." You can find a more detailed description [here](https://rstudio.github.io/renv/articles/renv.html).

<!-- style="background-color: #E72E6B; color: white"--> 
>__Quiz XII__ 
>
>What problems can a stable programming environment (like the one provided by the *renv* package) solve? 
> 
>Click on the lightbulb to get some hints!

-[[X]] Getting different results on different devices.
-[[X]] Updating R packages on your machine without wondering how it may affect past projects.
-[[X]] Getting different results at different points in time.
-[[ ]] Never getting results where p > .05.
[[?]] There are multiple correct answers.
*** 
Solution: Stable research environments like the one you can obtain by means of the *renv* package store the information on the version of software and packages you use in a specific project. Whenever you start the project, this information is retrieved and the exact same programming environment is recreated. This helps preventing different results because of different versions of packages on different machines or points in time.
***

<!-- style="background-color: #6EC7D9;"--> 
> **Congrats**
>
> In this section you learnt about accessing datasets via an API and the renv package and to use these features to facilitate reproducible workflows.
>
> Now, go to the [summary](#21) to wrap up your learning!

# Summary

Congratulations! You completed the course “Open Science and Reproducible Research”.  

In this course you learned about principles and benefits of reproducible science and now have a deeper insight into  frequently used tools. You now know which tools you can use to develop a reproducible workflow for your own research projects. 

We are continually updating the course and incorporating feedback, so please do not hesitate to contact us at [AUSSDA](mailto:info@aussda.at). If you are interested in live events hosted by the Infra4NextGen project, please visit the [I4NG events site](https://infra4nextgen.com/i4ng-events/forthcoming-events/) and come join us at one of our events - we are hosting webinars, workshops and hackathons regularly!



<!-- style="background-color: #6EC7D9;"--> 
>__Where to go from here?__
>
> If you would like to dive deeper into the theoretical background, check out the [bibliography](#22).
>
>If you would like to start using GIT these are some valuable guides you can use:
>
>* Chacon, Scott, and Ben Straub. 2024. Pro Git: Everything You Need to Know about GIT. 2nd ed. New York, NY: Apress. https://github.com/progit/progit2/releases/download/2.1.438/progit.pdf. 
>
>* Bryan, Jennifer. 2018. “Excuse Me, Do You Have a Moment to Talk about Version Control?” The American Statistician 72 (1): 20–27. https://doi.org/10.1080/00031305.2017.1399928. 
>
>* Chacon, Scott, and Ben Straub. 2024. Pro Git: Everything You Need to Know about GIT. 2nd ed. New York, NY: Apress. https://github.com/progit/progit2/releases/download/2.1.438/progit.pdf. 
>
>* Vuorre, Matti, and James P. Curley. 2018. “Curating Research Assets: A Tutorial on the Git Version Control System.” Advances in Methods and Practices in Psychological Science 1 (2): 219–36. https://doi.org/10.1177/2515245918754826. 
>
>If you prefer other formats on Git, you can also find plenty of online training material on Git, e.g.: 
>
>* Online courses hosted by the [Code Academy](https://www.codecademy.com/)
>
>* [Git introduction by the MIT](https://missing.csail.mit.edu/2020/version-control/)
>
> If you would like to dive into Quarto, the project's websites offers a comprehensive introduction: [https://quarto.org/](https://quarto.org/).

---
![Infra4NextGen Logo](images/Infra4NextGen_logo_resized.jpg  "https://infra4nextgen.com/") ![CESSDA Logo](images/cessda_logo.png  "https://www.cessda.eu/") 

# Bibliography

Peikert, Aaron, Caspar J. van Lissa, and Andreas M. Brandmaier (2021). "Reproducible Research in R: A Tutorial on How to Do the Same Thing More
Than Once". In: Psych 3.4, pp. 836–867. DOI: [10.3390/psych3040053](https://doi.org/10.3390/psych3040053).

Pontika, Nancy et al. (2015). "Fostering open science to research using a taxonomy and an eLearning portal”. In: Proceedings of the 15th International Conference on Knowledge Technologies and Data-Driven Business. i-KNOW ’15. Graz, Austria: Association for Computing Machinery. DOI: [10.1145/2809563.2809571](https://doi.org/10.1145/2809563.2809571).

Ramachandran, Rahul, Kaylin Bugbee, and Kevin Murphy (2021). "From Open Data to Open Science". In: Earth and Space Science 8.5, pp. 1–17. DOI: [10.1029/2020EA001562](https://doi.org/10.1029/2020EA001562).

Rokem Ariel, Ben Marwick and Valentina Staneva (2017). "Assessing Reproducibility". In: The Practice of Reproducible Research: Case Studies and
Lessons from the Data-Intensive Sciences. Ed. by Daniel Turek Justin Kitzes and Fatma Deniz. University of California Press. available via: http://www.practicereproducibleresearch.org/.

Stark, Philipp (2017). "Preface". In: The Practice of Reproducible Research: Case Studies and Lessons from the Data-Intensive Sciences. Ed. by Daniel Turek Justin Kitzes and Fatma Deniz. University of California Press. available via: http://www.practicereproducibleresearch.org/.

Wilkinson, M. D. et al. (2016). "The FAIR Guiding Principles for scientific data management and stewardship". In: Scientific Data 3.1. DOI: [10.1038/sdata.2016.18](https://doi.org/10.1038/sdata.2016.18).


