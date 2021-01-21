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
4. [Django minio backend](https://pypi.org/project/django-minio-backend/)
5. [Django minio](https://pypi.org/project/django-minio/)
6. [Django minio storage](https://django-minio-storage.readthedocs.io/en/latest/)
7. [Minio storage define - github](https://github.com/py-pa/django-minio-storage/blob/master/minio_storage/storage.py)
8. [Django filer settings](https://django-filer.readthedocs.io/en/latest/settings.html)
9. [Django filer settings - github](https://github.com/django-cms/django-filer/blob/master/filer/settings.py)
10. [Django filer storage - github](https://github.com/django-cms/django-filer/blob/master/filer/storage.py)
