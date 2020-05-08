# vettom.github.io ![alt text](https://vettom.github.io/images/dv-tec-logo-round2cm.png "Denny Vettom  Tech Logo")

### My Public Repos 
| My Repos   | Description |
| ------------ | ------------ |
| [Kubernetes](https://github.com/vettom/Kubernetes) |  Kubernetes exam tips and sample files that works. |
| [AWS-Boto3](https://github.com/vettom/Aws-Boto3) | Python scripts using AWS Boto3. Also advanced with a text based CMDB |
| [Python Basics](https://github.com/vettom/PythonBasics) | Sample python script and functions for beginners |
| [Scripts](https://github.com/vettom/Scripts) | Few shell scripts working with AWS CLI |
| [Aces WheelchairBasketball](https://vettom.github.io/aces/)| Wheelchair Basktball moves demonstrated with Adobe After Effect Animation  |

- [Kubernetes](https://github.com/vettom/Kubernetes) Kubernetes exam tips and sample files that works.
- [AWS-Boto3](https://github.com/vettom/Aws-Boto3) Python scripts using AWS Boto3. Also advanced with a text based CMDB
- [Python Basics](https://github.com/vettom/PythonBasics)  :Sample python script and functions for beginners
- [Scripts](https://github.com/vettom/Scripts)  : Few shell scripts working with AWS CLI
- [Aces](https://vettom.github.io/aces/) : Wheelchair Basktball moves demonstrated with Adobe After Effect Animation

# Development Principle
![alt text](https://vettom.github.io/images/dvethos.jpg "Denny Vettom Development ethos ")

### Scripts 
 > Requires: Python 3.x, Boto3, AWS Cli Config files
- [dnsctl.py](https://github.com/vettom/Aws-Boto3#dnsupdatepy)               : Add/remove/update DNS record
- [ec2instance.py](https://github.com/vettom/Aws-Boto3#ec2instancepy)             : Generic Manage Ec2 instance stop/start
- [elbctl.py](https://github.com/vettom/Aws-Boto3#elbctlpy)             : Mange Classig ELB
- [albctl.py](https://github.com/vettom/Aws-Boto3#albctlpy-elb-v2)      : Manage ALB list/status/attach/detach


## dnsctl.py
    Script can create DNS A record or Alias record on Route 53. If there is requirement to create multiple aliases to single domain, you can provide it as space separated arguments or list domains in a file.
    - Set your Default Zone ID in script or provide as -z argument.
  
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

## ec2instance.py 
Manage EC2 instance list/start/stop/restart/status

```
ec2instance.py -h
usage: ec2instance.py [-h] [--profile PROFILE] [--region REGION]
                      [--instance INSTANCE]
                      {list,start,stop,restart,status}

Perform common instance tasks

positional arguments:
  {list,start,stop,restart,status}
                        Instance action to be performed
                        list/start/stop/restart/status

optional arguments:
  -h, --help            show this help message and exit
  --profile PROFILE     If no profile provided, assumes default
  --region REGION       Default is eu-west-1, or provide as argument
  --instance INSTANCE   Name of Aws instance
  ```
## elbctl.py
Manage ELB activity like list elb, status of elb, atach/detach instances
- Script can accept multiple ELB and instances at same time. If multiple elb, same action will be performed on each elb.

```
elbctl.py -h
usage: elbctl.py [-h] [-p PROFILE] [-r REGION] [--elb ELB [ELB ...]]
                 [--vpc VPC [VPC ...]] [-i INSTANCES [INSTANCES ...]]
                 {list,status,attach,detach}

ELB Operations tasks

positional arguments:
  {list,status,attach,detach}
                        list/status/attach/detach

optional arguments:
  -h, --help            show this help message and exit
  -p PROFILE, --profile PROFILE
                        If no profile provided, assumes default
  -r REGION, --region REGION
                        Default is eu-west-1, or provide as argument
  --elb ELB [ELB ...]   Name/s of Aws ELB
  --vpc VPC [VPC ...]   Name/s of Aws VPC
  -i INSTANCES [INSTANCES ...], --instances INSTANCES [INSTANCES ...]
                        Instance ID/s
```