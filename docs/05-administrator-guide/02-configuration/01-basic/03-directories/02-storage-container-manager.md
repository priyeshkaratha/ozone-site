---
sidebar_label: Storage Container Manager
---

# Directory Configurations for Storage Container Manager

This section describes the directory-related configuration properties used by the Storage Container Manager (SCM).

| Property Name                       | Description                                                                                                                                              | Tags                              | Default/Example Value                            | Sample Value                   |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------- | ------------------------------------------------ | ------------------------------ |
| `ozone.scm.db.dirs`                 | Directory where SCM stores its metadata (RocksDB). SCM creates the directory if it does not exist. If not defined, falls back to `ozone.metadata.dirs`. | OZONE, SCM, STORAGE, PERFORMANCE | Empty (creates directory if it doesn't exist)    | `/var/data/ozone/scm`          |
| `ozone.scm.db.dirs.permissions`     | Permissions for SCM metadata directories. Octal or symbolic format.                                                                                     |                                   | `700`                                            | `700`                          |
| `ozone.scm.ha.ratis.storage.dir`    | Directory where SCM stores its Ratis (Raft) log files. Should use fast storage like SSD for optimal performance.                                         | OZONE, SCM, HA, RATIS             | Falls back to `ozone.metadata.dirs` if undefined | `/var/data/ozone/scm/ratis`    |
| `ozone.scm.ha.ratis.snapshot.dir`   | Directory for SCM Ratis snapshot files downloaded from the leader during HA follower recovery. Falls back to `ozone.metadata.dirs` if not defined.       | OZONE, SCM, HA, RATIS             | Falls back to `ozone.metadata.dirs` if undefined | `/var/data/ozone/scm/snapshot` |
| `ozone.scm.datanode.id.dir`         | Directory where Datanodes store their `datanode.id` file. The directory is created if it does not exist. Falls back to the metadata directory if unset.  | OZONE, MANAGEMENT                 | Falls back to `ozone.metadata.dirs` if undefined | `/var/data/ozone/scm`          |
