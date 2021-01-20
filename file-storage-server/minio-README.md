### Permissions for Minio 
If port for minio is being used or any other minio instance is used 
```
sudo pgrep minio
```
kill that process like this 
```
sudo pkill -9 minio
```
If Minio persistant ./data file has no background write permission 
```
sudo chown -R mobasshir /data && sudo chmod u+rxw /data
```

## Resources
1. [Try MinIO – Self-Hosted S3-Compliant High Performance Object Storage](https://geekflare.com/minio-object-storage/)
2. [MinIO Python SDK for Amazon S3 Compatible Cloud Storage](https://docs.min.io/docs/python-client-quickstart-guide)
3. [Python Client API Reference](https://docs.min.io/docs/python-client-api-reference)
