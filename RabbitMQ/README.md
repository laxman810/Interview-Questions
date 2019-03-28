# RabbitMQ Interview Questions


Installing on Ubuntu
========================
apt-get    update 
apt-get -y upgrade
echo "deb http://www.rabbitmq.com/debian/ testing main" >> /etc/apt/sources.list
curl http://www.rabbitmq.com/rabbitmq-signing-key-public.asc | sudo apt-key add -
apt-get update
sudo apt-get install rabbitmq-server
sudo nano /etc/default/rabbitmq-server (Uncomment the limit line)


enable RabbitMQ Management Console
==================================
sudo rabbitmq-plugins enable rabbitmq_management


RabbitMq Permission Problem
==============================
rabbitmqctl add_user laxman laxman
rabbitmqctl set_user_tags laxman administrator
rabbitmqctl set_permissions -p / laxman ".*" ".*" ".*"

Managing on Ubuntu
====================
service rabbitmq-server start
service rabbitmq-server stop
service rabbitmq-server restart
service rabbitmq-server status

NODE.JS RabbitMq Example
========================
'use strict'
const amqp = require('amqplib/callback_api');
var url = "amqp://test:test@localhost:5672";
amqp.connect(url + "?heartbeat=60", (err, conn) => {
    if (err) {
        console.log("[AMQP]", err.message);
    }
    conn.on("error", (err) => {
        if (err.message !== "Connection closing") {
            console.error("[AMQP] conn error", err.message);
        }
    });
    conn.on("close", () => {
        console.log("[AMQP] reconnecting");
    });
    console.log("[AMQP] connected --------------------- ");
});


RabbitMQ advantages:
===================
*Fast
Polyglot
Simple management
No Erlang knowledge needed
Great documentation and community

RabbitMQ with Docker:
=====================
docker run -d --hostname my-rabbit --name some-rabbit -e RABBITMQ_DEFAULT_USER=user -e RABBITMQ_DEFAULT_PASS=password -p 8080:15672 rabbitmq:3-management
docker run -d --hostname my-rabbit --name some-rabbit -p 8080:15672 rabbitmq:3-management

Code  from : 
https://github.com/rabbitmq/rabbitmq-tutorials/tree/master/javascript-nodejs


installed from : 
https://www.digitalocean.com/community/tutorials/how-to-install-and-manage-rabbitmq


Running on :
http://iserve.ind.in:15672/#/


solved  login not working :
https://stackoverflow.com/questions/23669780/rabbitmq-3-3-1-can-not-login-with-guest-guest