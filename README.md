# Hive metastore

Run hive metasotre on [staroid](https://staroid.com).

 - Based on Hive 3.1.2
 - Postgresql DB configured on Persistent volume

## Use

Hive metastore is usually being used by other projects, such as Spark.

It exports [hive-metastore-info](https://github.com/open-datastudio/hive-metastore/blob/master/k8s-hive.yaml) ConfigMap that includes its Namespace and Service to the thrift endpoint. So other projects can import those information and make connection to the thrift endpoint.

Other project can import this ConfigMap and use Namespace and Service to connect to the thrift endpoint.

See [dependency](https://docs.staroid.com/project/dependency.html#dependency) to learn more about how to import/export ConfigMap, Secrets between different projects.


## Development

To run locally on minikube, use `minikube` profile.

```
skaffold dev --port-forward -p minikube
```
