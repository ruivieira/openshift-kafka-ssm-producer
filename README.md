# openshift-kafka-ssm-producer

## Launching on OpenShift

```
oc new-app --template oshinko-java-spark-build-dc \
  -p APPLICATION_NAME=kafka-ssm-producer \
  -p GIT_URI=https://github.com/ruivieira/openshift-kafka-ssm-producer \
  -p APP_MAIN_CLASS=org.ruivieira.openshift.kafka.ssm.producer.App \
  -p SPARK_OPTIONS='--packages org.apache.spark:spark-streaming-kafka-0-10_2.11:2.2.0 --conf spark.jars.ivy=/tmp/.ivy2' \
  -e KAFKA_BROKERS=kafka:9092 \
  -e KAFKA_TOPIC=sometopic
```
