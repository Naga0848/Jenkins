### In this repo, we will understand the basics of Jenkins

#### Commands to install Jenkins

    sudo curl -o /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo

    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
    # Add required dependencies for the jenkins package

    sudo yum install fontconfig java-21-openjdk jenkins -y
    sudo systemctl daemon-reload
    sudo systemctl start jenkins
    sudo systemctl enable jenkins

#### Shift Left Strategy

    app deploy in QA SIT UAT --> test
    PROD deploy --> testing, no scanning

    we are using shift-left strategy for our CICD pipelines, instead of testing and scanning after deploying the application in  high environment we are doing testing and scanning in DEV environment, so we can find the issues in early stages.

#### Disadvantages of Freestyle project

    freestyle pipelines --> create the pipeline in UI with some clicks.
    1. cant' restore if error comes
    2. can't track, no version control
    3. no body remember how to do it again
    4. can't re use
    5. time consuming