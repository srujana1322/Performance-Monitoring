Script:
#!/bin/bash
# Collect system performance data mpstat >
/var/log/performance/mpstat.log iostat >
/var/log/performance/iostat.log vmstat >
/var/log/performance/vmstat.log

# Aggregate and summarize data performance_summary="/var/log/performance/summary.log" echo "Performance Summary" > $performance_summary echo "===================" >> $performance_summary echo "" >>
$performance_summary cat /var/log/performance/mpstat.log >>
$performance_summary cat /var/log/performance/iostat.log >>
$performance_summary cat /var/log/performance/vmstat.log >>
$performance_summary
# Notify administrator echo "Performance monitoring completed. Review summary at
/var/log/performance/summary.log" | mail -s "Performance
Monitoring Notification" admin@mycomp.com

This script collects various system performance metrics using tools like mpstat, iostat, and vmstat. It aggregates and summarizes the collected data into a single log file and notifies the system administrator to review the performance summary.
