# learn-jenkins

Jenkins notes and important plugins

## Start up Jenkins as code

Jenkins server exposes few APIs which can be used to configure Jenkins via code.

Few developers have already written few groovy scripts which calls those APIs and configure Jenkins.

The group of groovy scripts can be found in [GitHub](https://github.com/buildit/jenkins-startup-scripts). Popularly known as **Jenkins Startup Scripts**.

The **Jenkins Startup Scripts** runs in conjunction with **jenkins-startup-scripts-runner** and can be found here [GitHub](https://github.com/buildit/jenkins-startup-scripts-runner). This is a framework which enable Jenkins to configure on startup.

To download and use of please refer the **GitHub mentioned** above. For reference each jenkins.config file will have the below code

```groovy
startupScripts=[
        bintray: [
                artifactPattern: 'https://dl.bintray.com/buildit/maven/com/buildit/[module]/[revision]/[module]-[revision].[ext]',
                artifacts: [":jenkins-startup-scripts:X.X.X@zip"]
        ]
]
```

Remember that the Groovy scripts are there in `Jenkins Startup Scripts` which in turns calls the Jenkins APIs. These scripts can be extended.
