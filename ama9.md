# AMA Session Questions and Answers

## Adhikya Edammala: What are the default tables in Django Admin?

When you run Django migrations, several default tables are created, including:

- `auth_user` – Stores user accounts.
- `auth_group` – Stores user groups.
- `auth_permission` – Stores permissions.
- `django_admin_log` – Records admin site actions.
- `django_content_type` – Tracks installed models.
- `django_session` – Stores session data.
- `django_migrations` – Keeps track of applied migrations.

---

## Allanki VV Manikanta Sai: What is the command to remove a Docker container?

Remove a stopped container:

```bash
docker rm <container_id_or_name>
```

Force remove a running container:

```bash
docker rm -f <container_id_or_name>
```

---

## Arpit Yadav: What is a Docker repository?

A Docker repository is a collection of Docker images with the same name but different tags (versions). Repositories are stored in a Docker registry such as Docker Hub or a private registry.

---

## Boorle Sowmya Sri Lakshmi: What is meant by a RabbitMQ cluster?

A **RabbitMQ cluster** is a group of RabbitMQ nodes working together as a single messaging system.

### Benefits:
- High availability
- Load distribution
- Fault tolerance
- Scalability


---

## Md Musharaf: What is a Dead Letter Queue (DLQ) in RabbitMQ?

A **Dead Letter Queue (DLQ)** stores messages that cannot be processed successfully.

Messages are moved to a DLQ when:
- They are rejected without requeue.
- They expire.
- The queue reaches its maximum length.
- They cannot be routed.

---

## Naman Sharma: What are ACK signal and Auto ACK in RabbitMQ?

### ACK (Acknowledgment)

An ACK is sent by the consumer after successfully processing a message.

- Ensures reliable message delivery.
- If no ACK is received, RabbitMQ can redeliver the message.

### Auto ACK

With Auto ACK enabled, RabbitMQ considers the message delivered immediately after sending it to the consumer.

- Faster performance.
- Risk of message loss if the consumer crashes before processing the message.

---

## Nayunipatruni Harsha Vardhan: What is the command to see logs of a Docker container?

View container logs:

```bash
docker logs <container_name_or_id>
```

---

## Parlapalli Sulochana: What is the difference between `RUN` and `CMD` in a Dockerfile?

| RUN | CMD |
|------|-----|
| Executes commands during image build. | Specifies the default command when a container starts. |
| Creates a new image layer. | Does not create a new image layer during build. |

---

## Rongala Vasu: What is the difference between Docker and a Virtual Machine?

| Docker | Virtual Machine |
|---------|-----------------|
| Uses containerization. | Uses hardware virtualization. |
| Shares the host OS kernel. | Includes a full guest operating system. |
| Lightweight and fast. | Heavier and slower. |
| Starts in seconds. | Takes longer to boot. |
| Uses less memory and storage. | Uses more memory and storage. |
| Best for microservices and cloud-native apps. | Best for running different operating systems on the same hardware. |

---

## Rovinpal Udupi: What is Cache Avalanche in Redis?

A **Cache Avalanche** occurs when many cached keys expire at the same time, causing a large number of requests to hit the database simultaneously.

### Causes
- Many keys have the same expiration time.
- Redis server failure.
- Cache eviction.

### Prevention
- Use random expiration times (TTL jitter).
- Enable Redis replication and high availability.
- Implement cache warming.
- Use rate limiting and request throttling.
- Use distributed caching strategies.

This reduces sudden spikes in database load and improves system stability.
