---
title: Ceph Mon Health
weight: 40
indent: false
---
# Ceph Mon Health
It is important to keep the Ceph Mons healthy. Healthy mons are having a quorum and at least a "backup" mon to still have quorum on failure of a mon.

## Quorum Calculation
The following equation calculates how many mons need to be healthy and in the quorum for the quorum to have formed:
```
x = round_up(MON_COUNT / 2)
```

This equation calculates how many mons you can lose before the quorum is lost:
```
x = round_up(MON_COUNT / 2)
```

## Mon Status
To get the current mon status you can run the following command in the toolbox:
```shell
$ ceph mon stat
e10: 3 mons at {rook-ceph-mon0=10.0.0.1:6790/0,rook-ceph-mon1=10.0.0.2:6790/0,rook-ceph-mon2=10.0.0.3:6789/0}, election epoch 3, leader 0 rook-ceph-mon0, quorum 0,1,2 rook-ceph-mon0,rook-ceph-mon1,rook-ceph-mon2
```
