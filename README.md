# Create a Freestyle job in Jenkins that runs a Java program using the Build Periodically feature, follow these steps:# 

# 1. Access Jenkins Dashboard:
  Open your Jenkins web interface and log in with your credentials.
#  2. Create a New Freestyle Job:
  From the Jenkins dashboard, click New Item.
  Enter a name for your job (e.g., JavaPeriodicJob).
  Select Freestyle Project as the job type.
  Click OK.
# 3. Configure the Freestyle Job:
  a. Source Code Management :
  Select the Git under the Source Code Management section.
  Provide the repository URL and branch to pull the Java code from Git
  Github URL: https://github.com/Nagadeops/JavaPeriodicJob
  Branch: main
  b. Build Triggers:
  Scroll down to the Build Triggers section.
  Check the Build periodically option.
  In the Schedule field, enter a cron expression to define when the job should run (e.g., H/5 * * * * to run every 5 minutes).
  Example cron:
  H/15 * * * * (every 15 minutes)
  H 12 * * * (at noon every day)
  * * * * * (every minute)
  Cron format:
  MINUTE HOUR DOM MONTH DOW

# c. Build Step:
  Scroll down to the Build section.
  Click on Add build step and select Execute shell (Linux/Mac)
  Enter the command to run your Java program.
  # Example for Linux/Mac:
    javac MyProgram.java
    java MyProgram

# d. Optional Post-build Actions:
  You can set up notifications (e.g., email notifications) if required under the Post-build Actions section.
  4. Save and Schedule the Job:
  Once the job is fully configured, click Save.
  Jenkins will now run the Java program periodically based on the cron schedule you've defined.
# 5. Monitor the Job:
  Under the Build History, you can see when the job runs.
  Click on any build to view the Console Output to ensure the Java program is running correctly.
  # Example Java Program:
  If you are just testing with a basic Java program, here’s an example:

  public class MyProgram {
      public static void main(String[] args) {
          System.out.println("Hello, Jenkins!");
      }
  }

  This setup allows you to periodically execute any Java program on a Jenkins Freestyle job.
