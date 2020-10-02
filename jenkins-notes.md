# config.xml
```
<projectNamingStrategy class="jenkins.model.ProjectNamingStrategy$DefaultProjectNamingStrategy"/>
<workspaceDir>D:/Workspace/${ITEM_FULL_NAME}</workspaceDir>
<buildsDir>D:/Logs/${ITEM_ROOTDIR}/Build</buildsDir>

This value may include the following variables:

${JENKINS_HOME} — Absolute path of the Jenkins home directory
${ITEM_ROOTDIR} — Absolute path of the directory where Jenkins stores the configuration and related metadata for a given job
${ITEM_FULL_NAME} — The full name of a given job, which may be slash-separated, e.g. foo/bar for the job bar in folder foo

```
