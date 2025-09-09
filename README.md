# RabbitMQ Order Demo 

This is a **minimal demo project** to understand how RabbitMQ works in a production-like setup.  
It contains two small services:

- **Order API (Producer)** → Exposes an HTTP endpoint to create new orders and publishes events to RabbitMQ.  
- **Order Worker (Consumer)** → Listens to the queue and processes incoming order messages.  

RabbitMQ runs via Docker Compose with the **management plugin** enabled so you can monitor queues and messages in real time.

## 🚀 Architecture

- The **Order API** accepts POST requests (`/order`) and publishes messages (`order.created`) to RabbitMQ.  
- The **Order Worker** consumes messages from the `order.created` queue and processes them (logs them to the console or stores them in a DB).  

---

## 🛠️ Tech Stack
- **RabbitMQ** (via Docker Compose)  
- **Node.js** (Express for API, [amqplib](https://www.npmjs.com/package/amqplib) for RabbitMQ integration)  
- **Docker** (to orchestrate RabbitMQ and services)  

