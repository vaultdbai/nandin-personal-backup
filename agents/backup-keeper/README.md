# Backup Keeper

Keeps the folders you choose backed up in your own Amazon S3 bucket, as Glacier Deep Archive: the cheapest storage AWS has (about $1 per TB a month).

- **Backs up as things change.** Each folder you assign gets a change trigger (at most one backup every 15 minutes while it keeps changing), plus a backup of everything every night at 2:00.
- **Never deletes.** Removing a file on your computer doesn't remove its backup.
- **Sets up AWS with you.** If you have no AWS account, it can open the sign-up page. With your approval it creates a private bucket and an IAM user that can only upload to it, and saves that user's key on your computer. The agent never sees the key.

Needs: the AWS CLI on this computer, and the **S3 Backup** connector (Library › Tools).

Start with the **Set up S3 backup** workflow (Automations), or just tell Backup Keeper "set up my backup".

Restores take hours and cost a little per GB: this is insurance for when a disk dies, not a sync folder.
