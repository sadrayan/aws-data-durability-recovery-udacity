## Recovery Time Objective (RTO) and Recovery Point Objective (RPO) 

1- Minimum RTO for a single AZ outage

| Time  | Description                                                |
| ----- | ---------------------------------------------------------- |
| 00:01 | Problem happens (First minute)                             |
| 00:02 | Enhanced monitoring alert triggers (60 seconds)            |
| 00:03 | Automatically switch to second availability zone (1 mins)  |

**Total time ±3 mins**

2- Minimum RTO for a single region outage

| Time  | Description                                                                                 |
| ----- | ------------------------------------------------------------------------------------------- |
| 00:01 | Problem happens (First minute)                                                              |
| 00:02 | Enhanced monitoring alert triggers (60 seconds)                                             |
| 00:05 | Alert triggers on-all staff (2 mins)                                                        |
| 00:25 | On-call staff, log in, log onto VPN (20 mins)                                               |
| 00:35 | On-call staff starts diagnosing the issue (10 mins)                                         |
| 00:45 | Root cause is discovered (10 mins)                                                          |
| 00:50 | Read reblica promote started (5 mins)                                                       |
| 01:00 | Issue fixed (10 mins)                                                                       |

**Total time ±60 mins**

3- Minimum RPO for a single AZ outage

RDS point in time restore can be set to 5 minutes. With this configuration, most data lost of system would be about 5 minutes.

4- Minimum RPO for a single region outage

Read replicas keep the updates from the primary DB, which ensures read replica RPO to be similar to primary DB. The Prod cirical senario can consider RPO of ±10 mins.

