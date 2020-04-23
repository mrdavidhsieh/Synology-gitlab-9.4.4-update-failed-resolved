# Synology-gitlab-9.4.4-update-failed-resolved
Main problem is that the gitlab 9.4.4 installed through Synology can't update.

During the update Synology will ask if migrating the DB from MySQL to Postgresql but it will keep failing.

After the checking, I find out that the failure is caused by the db_converter.py file in Synology update package.

The dump from MySQL is fine but the sql file converted by the db_converter.py will have error.

In my case, I have wrong symbol jsut look like "current_timestamp( ,".
Hence, I resolve the problem by adding some code in db_converter.py and I don't change or delete the origin code in this py file.

Be free to download the spk file and test if it helps to update the gitlab.
After update to the 11.0.4-0053 using my spk, you can continue update the gitlab to the latest version through Synology package center.

During the update of using my spk, you will confront that Synology tell you that the package is broken, just confirm and continue the installation.

Notice!!! Please backup the gitlab first before any operation. I'm not responsible for any loss.
This spk file is almost same as spk file you can download from Synology only db_converter.py is different.
The original package that I used to modify is Docker-GitLab-AllinOne-x64-11.0.4-0053

You can download the two files here: https://drive.google.com/drive/folders/1-bT5Sbnq3uOFU9JGivVsAiB8rwCmRpeK?usp=sharing
