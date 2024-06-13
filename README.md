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
Date Time User Sys Idle
2024-06-13 16:17:47 11.42 9.96 78.61
2024-06-13 16:17:52 10.55 10.94 78.50
2024-06-13 16:18:06 9.60 9.73 80.66
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
Date Time User Sys Idle
2024-06-13 16:21:00 8.57 7.77 83.65
2024-06-13 16:22:01 8.25 7.36 84.38
2024-06-13 16:23:01 8.51 7.56 83.91
```
