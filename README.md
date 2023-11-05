# Git diff filter for OpenPGP

```sh
git config diff.sqinspect.binary true
git config diff.sqinspect.textconv "sq inspect --certifications"
```

And it works like that:

```diff
$ git show ed26a99e5650d75d7f472bc3f3c8bb54f8755e5e
commit ed26a99e5650d75d7f472bc3f3c8bb54f8755e5e (HEAD -> main)
Author: Wiktor Kwapisiewicz
Date:   Sun Nov 5 16:23:30 2023 +0100

    Add certification

diff --git a/file.asc b/file.asc
index 2068ed0..39ac11c 100644
--- a/file.asc
+++ b/file.asc
@@ -1,4 +1,4 @@
-/tmp/git-blob-4hzrvR/file.asc: OpenPGP Keyring.
+/tmp/git-blob-NFuCcs/file.asc: OpenPGP Keyring.
 
 OpenPGP Certificate.
 
@@ -4702,6 +4702,9 @@ Public-key size: 2048 bits
       Key flags: transport encryption, data-at-rest encryption
 
          UserID: Jonathan Steel <jsteel@archlinux.org>
+  Certification: Creation time: 2023-10-29 19:37:29 UTC
+                 Alleged certifier: 3572FA2A1B067F22C58AF155F8B821B42A6FDCD7
+                 Hash algorithm: SHA512
   Certification: Creation time: 2022-12-01 16:38:10 UTC
                  Alleged certifier: 69E6471E3AE065297529832E6BA0F5A2037F4F41
                  Hash algorithm: SHA512
```
