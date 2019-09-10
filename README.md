# vettom.github.io

### Scripts 
- [dnsctl.py](https://github.com/vettom/Aws-Boto3#dnsupdatepy)               : Add/remove/update DNS record
- [ec2instance.py](https://github.com/vettom/Aws-Boto3#ec2instancepy)             : Manage Ec2 instance stop/start
- [elbctl.py](https://github.com/vettom/Aws-Boto3#elbctlpy)             : Mange Classig ELB


## DNSCTL

```
dnsctl.py -h
usage: dnsctl.py [-h] (-s SRC_URL [SRC_URL ...] | -f SRC_FILE)
                 [-d DESTINATION] [-z ZONEID] [--destzoneid DESTZONEID]
                 [--health_check {True,False}]
                 {add,update,delete}

Manage routine DNS tasks.

positional arguments:
  {add,update,delete}   Choose task toperform

optional arguments:
  -h, --help            show this help message and exit
  -s SRC_URL [SRC_URL ...], --src_url SRC_URL [SRC_URL ...]
                        Alias/Domain name to be created separated by space
  -f SRC_FILE, --src_file SRC_FILE
                        File containing Alias list, one per line
  -d DESTINATION, --destination DESTINATION
                        Destination CNAME or IP
  -z ZONEID, --zoneid ZONEID
                        Zone ID, defaults to adobecqms ID
  --destzoneid DESTZONEID
                        Destination Zone ID for ELB only or if different
                        zoneid
  --health_check {True,False}
                        Evaluate health check, Default=False
```