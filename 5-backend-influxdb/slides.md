%title: NETDATA
%author: xavki


# Netdata : Backend InfluxDB

<br>
Blog : https://computingforgeeks.com/monitor-linux-server-with-netdata-and-grafana/

<br>
* installation :

```
echo "deb https://repos.influxdata.com/ubuntu bionic stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
sudo curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -
sudo apt-get update
sudo apt-get install -y influxdb
systemctl enable influxdb
```

------------------------------------------------------------------------------------

# Configurations : influxdb et netdata


<br>
* configuration influxdb /etc/influxdb/influxdb.conf

```
[[opentsdb]]
  enabled = true
  bind-address = ":4242"
  database = "opentsdb"
```

<br>

```
[backend]
        host tags = hoststats
        enabled = yes
        data source = average
        type = opentsdb
        destination = tcp:192.168.60.3:4242
        prefix = netdata
```

<br>

* template : https://raw.githubusercontent.com/kmonsoor/netdata-influx-grafana/master/grafana-dashboard.json
