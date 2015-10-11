# mvn-search-cli
CLI script for searching artifacts at maven central

## Requirements
- Make sure you have python 2.7+ (<3) installed and the mvn-search script executable
- update your PATH variable to include the executable.

## Usage
```
mvn-search [-h] [-r max_results] [-f format] [-v] query
```
The supported formats are: 'table', 'mvn', 'buildr', 'ivy', 'grape', 'gradle', 'sbt', 'leiningen'. 'table' is the default output.

## Examples
Search for vertx artifacts:
```
→ mvn-search vertx
┌────────────────────────────────────────────────────────────┐
│        group id       │       artifact id        │ version │
├────────────────────────────────────────────────────────────┤
│              io.vertx │       vertx-dependencies │   3.1.0 │
│ com.englishtown.vertx │ vertx-httpservlet-parent │   2.1.0 │
│ com.englishtown.vertx │   vertx-cassandra-parent │   3.1.0 │
│ com.englishtown.vertx │   vertx-zookeeper-parent │   2.1.0 │
│ com.englishtown.vertx │      vertx-jersey-parent │   4.2.0 │
│ com.englishtown.vertx │        vertx-when-parent │   4.1.0 │
│ com.englishtown.vertx │       vertx-guice-parent │   2.1.0 │
│ com.englishtown.vertx │         vertx-hk2-parent │   2.1.0 │
│ com.englishtown.vertx │         oss-parent-vertx │   2.1.0 │
│              io.vertx │              vertx-stack │   3.1.0 │
└────────────────────────────────────────────────────────────┘
```
Search for the first three results for vertx artifacts with mvn specific output:
```
→ mvn-search vertx -r 3 -f mvn
<dependency>
  <groupId>io.vertx</groupId>
  <artifactId>vertx-dependencies/artifactId>
  <version>3.1.0</version>
</dependency>
<dependency>
  <groupId>com.englishtown.vertx</groupId>
  <artifactId>vertx-httpservlet-parent/artifactId>
  <version>2.1.0</version>
</dependency>
<dependency>
  <groupId>com.englishtown.vertx</groupId>
  <artifactId>vertx-cassandra-parent/artifactId>
  <version>3.1.0</version>
</dependency>
```
