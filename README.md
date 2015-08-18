# EPICS V4 Jenkins Jobs

The templates and definitions in this repository are used to create
the Jenkins jobs for the EPICS V4 Continuous Integration system instance
hosted on [CloudBees](https://openepics.ci.cloudbees.com).

## Jenkins Job Builder

The tool used to create the XML job definitions is called
[Jenkins Job Builder](http://docs.openstack.org/infra/jenkins-job-builder/).

It takes simple descriptions of Jenkins jobs in YAML or JSON format
and uses them to create the XML files that configure Jenkins.

## How-To

### Prepare

Install Jenkins Job Builder (JJB) and clone this repository.

Add your CloudBees credentials to the JJB configuration file `cloudbees.ini`.

### Test

To check the generated XML, use JJB's `test` command:
```
$ jenkins-jobs --conf ./cloudbees.ini test templates:cloudbees
```
You can add job names as additional arguments to limit the XML generation
to the specified jobs.

### Update

To update the jobs on CloudBees, use JJB's `update` command:
```
$ jenkins-jobs --conf ./cloudbees.ini update templates:cloudbees
```
Job names as additional arguments will update only the specified jobs.
