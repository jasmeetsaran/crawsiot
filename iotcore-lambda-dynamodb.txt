# Code
import boto3

def lambda_handler(event, context):
    client = boto3. client('dynamodb')
    response = client.put_item(
        TableName = 'mytable',
        Item = {
            'timestamp': {'S': str(event['timestamp'])},
            'deviceId': {'S': event['deviceId']},
            'temperature': {'N': str(event['temperature'])},
            'humidity': {'N': str(event['humidity'])},
        }
    )
    return 0




# Test template

{
  "timestamp": 1733936240,
  "deviceId": "team01",
  "temperature": 59,
  "humidity": 25
}
