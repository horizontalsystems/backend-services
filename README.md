# Docker images for Backend-services

Set of docker images and docker-compose build files for blockchain services.


## Blockchain-services

Docker images for fee services. Composed from 3 containers (nginx , btc-node, ltc-node).
Nginx container redirects (proxy) requests to nodes Fee RPC enpoints.

**/fee/avg**  request simply proxied to nodes that call below RPC method:
```json
{
  "id": "0",
  "method":"estimatesmartfee",
  "params": [12]
}
```
**Result**
```json
{
    "result": {
        "feerate": 0.00003013,
        "blocks": 3
    },
    "error": null,
    "id": "0"
}
```

Available requests:

| URI       | Description |
| --------- | -------- |
| /fee/low  | Get low fee (blocks: 40) |
| /fee/avg  | Get average fee (blocks: 12) |
| /fee/high | Get high fee (blocks: 3) |


Installation :
```bash
docker-compose up -d
```
## Btc-node

Bitcoin API based on BCOIN

Installation :
```bash
docker-compose up -d
```
## Dash-node

Insight api and block-explorer for Dash. Composed from 2 containers (Dash-node, dashcore-node with insight-api and UI)

Installation :
```bash
docker-compose up -d
```
## Ltc-node

Litcoin API based on LCOIN

Installation :
```bash
docker-compose up -d
```
