---
title: Metrics
description: Metrics related to backup and restore functionality
weight: 10
---

Backup and restore operations export several metrics using the expvars interface. These are available at the `/debug/vars` endpoint of Vtbackup's and VTTablet's http status pages. [More details can be found here](../../features/monitoring/#3-push-based-metrics-system).

## Backup and Restore metrics

Metrics related to backup and restore operations are available in both Vtbackup and VTTablet.

#### BackupBytes, BackupCount, BackupDurationNanoseconds

Depending on the Backup Engine and Backup Storage in-use, a backup may be a complex pipeline of operations, including but not limited to:

 * Reading files from disk.
 * Compressing files.
 * Uploading compressed files to cloud object storage.

These operations are counted and timed, and the number of bytes consumed or produced by each stage of the pipeline are counted as well.

Metrics related to backup operations are available in both Vtbackup and VTTablet.

#### BackupBytes, BackupCount, BackupDurationNanoseconds

Depending on the Backup Engine and Backup Storage in-use, a backup may be a complex pipeline of operations, including but not limited to:

 * Reading files from disk.
 * Compressing files.
 * Uploading compressed files to cloud object storage.

These operations are counted and timed, and the number of bytes consumed or produced by each stage of the pipeline are counted as well.

#### backup_duration_seconds

**Deprecated**

_backup_duration_seconds_ times the duration of a backup. This metric is deprecated and will be removed in a future release. Use _BackupDurationNanoseconds_ instead.

#### RestoreBytes, RestoreCount, RestoreDurationNanoseconds

Depending on the Backup Engine and Backup Storage in-use, a restore may be a complex pipeline of operations, including but not limited to:

 * Downloading compressed files from cloud object storage.
 * Decompressing files.
 * Writing decompressed files to disk.

These operations are counted and timed, and the number of bytes consumed or produced by each stage of the pipeline are counted as well.

Metrics related to restore operations are available in both Vtbackup and VTTablet.

#### RestoreBytes, RestoreCount, RestoreDurationNanoseconds

Depending on the Backup Engine and Backup Storage in-use, a restore may be a complex pipeline of operations, including but not limited to:

 * Downloading compressed files from cloud object storage.
 * Decompressing files.
 * Writing decompressed files to disk.

These operations are counted and timed, and the number of bytes consumed or produced by each stage of the pipeline are counted as well.

#### RestoredBackupTime, RestorePosition

_RestoredBackupTime_ captures the timestamp associated with the backup from which the current process was restored. _RestorePosition_ captures the GTID position associated with that backup.

#### Instrumented components and operations

| Component | Implementation | Operation | Metrics |
|-|-|-|-|
| BackupEngine | Builtin | Compressor:Close | BackupCount, BackupDurationNanoseconds  |
| BackupEngine | Builtin | Compressor:Open | BackupCount, BackupDurationNanoseconds |
| BackupEngine | Builtin | Compressor:Write | BackupBytes, BackupDurationNanoseconds |
| BackupEngine | Builtin | Decompressor:Read | RestoreBytes, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Decompressor:Close | RestoreCount, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Decompressor:Open | RestoreCount, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Destination:Close | BackupCount, BackupDurationNanoseconds, RestoreCount, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Destination:Open | BackupCount, BackupDurationNanoseconds, RestoreCount, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Destination:Write | BackupBytes, BackupDurationNanoseconds, RestoreBytes, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Source:Close | BackupCount, BackupDurationNanoseconds, RestoreCount, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Source:Open | BackupCount, BackupDurationNanoseconds, RestoreCount, RestoreDurationNanoseconds |
| BackupEngine | Builtin | Source:Read | BackupBytes, BackupDurationNanoseconds, RestoreBytes, RestoreDurationNanoseconds |
| BackupStorage | File | File:Read | RestoreBytes, RestoreDurationNanoseconds |
| BackupStorage | File | File:Write | BackupBytes, BackupDurationNanoseconds |
| BackupStorage | S3 | AWS:Request:Send | BackupCount, BackupDurationNanoseconds, RestoreCount, RestoreDurationNanoseconds |

## Vtbackup metrics

Vtbackup exports some metrics which are not available elsewhere.

#### DurationByPhaseSeconds

Deprecated. See next section.

#### Phase

_Phase_ a binary-valued gauge that reports the currently active phase.

#### PhaseStatus

Vtbackup emits status metrics for its phases of execution. `PhaseStatus` reports a 1 (active) or a 0 (inactive) for each of the following phases and statuses:


 * `CatchUpReplication` phase has statuses `Stalled` and `Stopped`.
   * `Stalled` is set to `1` when replication stops advancing.
   * `Stopped` is set to `1` when replication stops before `vtbackup` catches up with the primary.

<hr style="border-top: 2px dashed brown">

## Example

**A snippet of vtbackup metrics after running it against the local example after creating the initial cluster**

(Processed with `jq` for readability.)

```
{
  "BackupBytes": {
    "BackupEngine.Builtin.Source:Read": 4777,
    "BackupEngine.Builtin.Compressor:Write": 4616,
    "BackupEngine.Builtin.Destination:Write": 162,
    "BackupStorage.File.File:Write": 163
  },
  "BackupCount": {
    "-.-.Backup": 1,
    "BackupEngine.Builtin.Source:Open": 161,
    "BackupEngine.Builtin.Source:Close": 322,
    "BackupEngine.Builtin.Compressor:Close": 161,
    "BackupEngine.Builtin.Destination:Open": 161,
    "BackupEngine.Builtin.Destination:Close": 322
  },
  "BackupDurationNanoseconds": {
    "-.-.Backup": 4188508542,
    "BackupEngine.Builtin.Source:Open": 10649832,
    "BackupEngine.Builtin.Source:Read": 55901067,
    "BackupEngine.Builtin.Source:Close": 960826,
    "BackupEngine.Builtin.Compressor:Write": 278358826,
    "BackupEngine.Builtin.Compressor:Close": 79358372,
    "BackupEngine.Builtin.Destination:Open": 16456627,
    "BackupEngine.Builtin.Destination:Write": 11021043,
    "BackupEngine.Builtin.Destination:Close": 17144630,
    "BackupStorage.File.File:Write": 10743169
  },
  "DurationByPhaseSeconds": {
    "InitMySQLd": 2,
    "RestoreLastBackup": 6,
    "CatchUpReplication": 1,
    "TakeNewBackup": 4
  },
  "Phase": {
    "InitialBackup": 0,
    "RestoreLastBackup": 0,
    "CatchupReplication": 0,
    "TakeNewBackup": 0
  },
  "RestoreBytes": {
    "BackupEngine.Builtin.Source:Read": 1095,
    "BackupEngine.Builtin.Decompressor:Read": 950,
    "BackupEngine.Builtin.Destination:Write": 209,
    "BackupStorage.File.File:Read": 1113
  },
  "RestoreCount": {
    "-.-.Restore": 1,
    "BackupEngine.Builtin.Source:Open": 161,
    "BackupEngine.Builtin.Source:Close": 322,
    "BackupEngine.Builtin.Decompressor:Close": 161,
    "BackupEngine.Builtin.Destination:Open": 161,
    "BackupEngine.Builtin.Destination:Close": 322
  },
  "RestoreDurationNanoseconds": {
    "-.-.Restore": 6204765541,
    "BackupEngine.Builtin.Source:Open": 10542539,
    "BackupEngine.Builtin.Source:Read": 104658370,
    "BackupEngine.Builtin.Source:Close": 773038,
    "BackupEngine.Builtin.Decompressor:Read": 165692120,
    "BackupEngine.Builtin.Decompressor:Close": 51040,
    "BackupEngine.Builtin.Destination:Open": 22715122,
    "BackupEngine.Builtin.Destination:Write": 41679581,
    "BackupEngine.Builtin.Destination:Close": 26954624,
    "BackupStorage.File.File:Read": 102416075
  },
  "RestorePosition": "MySQL56/f00e54ca-0fbf-11ee-ad84-eddb850690bf:1-61",
  "RestoredBackupTime": "2023-06-21T00:39:00Z",
}
```

Some notes to help understand these metrics:

 * `BackupBytes["BackupStorage.File.File:Write"]` measures how many bytes were read from disk by the `file` Backup Storage implementation during the backup phase.
  * `Phase["CatchupReplication"]` reports whether the catch-up replication phase is active (1) or not (0).
  * `Phase["RestoreLastBackup"]` reports whether the restore last backup phase is active (1) or not (0).
  * `RestoreDurationNanoseconds["-.-.Restore"]` also measures to the duration of the restore phase.
