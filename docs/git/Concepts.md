## GIT Concepts

### Architecture
GIT is three-tree architecture.
This is the workflow of how commit works.

                 git add               git commit   
    working copy ------> Staging Index --------> Repository

* Each commit corresponds to some Snapshots or ChangeSets.
* Uses checksum for checking data integrity. It uses SHA-1 hash algorithm to create checksums

---

### Merkle Tree or Hash Tree
Git uses Merkle/Hash Tree.
* Merkle trees are used in distributed systems for efficient data verification. 
* They are efficient because they use hashes instead of full files.
* Hashes are ways of encoding files that are much smaller than the actual file itself.

---