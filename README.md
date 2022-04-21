sig-metrics.jar README
======================================

sig-metrics-java11.jar requires Java 11 - use this for Coverity Connect version 2019.03 or later
sig-metrics-java8.jar requires Java 8 - use this for Coverity Connect versions older than 2019.03

======================================

Examples:
java -jar sig-metrics.jar -host connect1.example.com -port 8443 -ssl -user admin -passfile admin_pass.txt -datestart 2017-01-01 -dateend 2017-06-30 -detailed
java -jar sig-metrics.jar -url https://connect1.example.com:8443 -user admin -passfile admin_pass.txt -detailed

Usage:

usage: java -jar sig-metrics.jar [OPTIONS]
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
