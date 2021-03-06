
## Steps for using github repository in RStudio

### 1. Check Git settings in RStudio

* Check whether git is installed on your machine. 
    * on a mac open a terminal and type: `git --version`
    * you can download the latest version from (https://git-scm.com/download/)
    
* Check git setting in RStudio
    * In RStudio go to _Tools > Global Options_ and select __Git/SVN__
        
        ![](img/git_setup1.png)
        
        It should show the path to your git installation if RStudio has been able to find it.

### 2. Create a public key and copy to github

* If you do not see a path in the __SSH RSA Key__ dialog, select __Create RSA Key__

     ![](img/create_key1.png)
     
* Create the key and then select __View public key__ and copy it to the clipboard.

* Go to your github account and select settings from top right menu

     ![](img/add_key1.png)
     
* Select __SSH and GPG keys__

     ![](img/add_key2.png)

* Paste key from clipboard in the __Key__ dialog and add a title

     ![](img/add_key3.png)
     
     
### 3. Create a new repository on your github account

* On your github home page click on the __+ icon__ in top right corner and select __New repository__

   ![](img/create_repo1.png)


* Enter the name for the repository and select Create


   ![](img/create_repo2.png)


* Copy the URL for your repository

   ![](img/create_repo3.png)

### 4. Create a new RStudio project linked to github repository

* In RStudio select __File > New Project__

* Select __Version Control__

    ![](img/new_proj1.png)
   
* Select __Git__

    ![](img/new_proj2.png)

* Enter  

    1. repository URL copied from github when you setup your new repository
    2. name for the RStudio project (probably best to use same name as repository)
    3. location on your machine where you want to store the files
    4. check __Open in new session__

        ![](img/new_proj3.png)

* Select __Create project__. A new RStudio session window will pop up with any files in repository pulled from github. Here there are yet any files in repository.

    ![](img/new_proj4.png)
  
    
    On a mac a new RStudio icon will be shown in the dock with the project name across it ![](img/new_proj5.png)
    


### 5. Add some flies to the project

* Now you can add files to the project. For example create a _New Folder_ called **data** and add a csv file, e.g.


    ```
    write.csv(mtcars, 'data/datafile.csv', row.names=F)
    ```
    
* Create a new RMarkdown file and save it in the project

    ![](img/add_files1.png)
    
* All files in project are shown in the __Files__ tab. At this stage none of them are under version control

    ![](img/add_files2.png)


### 6. Add files to (local) version control

* You should see a GIT menu icon at the top of the project window

    ![](img/commit_files1.png)
    
* Select __Commit...__

    ![](img/commit_files2.png)
    
* The _Status__ column shows files and folders in the project that are either not under version control or have changed. To add a file or folder click the __Staged__ checkbox.

    ![](img/commit_files3.png)

* Add a message describing the changes you want to commit into version control and click __Commit__

    ![](img/commit_files4.png)
    
* These files are now committed to your local git repository and you can continue to make changes to the project files and track changes in the same way buy adding changes and committing them.

### 7. Add files to github repository

* To push these changes to your github repository click the __Push__ icon in the top right corner.

    ![](img/commit_files5.png)
    
* You should see a message indicating that changes to the local repository have been pushed up to your remote repository.

    ![](img/commit_files6.png)
    
* Check the repository on github and you should see the new files added.

    ![](img/commit_files7.png)


### 8. Add file(s) on github to repository

* You can add files to a github repository by uploading or creating them on the github site. For example you can add a `README.md` file if one doesn't exist:

    ![](img/add_remote1.png)

    * edit content
     ![](img/add_remote2.png)

    * Commit file
     ![](img/add_remote3.png)

* You'll see the new file in your repository. `README.md` file is treated in a special way and its content is displayed below the list of files. You should use this file as a way to describe the content and purpose of your repository.

    ![](img/add_remote4.png)


### 9. Syncing remote changes with your local repository

* If you (or your collaborators) have made remote changes to your repository on github you will need to **pull** those changes into your local repository. In the __Git__ menu in RStudio click on the __Pull__ icon

     ![](img/pull_files1.png)
     
* You should see a confirmation message if changes from the remote respository could be integrated into your local repository without conflicts.

     ![](img/pull_files2.png)
