# Version Control

**Important:** You should complete this lab with the help of a partner. In this handout, we will name `L` the *Leader* role and `H` the *Helper* role. The two partners should do the exercise twice to take alternatively the *Leader* and *Helper* roles. The two partners should work on separated computers as if they were working remotely on the same project.

In this handout, we will use keywords such as *clone*, *stage*, *commit*, *push* and *pull*. If you are not familiar with those terms and/or how to perform these actions with the `git` command, you should read through the [Git Handbook](https://guides.github.com/introduction/git-handbook/) first. 

To get a full mark in this lab:

- your code must compile and execute by generating some kind of text output
- the git logs should demonstrate that you have generated and solved the two types of conflicts practiced below
- the git logs should have meaningful log messages that characterize the changes you made to the code base
- the repository should not contain any file generated automatically (binaries and so on) 
- the `.gitignore` file should contain instructions to ignore Java build files

## Clone a repository, compile and run the code

First, we are to fetch, compile and run the code stored on a remote version control repository on Github. 

1. As *L*, clone your *L03* repository on your computer.

2. As *L*, compile and run the app source code. You can either do it through your favorite Java code editor or through the command line directly. You should not change the code or move files around to do so. Yet, this is how the course staff is going to run and check your code: 

```
javac -d bin src/main/java/ca/utoronto/app/App.java
java -cp bin ca.utoronto.app.App
```

# Pushing and pulling changes

Now, we are going to practice how to make changes to the code base and push these changes to Github. 

3. As `L`, invite `H` to collaborate on your code. To do so, open the repository page on Github, click on `settings` then `collaborators` from the left menu, and adds `H` Github username as collaborator. 

4. As `H`, accept the invitation that was sent to you by email or directly through Github, and clone the repository on your computer. 

5. As `L`, modify `App.java` by adding some java code (at least 5 lines of code that is up to you). Make sure that your code compile and run. Thus, stage the changes you made to the source code (do not stage the `.class` file), make a commit (with a meaningful commit message that characterize the changes you made) and push it to Github.

6. As `H`, pull the latest commit made by `L` on your local copy. 

## Dealing with conflicting changes that Git can handle automatically

At this stage, both `H` and `L` should have the same version of the code on their computer. Now, we are going to see what happens when two people make changes to the repostory at the same time. In the scenario below, we are going to see that Git is able to merge changes automatically when these changes are not touching the same lines in the code. 

7. As both, modify the file `App.java` but **do not change the same line of code** on your respective local copy.

8. As `L`, push your changes to Github first.

9. As `H`, after trying to push your changes to Github, `git` tells you that a more recent commit has been pushed first and asks you to pull the updated version from Github. There will be some conflicts but they should be automatically merged by `git` and you should be prompted to enter a merge message. To do so, type `i` (for insert), then type the message, press the `<esc>` key (to exit insert mode) and finally `:wq` to save and close the code editor.  Make sure that your code compile and run. Commit the changes again and push them to Github. 

10. As `L`, pull the new version from Github. 

# Dealing with conflicting changes that Git cannot handle automatically

At this stage, both `H` and `L` should have the same version of the code on their computer. Now, we are going to see what happens when two people make changes to the same lines of code at the same time. In this case, one person will have to resolve the conflicts by modifying the code manually.  

11. As `L` and `H`, modify the **the same** line of code in the file `App.java`. 

12. As `H`, pushes the changes to Github first.

13. As `L`, after trying to push your changes to Github, `git` tells you that a more recent commit has been pushed first and asks you to pull the updated version from Github. Now, `git` complains that there are conflicts that need to be solved manually. Read the conflict report and edit all concerned files to solve these conflicts. Make sure that your code compile and run. Finally, push these changes  Github. 

14. As `L`, pull the new version from Github.

# Create a .gitignore to avoid pushing generated files

The repository should always be clean meaning it should not contain files that are automatically generated. If you have such files, you should delete them from the repository. Yet, it is always annoying to have these files appearing as untracked files when you check `git status`. However, it is possible to instruct `git` to ignore these files using a `.gitignore` file. 

16. Create a file called `.gitignore` at the root of your repository with the instruction to ignore all `.class` files:

```
*.class
```

17. Push this file to Github and run `git status` to check that these files are not ignored










