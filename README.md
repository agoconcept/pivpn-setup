# pivpn-setup

## Manage clients

```
pivpn add
pivpn list
pivpn clients
pivpn qrcode
```


## Troubleshooting issues

```
pivpn debug
```


## Backup configuration

To restore the backup, follow instructions at:
[https://docs.pivpn.io/openvpn/wireguard/#migrating-pivpn-wireguard]


## Update pivpn

```
pivpn update
```


# Throttling

## Limit bandwidth to 50 Mbps

```
sudo tc qdisc add dev wg0 parent root handle 1: hfsc default 1
sudo tc class add dev wg0 parent 1: classid 1:1 hfsc sc rate 50mbit ul rate 50mbit
```

or use `replace` instead of `add` if the class is already created


## View configured classes

```
tc class show dev wg0
```

