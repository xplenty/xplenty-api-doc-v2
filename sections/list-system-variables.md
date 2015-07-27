## List System Variables

### Description
List public system variables

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/variables" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "_MAX_COMBINED_SPLIT_SIZE": 67108864,
  "_BYTES_PER_REDUCER": 209715200,
  "_LINE_RECORD_READER_MAX_LENGTH": 1048576,
  "_DEFAULT_TIMEZONE": "'+00:00'",
  "_DEFAULT_PARALLELISM": 0,
  "_SHUFFLE_INPUT_BUFFER_PERCENT": 0.7,
  "_COPY_PARALLELISM": "(int)$_CLUSTER_NODES_COUNT * 3",
  "_COPY_TARGET_PARTITIONS": "100",
  "_COPY_TARGET_SIZE": "64",
  "_PARQUET_COMPRESSION": "'UNCOMPRESSED'",
  "_PARQUET_PAGE_SIZE": "1 * 1024 * 1024",
  "_PARQUET_BLOCK_SIZE": "128 * 1024 * 1024"
}
```
