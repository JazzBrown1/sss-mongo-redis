# Super Scaled Sockets - The Mongo Redis Super Scaler

### What is Super Scaled Sockets?

This is the Mongo Redis Scaler for the Super Scaled Sockets Library.

### Prerequisites

A mongoDb database and credentials

A redis instance and credentials

MongoDB Atlas: [https://www.mongodb.com](https://www.mongodb.com)

RedisLabs: [https://redislabs.com/](https://redislabs.com/)

### Installation

On nmp run the following command:
~~~~
npm install sss-mongo-redis
~~~~

#### Usage

~~~
// mongo connection info all properties are required

const sss = require('super-scaled-sockets');
const mongoRedis = require('sss-mongo-redis');

const mongoConnection = {
  uri: 'mongodb+srv://smartUsername:smartPassword@cluster0-abcd.zyx.mongodb.net/test?retryWrites=true',
  dbName: 'redis',
  collectionName: 'redis'
};

// redis connection Info all properties are required
const redisConnection = {
  password: 'ABCDefGH1234567890ZYXWvu',
  host: 'redis-123456.z9.us-east-1-0.ec2.cloud.redislabs.com',
  port: 123456
};

mongoRedis.connect(mongoConnection, redisConnection, (err, scaler) => {
  if (err) {
    console.log('Error establishing scaler connection');
    return;
  }
  sss.connect(scaler, {}, (error) => {
  // ......
~~~

For details about setting up the rest of Super Scaled Sockets please see the [Super Scaled Sockets Page](https://github.com/JazzBrown1/super-scaled-sockets).