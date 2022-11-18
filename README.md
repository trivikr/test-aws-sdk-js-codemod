# test-aws-sdk-js-codemod
Test repo for aws-sdk-js-codemod

## Usage

```console
$ npx aws-sdk-js-codemod -t v2-to-v3 src/example.ts 
Processing 1 files... 
Spawning 1 workers...
Sending 1 files to free worker...
Browserslist: caniuse-lite is outdated. Please run:
  npx browserslist@latest --update-db
  Why you should do it regularly: https://github.com/browserslist/browserslist#browsers-data-updating
All done. 
Results: 
0 errors
0 unmodified
0 skipped
1 ok

$ git diff
diff --git a/src/example.ts b/src/example.ts
index 99bc80b..bb099eb 100644
--- a/src/example.ts
+++ b/src/example.ts
@@ -1,7 +1,7 @@
-import AWS from "aws-sdk";
+import { DynamoDB } from "@aws-sdk/client-dynamodb";
 
 const region = "us-west-2";
-const client = new AWS.DynamoDB({ region });
+const client = new DynamoDB({ region });
 client.listTables({}, (err, data) => {
   if (err) console.log(err, err.stack);
   else console.log(data);
```