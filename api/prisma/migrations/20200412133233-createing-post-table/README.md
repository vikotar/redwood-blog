# Migration `20200412133233-createing-post-table`

This migration has been generated at 4/12/2020, 1:32:33 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "quaint"."Post" (
    "body" TEXT NOT NULL DEFAULT '' ,
    "createAt" DATE NOT NULL DEFAULT '1970-01-01 00:00:00' ,
    "id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,
    "title" TEXT NOT NULL DEFAULT '' 
) 
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200412133233-createing-post-table
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,19 @@
+datasource DS {
+  provider = "sqlite"
+  url      = env("DATABASE_URL")
+}
+
+generator client {
+  provider      = "prisma-client-js"
+  binaryTargets = env("BINARY_TARGET")
+}
+
+// Define your own datamodels here and run `yarn redwood db save` to create
+// migrations for them.
+// TODO: Please remove the following example:
+model Post {
+  id       Int      @default(autoincrement()) @id
+  title    String
+  body     String
+  createAt DateTime @default(now())
+}
```


