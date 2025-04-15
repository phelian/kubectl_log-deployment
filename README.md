# kubectl_log-deployment

Kubectl plugin to logs multiple pods for same deployment

Example output:

```sh
kubectl log-deployment api --jq
Using jq to format logs
🔍 Fetching pods for deployment: api
🪵  Tailing logs from pod: api-cbb686b7d-5dk84
🪵  Tailing logs from pod: api-cbb686b7d-5vrwk
[api-cbb686b7d-5vrwk] {
[api-cbb686b7d-5vrwk]   "level": 30,
[api-cbb686b7d-5vrwk]   "time": 1744682273777,
[api-cbb686b7d-5vrwk]   "pid": 1,
[api-cbb686b7d-5vrwk]   "hostname": "api-cbb686b7d-5vrwk",
[api-cbb686b7d-5vrwk]   "reqId": "a22069c5-d7be-4c8d-b080-51b378dcc180",
[api-cbb686b7d-5vrwk]   "req": {
[api-cbb686b7d-5vrwk]     "method": "GET",
[api-cbb686b7d-5vrwk]     "url": "/api/public/healthcheck",
[api-cbb686b7d-5vrwk]     "host": "10.255.139.172:3001",
[api-cbb686b7d-5vrwk]     "remoteAddress": "10.255.128.178",
[api-cbb686b7d-5vrwk]     "remotePort": 36080
[api-cbb686b7d-5vrwk]   },
[api-cbb686b7d-5vrwk]   "msg": "incoming request"
[api-cbb686b7d-5vrwk] }
```

```sh
» kubectl log-deployment api
🔍 Fetching pods for deployment: api
🪵  Tailing logs from pod: api-cbb686b7d-5dk84
🪵  Tailing logs from pod: api-cbb686b7d-5vrwk
[api-cbb686b7d-5dk84] {"level":30,"time":1744682303788,"pid":1,"hostname":"api-cbb686b7d-5dk84","reqId":"5522cf0d-29b9-463b-9621-2b93fa8f92d6","req":{"method":"GET","url":"/api/public/healthcheck","host":"10.255.179.136:3001","remoteAddress":"10.255.128.178","remotePort":10210},"msg":"incoming request"}
[api-cbb686b7d-5vrwk] {"level":30,"time":1744682286207,"pid":1,"hostname":"api-cbb686b7d-5vrwk","reqId":"c1c9ea3b-bb86-42e5-8a22-a41d6903620e","res":{"statusCode":204},"responseTime":0.19321107864379883,"msg":"request completed"}
^C🛑 Stopping log tails...
```
