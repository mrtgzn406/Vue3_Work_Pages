# Description

I get this course from the channel named "Codevolution" on the YouTube platform. (This set will continue.)

Here is the [link](https://youtube.com/playlist?list=PLC3y8-rFHvwgeQIfSDtEGVvvSEPDkL_1f)


## 1.) Questions: 

### a ) How to create and run a Vue project ?

In order to use the Vue.js framework, we must first download the Node.js framework to our computer.
Download link: https://nodejs.org/en/ 

Note : Downloading the "LTS" version is recommended because using the latest version can rise some problems.

Then we have to open the command line and select the folder where we will create our project by typing 
**cd 'file-path'** there. So the command line will work there.

Then, to download the command line interface of Vue.JS, we type **npm install -g @vue/cli** on the command line and 
Vue Cli (command line interface) is downloaded to the pc.
Then we start creating the project. To create a project, we write **vue create 'project-name'**, then a folder is 
created with that name and all the related files of Vue.js come in that folder, the work of creating the project is 
finished at this stage.

Then, in order to run the project, we must first download the project dependencies, for this we type **npm install** 
on the command line (We just need to run this command once in the folder directory where we will work).
Finally, we type **npm run serve** on the command line to run the project and the project is running.

Warning: If you want to rename a VueJS project folder via vs code, you have to close all terminals (cmd's) located 
in that folder otherwise, you may get an error. If you do the renaming process via normal file explorer, then do it 
after closing vs code.


### b ) When I download and try to run a project from this repository, I am getting errors. What's wrong ?

Normally every vue project has a folder that named "node_modules" because vue projects can launch with dependencies
like "node_modules", and if there is not a such folder then project will not work and we get errors. 
We can't run the any vue project that we upload this repository because "node_modules" package is not uploaded here.
Because "node_modules" folder has too many folders and files that causing project too big file size to be uploaded
and maintain with git. And as we know, every vue project has its own "node_modules" folder and every "node_modules" 
folder has 130 + mb file size and including so many folders and files like 10.000+. Supposing that, we must upload all files for each project, that is completey a mess and not required. 

Instead, we upload all vue  folder except "node_modules" folder and some other unnecessary folder like "dist" to 
avoid such  mess. But we don't upload files manually, we are using git version control system to upload files to our
github.  Because also we want to see the changes, addings and deletions process that we made in our project and 
take advantage of version control system. As a result, we uploaded our projects without "node_modules" folder and that is the most important folder we don't upload. Because to run the project, this folder definitely required.

So, if we want to download and run a project from this repository,  we should take these steps: 

1.) Download the project folder from this repository.

2.) Open the command line and navigate to the relevant project directory which you downloaded. 

3.) Write **npm install** on the command line, press Enter and wait till downloading process is finished.

4.) Write **npm run serve** on the command line to run the project.



