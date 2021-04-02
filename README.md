Repository Init Content
=======================

To build use:
> mvn clean pre-integration-test jib:build

To run use:
> docker run -p 8090:8090 wcgartifactory-docker.jfrog.io/nextgen/emerald-bdp

To test how it works::
> docker run -e SPRING_DATASOURCE_USERNAME={USER-NAME} -e SPRING_DATASOURCE_PASSWORD={PWD} -e M2_HOME=/mvn -e NARAYANA_DBCP_ENABLED=true -u 100000 --read-only -v /tmp/shtran:/transaction-logs/ShadowNoFileLockStore/defaultStore:rw -v /tmp/pbtmp:/tmp:rw -v /Volumes/Work/development/java/pb-poc/emerald-bdp/src/main/jib/.m2:/.m2:rw -p 8090:8090 wcgartifactory-docker.jfrog.io/nextgen/emerald-bdp:0.1.0-SNAPSHOT
