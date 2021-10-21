# sonar_quality_analysis_report_mail
Send Quality Analysis Report Mail Using Github Actions.

In this repository, you can find ready-to-use GitHub action to send the Sonar quality analysis report using mail every Monday.

# Sonar quality analysis criteria
1. Analysis should not be older than 7 days
2. Project Analysis should be passed

If there is not even a single Criteria match, we will consider it a failure and move that project into the Failed analysis.

# Steps
1. Clone this repo

2. Move the `sonar_quality_check.yml` to .github/workflows directory and push the code

2. Configure the Secret variables by going to GithubProject > Settings > Secrets, and clicking New repository secret.

    Add the following 
    ```
    #Sender mail credentials, make sure that email account is less secure
    MAIL_PASSWORD # Email password
    MAIL_USERNAME # Email ID

    #Sonar credentials
    TOKEN # sonar Token to access all projects
    URL # URL of the sonar
    EMAIL # Receptiant email address can be a group mail.
    ```
3. Now you will get Sonar quality analysis report on every Monday

## Sonar Token Permission
Must have access to the following API's
```
/api/projects/search
/api/qualitygates/project_status
/api/components/search_projects
```
