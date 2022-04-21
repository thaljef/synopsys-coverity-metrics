# Synopsys Coverity Metrics Utility

## Description

The Synopsys Coverity Metrics utility is used to collect usage and performance
data from a Coverity server. When analyzed, this data can illustrate the actual
and potential value of your static analysis efforts.

## Basics

Use this for Coverity Connect version 2019.03 or later. Substitue to `COVERITY_URL` with the
URL that you use to access your Coverity Connect server:
```
wget https://github.com/thaljef/synopsys-coverity-metrics/raw/main/sig-metrics-0.9.3-java11.jar
java -jar sig-metrics-0.9.3-java11.jar -url COVERITY_URL -user admin -detailed
```

Use this for Coverity Connect versions earlier than 2019.3. Substitute `COVERITY_HOST` and
`COVERITY_PORT` with the correct values for your Coverity Connect server:
```
wget https://github.com/thaljef/synopsys-coverity-metrics/raw/main/sig-metrics-0.9.3-java8.jar
java -jar sig-metrics-0.9.3-java8.jar -host COVERITY_HOST -port COVERITY_PORT -ssl -user admin -detailed
```

## Command Options

```
 -host <arg>        (Optional) Hostname of the Coverity Connect server.
 -port <arg>        (Optional) Port of the Coverity Connect server.
 -path <arg>        (Optional) Path to the Coverity Connect server, if necessary.
 -url <arg>         (Optional) URL of the Coverity Connect server. Alternative to using -host, -port, and -path
 -user <arg>        (Required) Coverity login username.
 -password <arg>    (Optional) Coverity login password - will prompt if not provided as an option.
 -passfile <arg>    (Optional) File containing Coverity login password
 -ssl               (Optional) Enable SSL. (required for https - Coverity Connect's SSL certificates may need to be imported into the Java keystore)
 -months <arg>      (Optional) Number of months to gather metrics. Defaults to 12 months if not specified.
 -datestart <arg>   (Optional) YYYY-MM-DD Specify the start of a date range to gather metrics. Must be used with -dateend.
 -dateend <arg>     (Optional) YYYY-MM-DD Specify the end of a date range to gather metrics. Must be used with -datestart.
 -project <arg>     (Optional) Specify project(s) to run metrics on. Use quotes and separate project names with a comma to specify multiple projects. Eg "Project1, Project2"
 -stream <arg>      (Optional) Specify stream(s) to run metrics on. Use quotes and separate stream names with a comma to specify multiple streams. Eg "Stream1, Stream2"
 -excludeComponent  (Optional) Specify component(s) to exclude. Use quotes and separate component names with a comma to specify multiple components.
 -excludeFindBugs   (Optional) Excludes FindBugs defects.
 -excludeMisra      (Optional) Excludes MISRA defects.
 -detailed          (Optional) Enable detailed metrics mode.
 -comments          (Optional) Enable defect comments gathering.
 -legacy            (Optional) Uses API v7 to support Coverity Connect versions < 7.6.0.  Cannot be used with -detailed.
 -debug             (Optional) Show entire stacktrace on exceptions.
```
