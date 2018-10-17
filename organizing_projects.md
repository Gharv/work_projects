Organizing Your Projects And Creating A Package
================

Why Organization Is Neccessary
==============================

Organization is very important in many walks of life and when writing code and analyzing data, it is no different. Creating an organized project not only makes it **easier** for other people to understand what you are trying to accomplish in a given project but more importantly it makes it easier for yourself. The upfront cost of organizing your projects will save you immensely any time you come back to a project may be it for **re-use** or to take certain ideas and implement them into a new project. There is also an added benefit that if you start a project thinking about organization then your code will also be more organized because you need to be able to fit the code you are writing into the overall organizational structure you have previously decided on.

What Does Organization Do For Us?
=================================

Everyone has their own way of doing things and organization of a project is no different. However I will show you some very basic ideas, which come from the way packages are structured to give you an idea of how many people go about tackling the organizational problem.

The first thing is developing a structure for our project. This involves creating folders and files to hold any data we may use for a given project. Since we are talking about analytic projects I will be focusing on a typical project structure for analyzing data sets.

So an organized project layout helps to:

-   Keep the project readable and portable to others
-   Allow for easy pickup after a long break
-   Keep integrity of data

We covered the first two but what do I mean by data integrity? Data integrity refers to **consistency** and **accuracy** of data. We can accomplish this consistency by separating parts of our project. For example we will separate our data files (files that just contain observations, such as a csv or database file), our code files (containing functions that we have created to make reading easier and simpler) and our analysis file which is our testing bed containing what we are actually trying to analyze. Accuracy is achieved because we treat the data files as read only meaning we do not modify them and save over the top, instead we modify them within our code.

Our Project Structure
=====================

This gives us our overarching project structure that looks like:

> proj/
> |--- R/
> |--- data/
> |--- analysis.R

R Folder
--------

The `R` folder contains code files with function definitions and **only** function definitions, meaning no code that actually runs. Code the runs will be in the `analysis.R` file

data Folder
-----------

The data folder as we talked about previously contains storage data. Depending on the project, this could be csv files or database files.

analysis.R File
---------------

Contains the code that uses functions defined in the `R` folder and data from the `data` folder to preform your desired analysis.

The `analysis.R` file will look like

    library(package_a)
    library(package_b)
    source("R/functions.R")
    source("R/utilities.R")

followed by code the collects data from the `data` folder, mungs the data, then runs analysis and generates figures to convey the overall ideas.

Very Simple Project Template
============================

For a very small project and typically how I start all my projects, not knowing how deep I want to go, I will use the following template.

> proj/
> |--- analysis-functions.R
> |--- data/
> |--- analysis.R

Here I do not have an `R` folder yet because I may have only a few functions. Even though the project may be small it is still very important to keep functions and analysis separate.

When I First Started
--------------------

I was self taught in programming and analyzing data sets. In the beginning I would write every bit of code in a single file, I would not have functions and everything would be tailor made for the specific idea I was trying to tackle at that moment. Later I would find myself coming across situations that I have already solved but for different data sets. This lead me to feel like I did something wrong. For me the whole reason to get into programming instead of just doing analysis on an excel worksheet was to start automating things I do over and over. So I went back to study and research better automation leading me to functionalizing everything I could to make my work **reproducible** for myself.

Conclusion
==========

Organization will help keep you sane and save a lot of time, it is well worth the little upfront time. This is also a great beginning for organizing projects because this follows a very similar pattern to the projects are built. Getting used to these simple ideas and implementing them into your own projects will also help you understand and interpret others projects that follow the same pattern (which many do). There is much more that can go into organizing a project and creating a package. Next we will look into testing of our code.
