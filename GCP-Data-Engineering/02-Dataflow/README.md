# Dataflow

bkt-dataflow-ftr-0001

- Enbale Dataflow API
```

gcloud config set project   playground-s-11-31963abe

#Download dataflow example usin mvn command below
mvn archetype:generate \
      -DarchetypeGroupId=org.apache.beam \
      -DarchetypeArtifactId=beam-sdks-java-maven-archetypes-examples \
      -DarchetypeVersion=2.8.0 -DgroupId=org.example \
      -DartifactId=dataflow-lab -Dversion="0.1" \
      -Dpackage=org.apache.beam.examples -DinteractiveMode=false


export PROJECT_ID=playground-s-11-31963abe
export BUCKET_NAME=bkt-dataflow-ftr-0001

mvn -Pdataflow-runner compile exec:java \
      -Dexec.mainClass=org.apache.beam.examples.WordCount \
      -Dexec.args="--project=${PROJECT_ID} \
      --stagingLocation=gs://${BUCKET_NAME}/staging/ \
      --output=gs://${BUCKET_NAME}/output \
      --runner=DataflowRunner"
```

### Resources
https://beam.apache.org/documentation/programming-guide/

