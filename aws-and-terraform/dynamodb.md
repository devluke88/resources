# DynamoDB

## Local Development

<pre class="language-python"><code class="lang-python"># Source: https://dynobase.dev/run-dynamodb-locally/
# Create a file called docker-compose.yml and paste following code:
<strong># docker-compose.yml
</strong><strong>version: "3.5"
</strong>
services:
  dynamo:
    container_name: local-dynamodb
    image: amazon/dynamodb-local
    networks:
      - local-dynamodb
    ports:
      - "8000:8000"
    volumes:
      - dynamodata:/home/dynamodblocal
    working_dir: /home/dynamodblocal
    command: "-jar DynamoDBLocal.jar -sharedDb -dbPath ."

networks:
  local-dynamodb:
    name: local-dynamodb

volumes:
  dynamodata: {}

# Run docker-compose up -d. You can skip -d flag if you don't want to run in in the "detached" mode.
docker-compose up -d
</code></pre>

