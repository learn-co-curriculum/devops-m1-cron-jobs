# Cron Jobs

## Learning goals

- Learn what cron jobs are and what they are used for
- Learn how to create, delete, and modify cron jobs

## Introduction

You probably won't find it surprising to hear that it's very common to create recurring tasks on server computers (or computers in general). Anything from executing scripts, backing up data, performing maintenance, interacting with/updating running programs, etc. can be set to a schedule that gets automatically processed. These are known as *cron jobs*.

## Cron Jobs

A **cron job** runs on a time-based schedule, and can be configured to run at any time, every week, month, or year.

The schedule is defined using a syntax that specifies the time interval followed by the command, as follows:

```bash
<minute> <hour> <day of the month> <month of the year> <day of the week> <command to be executed>
```

You can substitute any of the time parameters with an asterisk (`*`) when you wish to omit it. For example, to make a cron job that runs a script every day at 5:30 AM, you could use the following configuration:

```bash
30 5 * * * /home/john/scripts/script.sh
```

## `crontab`

The `crontab` command is available to manage cron jobs, and can do everything from adding/removing and listing existing jobs.

To list all the cron jobs for the current user, you can use the `-l` argument:

```bash
$ crontab -l
0 3 * * * /usr/cron/backup-script.sh
*/10 * * * * /usr/cron/monitoring-script.sh
```

To edit the cron jobs for the current user, you can use the `-e` argument. This will open up the cron file in the default editor (either `vi(m)` or `nano`), from which you can add/remove jobs (one per line):

```bash
$ crontab -e
```

Lastly, to remove the cron file altogether and delete all current cron jobs for the user, you can use the `-r` command:

```bash
$ crontab -r
```

## Conclusion

Cron jobs are a powerful tool for automating tasks in a *Linux* system; they can be used for a wide array of applications, ranging from periodic backups and maintenance to more complex interactions. As a server administrator, it's crucial to know where the jobs are located, as well as how to modify and maintain them.
