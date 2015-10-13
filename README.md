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

The query supports all coordinates, classname and SHA-1 checksum parameters:
* g:group.identifier
* a:artifact.identifier
* v:version.identifier
* l:classifier
* p:packaging-type
* fc:fully.classified.classname
* c:classname
* 1:hash

These query parameters can be mixed together. if separated by the AND keyword, all
parameters must be satisfied. e.g. "g:io.vertx AND a:vertx-core AND v:3.1.0"

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
Search for the first three results of artifacts from io.vertx with mvn specific output:
```
→ mvn-search -f mvn -r 3 g:io.vertx
<dependency>
  <groupId>io.vertx</groupId>
  <artifactId>vertx-stack-npm/artifactId>
  <version>3.1.0</version>
</dependency>
<dependency>
  <groupId>io.vertx</groupId>
  <artifactId>vertx-stack-docs/artifactId>
  <version>3.1.0</version>
</dependency>
<dependency>
  <groupId>io.vertx</groupId>
  <artifactId>vertx-stack-docker/artifactId>
  <version>3.1.0</version>
</dependency>
```
