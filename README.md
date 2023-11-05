# Git diff filter for OpenPGP

```sh
git config diff.sqinspect.binary true
git config diff.sqinspect.textconv "sq inspect --certifications"
```

And it works like that:

```diff
$ git show ce1f869d15d093e5e1d02e6df1844eafec1348f4
commit ce1f869d15d093e5e1d02e6df1844eafec1348f4
Author: Wiktor Kwapisiewicz
Date:   Sun Nov 5 16:05:00 2023 +0100

    Add attributes

diff --git a/.gitattributes b/.gitattributes
new file mode 100644
index 0000000..31d1ce5
--- /dev/null
+++ b/.gitattributes
@@ -0,0 +1 @@
+*.asc diff=sqinspect
diff --git a/file.asc b/file.asc
index 39ac11c..2068ed0 100644
--- a/file.asc
+++ b/file.asc
@@ -1,4 +1,4 @@
-/tmp/git-blob-pG4rQz/file.asc: OpenPGP Keyring.
+/tmp/git-blob-wflotm/file.asc: OpenPGP Keyring.
 
 OpenPGP Certificate.
 
@@ -4702,9 +4702,6 @@ Public-key size: 2048 bits
       Key flags: transport encryption, data-at-rest encryption
 
          UserID: Jonathan Steel <jsteel@archlinux.org>
-  Certification: Creation time: 2023-10-29 19:37:29 UTC
-                 Alleged certifier: 3572FA2A1B067F22C58AF155F8B821B42A6FDCD7
-                 Hash algorithm: SHA512
   Certification: Creation time: 2022-12-01 16:38:10 UTC
                  Alleged certifier: 69E6471E3AE065297529832E6BA0F5A2037F4F41
                  Hash algorithm: SHA512
```
