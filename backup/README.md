# Backup
This script creates an incremental copy of the directories based on the configuration specified in the config.txt file.

## Install backup script
```shell
mkdir /opt/backup
```
Copy files to the /opt/backup directory, modify the config.txt as needed, and schedule the crontab as follows:
```crontab
0 * * * * /opt/backup/backup
```

## config.txt
A TXT file containing the configuration to execute the copies. Each line will be evaluated for execution, and fields must be separated by a pipe.

```TXT
T|SOURCE|DESTINATION|FREQUENCY (HOURS)|RETENTION (DAYS)
A|/media/Files/|/backup/files|12|30
I|/media/Images/|/backup/images|24|10
```
### Fields
- **T** => (A) for active and (I) for inactive.
- **SOURCE** => Mount point or source directory for the files.
- **DESTINATION** => Mount point or destination directory for the files.
- **FREQUENCY (HOURS)** => Frequency, in hours, at which the copy will be executed.
- **RETENTION (DAYS)** => Number of days the copy will be retained.
