# log-cpu-usage-mac

This is a bash script for logging idle time, load average (1 minute), CPU usage, started processes, and top processes on my Macbook every minute using cron. (Top processes are logged to a separate file and only if the 1-minute load average is greater than 10.)

## Usage

1. Run the script (the log directory can optionally be specified as the first argument on the command line):

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
2024-06-14 15:05:00 0.00 3.98 11.69 13.61 74.69 [NONE]
2024-06-14 15:06:00 0.00 2.76 10.3 7.52 82.44 [NONE]
```

## Top processes log file

If the 1-minute load average is greater than 10, the top 5 processes will be logged to a file named `top-processes.log`.
