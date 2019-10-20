%title: NETDATA
%author: xavki


# Installation

<br>
Plusieurs type : 

* dépot git : https://github.com/netdata/netdata

* oneline :

```
bash <(curl -Ss https://my-netdata.io/kickstart.sh)
```

* docker : 

```
docker run -d --name=netdata \
  -p 19998:19999 \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```


-----------------------------------------------------------------

# Désinstallation

* si besoin

```
/usr/libexec/netdata/netdata-uninstaller.sh --yes -f
```
