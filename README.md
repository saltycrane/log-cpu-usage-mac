# log-cpu-usage-mac

This is a bash script for logging idle time, load average, CPU usage, started processes, and stopped processes on my Macbook every minute using cron.

## Usage

1. Run the script:

``` sh
./log-cpu-usage /tmp/my-cpu-usage.log
./log-cpu-usage /tmp/my-cpu-usage.log
./log-cpu-usage /tmp/my-cpu-usage.log
```

2. See the output:

``` sh
cat /tmp/my-cpu-usage.log
```

```
Date Time IdleTimeHrs LoadAvg1 LoadAvg5 LoadAvg15 CpuUser CpuSys CpuIdle StartedProcesses StoppedProcesses
2024-06-14 10:56:49 0.00 2.31 2.66 3.06 10.67 9.48 79.84 [NONE] [NONE]
2024-06-14 10:56:52 0.00 2.44 2.69 3.06 10.43 9.89 79.67 [NONE] [NONE]
2024-06-14 10:56:54 0.00 2.44 2.69 3.06 15.86 9.72 74.41 [NONE] [NONE]
```

## Usage with cron

1. Open the crontab editor:

``` sh
crontab -e
```

2. Add the following line to schedule the script to run every minute:

```
* * * * * /path/to/my/log-cpu-usage-mac-repo/log-cpu-usage /tmp/my-cpu-usage.log
```

3. See the output:

``` sh
cat /tmp/my-cpu-usage.log
```

```
Date Time IdleTimeHrs LoadAvg1 LoadAvg5 LoadAvg15 CpuUser CpuSys CpuIdle StartedProcesses StoppedProcesses
2024-06-14 11:00:00 0.00 10.02 4.63 3.71 20.24 12.37 67.37 [NONE] [NONE]
2024-06-14 11:01:00 0.00 6.63 4.75 3.83 21.66 15.48 62.85 [NONE] [NONE]
2024-06-14 11:02:01 0.01 4.99 4.65 3.85 14.30 13.78 71.90 [NONE] [NONE]
2024-06-14 11:03:00 0.02 4.28 4.50 3.84 13.43 13.6 73.50 [NONE] [NONE]
2024-06-14 11:04:00 0.01 3.14 4.12 3.75 12.57 12.36 75.5 [NONE] [NONE]
```
