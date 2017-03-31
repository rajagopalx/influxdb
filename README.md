# influxdb


`select sum(ram), sum(readops),sum(writeops),sum(diskread),sum(diskwrite) from windows where time > now() - 10m  GROUP BY "user","computer",time(1s) fill(none)`
