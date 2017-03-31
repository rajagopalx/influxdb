# influxdb


`select sum(ram), sum(readops),sum(writeops),sum(diskread),sum(diskwrite) from windows where time > now() - 10m  GROUP BY "user","computer",time(1s) fill(none)`

`select sum(ram)as ram, sum(readops) as readops, sum(writeops) as writeaops, sum(diskread) as diskread,sum(diskwrite) as diskwrite from windows where time > now() - 30s  GROUP BY "user","computer",time(1s) fill(none)`

`CREATE CONTINUOUS QUERY "user_metrics_query" ON "telegraf" BEGIN SELECT sum(ram)as ram, sum(readops) as readops, sum(writeops) as writeaops, sum(diskread) as diskread,sum(diskwrite) as diskwrite INTO "users_metrics" FROM "windows" GROUP BY "user","computer",time(1s) fill(none) END`
