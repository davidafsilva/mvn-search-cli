# mvn-search-cli
CLI script for searching artifacts at maven central

## Requirements
- Make sure you have python 2.7+ (<3) installed and the mvn-search script executable
- update your PATH variable to include the executable.

## Usage
```mvn-search <query>```

The I/O to perform a search for vertx would be something like this:
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
