## Centos Docker image with Tomcat, with different versions of java

[![Docker Stars](https://img.shields.io/docker/stars/chenmins/tomcat-centos.svg)]() [![Docker Pulls](https://img.shields.io/docker/pulls/chenmins/tomcat-centos.svg)]() [![Docker Automated buil](https://img.shields.io/docker/automated/chenmins/tomcat-centos.svg)]() [![Docker Build Statu](https://img.shields.io/docker/build/chenmins/tomcat-centos.svg)]()

[![](https://images.microbadger.com/badges/image/chenmins/tomcat-centos.svg)](https://microbadger.com/images/chenmins/tomcat-centos "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/chenmins/tomcat-centos.svg)](https://microbadger.com/images/chenmins/tomcat-centos "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/license/chenmins/tomcat-centos.svg)](https://microbadger.com/images/chenmins/tomcat-centos "Get your own license badge on microbadger.com")

[![GitHub forks](https://img.shields.io/github/forks/chenmins/tomcat-centos.svg?style=social&label=Fork)]() [![GitHub stars](https://img.shields.io/github/stars/chenmins/tomcat-centos.svg?style=social&label=Star)]() [![GitHub watchers](https://img.shields.io/github/watchers/chenmins/tomcat-centos.svg?style=social&label=Watch)]() [![GitHub followers](https://img.shields.io/github/followers/chenmins.svg?style=social&label=Follow)]()


### Versions

**Tomcat 8 Version**: `8.5.3`  
**Tomcat 7 Version**: `7.0.72`  
**JRE8/JDK8 Version**: `8u92-b14`  
**JRE7/JDK7 Version**: `7u80-b15`

### Tags

| Tomcat version | Java version      | tags                                 | Size                                                                                                                                              |
|:---------------|:------------------|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Tomcat 7       | Oracle Java 7 JRE | `latest` / `tomcat7` / `jre7tomcat7` | [![](https://images.microbadger.com/badges/image/chenmins/tomcat-centos.svg)](https://microbadger.com/images/chenmins/tomcat-centos "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/chenmins/tomcat-centos.svg)](https://microbadger.com/images/chenmins/tomcat-centos "Get your own version badge on microbadger.com") |


### Usage

Some indications:

* Tomcat installation directory is `/opt/tomcat` (`$TOMCAT_HOME`/`$CATALINA_HOME`). Executable scripts are found in directory `$TOMCAT_HOME/bin` and the application base (*appBase*) directory is `$TOMCAT_HOME/webapps`.
* The path of file `catalina.out` is managed by the variable `$CATALINA_OUT`, and its value by default is `/dev/null` (disabled).
* Apache logs are written into directory `/logs/`.

There are two ways to use this image:

1. Use it as base image for other images. For example:

  ```
  FROM chenmins/tomcat-centos:tomcat7
  ```

1. Use the image directly, and copy the `.war` files directly into the *appBase* directory. For example:

  ```
  docker run -it --rm chenmins/tomcat-centos /opt/tomcat/bin/catalina.sh run
  docker cp ./sample.war tomcat-ci:/opt/tomcat/webapps/sample.war
  ```
