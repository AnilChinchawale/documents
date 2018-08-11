# Atheios API

### Get balance for an address
Usage:
```
http://api.atheios.com/api/balance/{address}
or 
http://api.atheios.com/api/balance/{address}/raw
```

Example:
```console
$ curl -s -X GET http://api.atheios.com/api/balance/0x3e5c79bc6742ff23a884b8db576bd401b3e7ff59 | jq
{
  "balance": "8182.59412"
}

$ curl -s -X GET http://api.atheios.com/api/balance/0x3e5c79bc6742ff23a884b8db576bd401b3e7ff59/raw
8182.69412
```

### Get current block
Usage:
```
http://api.atheios.com/api/block
or
http://api.atheios.com/api/block/raw
```

Example:
```console
$ curl -s -X GET http://api.atheios.com/api/block | jq
{
  "block": "357917"
}

$ curl -s -X GET http://api.atheios.com/api/block/raw
357917
```

### Get current supply
Usage:
```
http://api.atheios.com/api/currentSupply
or 
http://api.atheios.com/api/currentSupply/raw
```

Example:
```console
$ curl -s -X GET http://api.atheios.com/api/currentSupply | jq
{
  "supply": "4390613.800000"
}

$ curl -s -X GET http://api.atheios.com/api/currentSupply/raw
4390613.800000
```
