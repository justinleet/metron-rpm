# metron-rpm
Used as a convenience to hold current build RPMs and mpack from Ambari Metron with the HDP 2.5.0.0 profile. Producing these is not automated.

If these are outdated, and new ones are desired, they can be produced from the Metron project itself.

* Clone the project from https://github.com/apache/incubator-metron and produce the artifacts

```
git clone https://github.com/apache/incubator-metron.git
mvn clean package -DskipTests -PHDP-2.5.0.0
cd metron-deployment
mvn clean package -DskipTests -Pbuild-rpms
mvn clean package -DskipTests -PHDP-2.5.0.0
```

Output will be in:
```
incubator-metron/metron-deployment/packaging/docker/rpm-docker/RPMS/noarch/*
```

```
incubator-metron/metron-deployment/packaging/ambari/metron-mpack/target/metron_mpack-1.0.0.0-SNAPSHOT.tar.gz
```
