# test-aws-sdk-js-codemod
Test repo for aws-sdk-js-codemod

## Usage

```console
$ node -v
v16.18.1

$ npm -v
8.19.2

$ npx aws-sdk-js-codemod -t v2-to-v3 src/example.ts 
Processing 1 files... 
Spawning 1 workers...
Sending 1 files to free worker...
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
