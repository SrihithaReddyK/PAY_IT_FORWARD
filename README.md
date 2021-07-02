# PAY IT FORWARD (2021)
## DOWNLOAD LINKS
### Front-end installation: 
• Microsoft VS code editor:<br />
https://code.visualstudio.com/download<br />
• Node NPM with NVM:<br />
https://medium.com/@lucaskay/install-node-and-npm-using-nvm-in-mac-or-linux-ubuntu-f0c85153e173<br />
• Download node 8.10:<br />
https://nodejs.org/en/download/<br />

### Back-end Installation:<br />
• Intellij IDEA Community Edition  
https://www.jetbrains.com/idea/download/<br />
• Eclipse IDE<br />
https://www.eclipse.org/downloads/<br />
• MySQL Standard Edition<br />
https://www.oracle.com/in/mysql/standard.html<br />
• MySQL Workbench<br />
https://dev.mysql.com/downloads/workbench/<br />
• Postman REST Client<br />
https://www.getpostman.com/downloads/<br />
• Git<br />
https://www.atlassian.com/git/tutorials/install-git<br />
• OpenJDK/Oracle 8:<br />
https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html<br />
https://docs.oracle.com/javase/8/docs/technotes/guides/install/mac_jdk.html<br />

## FRONT-END SET-UP
1. Copy the source code from the CD to the local machine.<br />
2. Open Terminal or Command Prompt and run:<br />
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;npm install<br />
   to set up node modules in your project.<br />
3. If complications arise, run:<br />
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;npm audit fix (or) npm audit fix --force<br />
4. Then, run yarn install (optional), if you want to run the project faster.<br />

## BACK-END SET-UP<br />
1.  After setting up MySQL Workbench, import the DB Tables (Source Code -> DB Tables), after running the project once (see next section). <br />
    You should have empty DB Tables ready for import before this step.<br />
3.  To configure idea source configuration in build.gradle file:<br />
    plugins {<br />
         &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;....<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;id 'idea'<br />
    }<br />
    ..<br />
    idea {<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;module {<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sourceDirs += file("app")<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;testSourceDirs += file("test")<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;scopes.COMPILE = [plus: [configurations.play], minus: []]<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;scopes.RUNTIME = [plus: [configurations.playRun], minus:[configurations.play]]<br />
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;scopes.TEST = [plus: [configurations.playTest], minus: [configurations.playRun]]<br />
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br />  
  }<br />
  ...<br />

3.  To Run (Run config):<br />
    In IDEA:<br />
    •	Open run configuration window<br />
    •	Click on (+) and Select Gradle<br />
    •	Name: as you need<br />
    •	Gradle project: your root project or location of your root project<br />
    •	Tasks: runPlayBinary<br />

4.	Go to IntelliJ preference (Alt+Shift+S)<br />
    •	Go to [Build, Execution and Deployment] section<br />
    •	Select build tool as gradle<br />

5.	For Database Connectivity:<br />
    •	Open MySQL Command Line Client and enter your server password.<br />
    •	“create database project_db_name;” //to create database<br />
    •	“use project_db_name;” //to use the project database<br />
    •	“SET GLOBAL sql_mode = (SELECT REPLACE (@@sql_mode, ‘ONLY_FULL_GROUP_BY’,’’))”<br />
      //to change global settings of SQL for the project<br />

## RENDERING THE PROJECT<br />
1.  Run the back_end folder in IntelliJ by clicking the green run button. <br />
    Then, the terminal says: <br />
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;“9 actionable tasks: 1 executed, 8 up-to-date<br />
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Waiting for changes to input files of tasks...”<br />
    In the end it should say “BUILD SUCCESSFUL”.<br />

2.  To render front_end:<br />
    There are 2 ways via Terminal or Command Prompt:<br />
	        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;npm start<br />
	        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;yarn start<br />
    If the browser does not open the localhost automatically, open http://localhost:3000/ in the browser.<br />
3.  Register and login for the access of the application and explore.<br />
# PAY_IT_FORWARD
