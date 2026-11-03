# Nandi Personal Backup

The first of Nandi's personal packs: agents that look after your own things, on your own accounts.

| Agent         | What it does                                                                                                                               | Status  |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------- |
| Backup Keeper | Backs up the folders you choose to your own S3 bucket as Glacier Deep Archive, as they change and nightly; sets up the AWS side with you | Preview |

| Workflow          | What it does                                                                                          |
| ----------------- | ----------------------------------------------------------------------------------------------------- |
| Set up S3 backup  | From no AWS account to the first backup: sign-up page, sign-in, bucket, upload-only user, folders     |

Needs the **S3 Backup** connector (built into Nandi, Library › Tools) and the AWS CLI.

How it fits together:

1. The workflow (or a chat with Backup Keeper) creates a private bucket and an IAM user that can only upload to it, with your approval at each step. The user's key goes straight into an AWS profile on your computer.
2. You pick the folders in **Library › S3 Backup › Setup**. Saving creates a change trigger per folder (`s3-backup-<folder>`, at most one backup every 15 minutes) and a nightly backup (`s3-backup-nightly`, 2:00). You can pause or edit them in Automations.
3. Each backup is `aws s3 sync` to `s3://<bucket>/<folder>/` with `--storage-class DEEP_ARCHIVE`, without `--delete`.

Licence: MIT (see LICENSE). Copy, change and share these agents freely.
