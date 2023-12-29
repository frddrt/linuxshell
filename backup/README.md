# Backup
This makes an incremental copy of the directories, according to the config.txt file.

## Install backup script
```shell
mkdir /opt/backup
```
Copy files to /opt/backup directory, change config.txt as needed, and schedule crontab this way
```crontab
0 * * * * /opt/backup/backup
```

## config.txt
A TXT file with the configuration to run the copies. Each line will be evaluated for execution. Fields must be separated by pipe.

```TXT
T|SOURCE|DESTINATION|FREQUENCY (HOURS)|RETENTION (DAYS)
A|/media/Files/|/backup/files|12|30
I|/media/Images/|/backup/images|24|10
```
### Fields
- **T** => (A) for active and (I) for inactive.
- **SOURCE** => Mount point or source directory for the files.
- **DESTINATION** => Mount point or destination directory for the files.
- **FREQUENCY (HOURS)** => Frequency, in hours, that the copy will be executed.
- **RETENTION (DAYS)** => Number of days the copy will be kept.
