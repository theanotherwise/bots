# bots

```bash
for i in `seq 1 50` ; do
  nohup watch -n 0 curl --connect-timeout 1 --max-time 1 "http://127.0.0.1:8080" -o /dev/null --silent > 2>&1 /dev/null & 
done
```

### `kill`
```bash
for i in `seq 1 100` ; do
  nohup bash -c 'for i in `seq 1 1000` ; do VAR=`date +"%H%M%S%d%m%Y%N"` && touch $VAR && dd if=/dev/urandom of=$VAR bs=1KB count=`echo $RANDOM % 100 + 1 | bc` > /dev/null 2>&1 ; done' > /dev/null 2>&1 &
done
```

```bash
for i in `seq 1 254` ; do 
  ADDR=155.133.21.$i
  ping $ADDR -c 1 -W 1 && echo $ADDR >> found || echo $ADDR >> not_found
done
```

```bash
for i in `docker ps -a | grep -i httpd | awk '{print $1}'` ; do 
  curl  $(docker inspect $i | grep -Po "IPAddress\": \"\K[0-9\.]*")
done
```
