# learning-etcd-v3

Learning etcd (aka coreOS)  v3

## what is

Etcd is an alternative of zookeeper. 

One of its usage is a multiple-node data store in order to keep your cloud applications in multiple sites having the same configurations.

**In short, sync conf saftly among sites.**


## setup etcd as a ubuntu service

https://computingforgeeks.com/how-to-install-etcd-on-ubuntu-18-04-ubuntu-16-04/

## main concept/protocol of etcd cluster - raft

https://speakerdeck.com/benbjohnson/raft-the-understandable-distributed-consensus-protocol/

## tutorial of etcd v3 API or commands

**Suggested reading**

Most commands except auth, in Chinese - https://www.jianshu.com/p/36429db7f398

Basic auth, in Chinese - https://cloud.tencent.com/developer/article/1380947

Backup and restore, in Chinese - https://cloud.tencent.com/info/7e40936e15a2ec21379855ab3a3e9eb2.html

Commands, in English - https://coreos.com/etcd/docs/latest/dev-guide/interacting_v3.html

User scenarios, in Chinese - https://www.cnblogs.com/softidea/p/6517959.html


**Officail Documents**

https://github.com/etcd-io/etcd/tree/master/Documentation

## Difference between v2 and v3

NOTE: v2 data store is isolated with v3 data store even in the same etcd instance. Read this to understand the difference. **In short, just use v3 API**

https://coreos.com/etcd/docs/latest/op-guide/v2-migration.html

https://www.compose.com/articles/etcd2to3-new-apis-and-new-possibilities/

## etcd API v3 SDK in nodejs

etcd3 - https://github.com/mixer/etcd3

etcd3 examples - https://github.com/mixer/etcd3/tree/master/test


## misc: commands

```bash

ETCDCTL_API=3 etcdctl get "/" --from-key --keys-only=false -w fields | grep -i "value\|key"     # show all keys and values start with '/'

ETCDCTL_API=3 etcdctl put "/v1/conf/mcs50/conf-dev-simulator-and-etc/csv/protocol2/电 - 包.csv" "base64(电 - 包.csv)"     # create key value pair

ETCDCTL_API=3 etcdctl snapshot save ./conf_db.etcd      # save etcd's snapshot to a file, and ignore change history

```

