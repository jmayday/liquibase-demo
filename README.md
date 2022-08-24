![example workflow](https://github.com/jmayday/liquibase-demo/actions/workflows/maven.yml/badge.svg)

# liquibase-demo
Minimalistic project presenting issue with liquibase mongodb preconditions extension

mvn liquibase:status 
```
[INFO] Opened connection [connectionId{localValue:3, serverValue:611}] to localhost:27018
1 changesets have not been applied to root@localhost:27018
     changesets/changeset_02.xml::changeset_20220822_1250_1::jmayday
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
```

mvn liquibase:validate
```
[INFO] Opened connection [connectionId{localValue:3, serverValue:614}] to localhost:27018
[INFO] No validation errors found.
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
```

mvn liquibase:update
```
[ERROR] Error setting up or running Liquibase:
[ERROR] liquibase.exception.MigrationFailedException: Migration failed for changeset changesets/changeset_02.xml::changeset_20220822_1250_1::jmayday:
[ERROR]      Reason: 
[ERROR]           changelog.xml : Index Exists Precondition: userId_1 : class liquibase.ext.mongodb.database.MongoConnection cannot be cast to class liquibase.database.jvm.JdbcConnection (liquibase.ext.mongodb.database.MongoConnection and liquibase.database.jvm.JdbcConnection are in unnamed module of loader org.codehaus.plexus.classworlds.realm.ClassRealm @4beddc56)

```