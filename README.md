# log-cpu-usage-mac

This is a bash script for logging idle time, load average (1 minute), CPU usage, started processes, and top processes on my Macbook 4 times every minute using cron. (Top processes are logged to a separate file and only if the 1-minute load average is greater than 10.)

## Usage

1. Run the script (it takes about 1 minute to run) (the log directory can optionally be specified as the first argument on the command line):

``` sh
./log-cpu-usage
```

2. See the output:

``` sh
cat ./cpu-usage.log
```

```
Date Time IdleTimeHrs LoadAvg1 CpuUser CpuSys CpuIdle StartedProcesses
2024-06-14 15:04:26 0.00 3.49 11.34 14.8 74.57 [NONE]
2024-06-14 15:04:37 0.00 3.58 28.25 20.26 51.48 [NONE]
2024-06-14 15:04:49 0.01 3.41 9.69 9.33 80.97 cleanup,local
2024-06-14 15:05:01 0.01 3.98 10.54 13.59 75.85 /usr/sbin/sendmail
```

## Usage with cron

1. Open the crontab editor:

``` sh
crontab -e
```

2. Add the following line to schedule the script to run every minute (specify the log directory as the first argument on the command line):

```
* * * * * /path/to/my/log-cpu-usage-mac-repo/log-cpu-usage /tmp
```

3. See the output:

``` sh
cat /tmp/cpu-usage.log
```

```
Date Time IdleTimeHrs LoadAvg1 CpuUser CpuSys CpuIdle StartedProcesses
2024-06-14 15:05:00 0.01 3.98 11.69 13.61 74.69 cleanup,local
2024-06-14 15:05:13 0.01 3.67 9.22 7.44 83.32 [NONE]
2024-06-14 15:05:25 0.02 3.45 13.70 10.39 75.90 [NONE]
2024-06-14 15:05:37 0.00 3.31 16.68 10.67 72.64 [NONE]
2024-06-14 15:06:00 0.00 2.76 10.3 7.52 82.44 cleanup,local
2024-06-14 15:06:12 0.00 2.56 9.32 7.12 83.55 [NONE]
2024-06-14 15:06:25 0.00 2.37 9.70 7.44 82.84 [NONE]
2024-06-14 15:06:37 0.00 2.32 26.63 13.82 59.54 [NONE]
```

## Top processes log file

If the 1-minute load average is greater than 10, the top 5 processes will be logged to a file named `top-processes.log`.
