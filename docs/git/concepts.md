## GIT Concepts

### Architecture
GIT is three-tree architecture.
This is the workflow of how commit works.

                 git add               git commit   
    working copy ------> Staging Index --------> Repository

* Each commit corresponds to some Snapshots or ChangeSets.
* Uses checksum for checking data integrity. It uses SHA-1 hash algorithm to create checksums

