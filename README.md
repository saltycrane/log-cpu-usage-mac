# log-cpu-usage-mac

This is a bash script for logging the CPU usage on my Macbook every minute using cron.

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
Date Time LoadAvg1 LoadAvg5 LoadAvg15 CpuUser CpuSys CpuIdle
2024-06-13 17:02:48 2.53 5.08 5.28 9.67 9.67 80.64
2024-06-13 17:02:52 2.53 5.08 5.28 10.26 10.40 79.33
2024-06-13 17:02:54 2.41 5.01 5.26 10.10 10.48 79.40
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
Date Time LoadAvg1 LoadAvg5 LoadAvg15 CpuUser CpuSys CpuIdle
2024-06-13 17:05:00 2.20 3.99 4.81 9.82 8.34 81.82
2024-06-13 17:06:00 1.94 3.60 4.60 8.80 7.42 83.76
2024-06-13 17:07:00 2.22 3.35 4.44 8.91 7.51 83.56
2024-06-13 17:08:00 1.94 3.06 4.26 11.15 8.49 80.35
2024-06-13 17:09:00 1.84 2.83 4.09 9.11 7.64 83.24
```
