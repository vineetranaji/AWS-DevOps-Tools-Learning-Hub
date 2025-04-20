## 1. AWS App Mesh

### 📌 What it is?
AWS App Mesh is a **service mesh** that provides **observability**, **security**, and **traffic control** for microservices running in **ECS**, **EKS**, or **EC2**. It standardizes communication between services using **Envoy** proxy sidecars.

### 📌 Why is it used?
- Enables **service-to-service communication** without requiring changes to the application code.
- Provides advanced traffic management with **retries**, **failover**, and **timeouts**.
- Supports **fine-grained traffic routing**, such as **canary deployments** and **blue/green deployments**.
- Offers **TLS encryption**, **mTLS-based authentication**, and **detailed telemetry** via CloudWatch, X-Ray, or Prometheus.

---

## 2. AWS Cloud Map

### 📌 What it is?
AWS Cloud Map is a **service discovery** and **resource registry** that lets you register any cloud resource (e.g., ECS services, EC2 instances, Lambda functions) and automatically keeps track of their metadata and locations.

### 📌 Why is it used?
- Allows microservices and cloud resources to be **registered with custom names**.
- Applications can discover resources using **DNS** or **HTTP API**.
- Keeps service registry up to date automatically, improving **resilience** and **scalability**.
- Works well in **dynamic environments** such as containerized and serverless apps.
- Integrates seamlessly with **Route 53**, **ECS**, **EKS**, **Lambda**, and **API Gateway**.

---

## 3. AWS CNI (Container Network Interface)

### 📌 What it is?
AWS CNI (Amazon VPC CNI plugin) provides **native VPC networking** for Kubernetes pods running in **EKS**, enabling them to be part of the VPC and have **directly routable IP addresses**.

### 📌 Why is it used?
- Assigns **Elastic Network Interfaces (ENIs)** and **VPC IPs** directly to pods, so no NAT is needed.
- Allows **fine-grained security controls** via **security groups** at the pod level.
- Ensures high **throughput** and **low latency** networking using AWS’s own VPC infrastructure.
- Compatible with AWS features like **PrivateLink**, **Transit Gateway**, and **Network ACLs**.
- Works with tools like **ALB Ingress Controller**, **CoreDNS**, and **KubeProxy**.

---

## 4. AWS Managed Control Plane (EKS Control Plane)

### 📌 What it is?
The AWS EKS Control Plane is a **fully managed Kubernetes control plane** that includes **API servers**, **etcd databases**, and **cluster controllers**, managed and maintained by AWS.

### 📌 Why is it used?
- Offloads the management of **Kubernetes master nodes**, **HA setup**, and **patching** to AWS.
- Provides **high availability** by distributing the control plane across **multiple Availability Zones**.
- Integrated with **IAM for RBAC**, **CloudTrail**, **CloudWatch**, and **KMS** for encryption.
- Automatically scales control plane resources based on load.
- Supports **secure and scalable** Kubernetes API access via public or private endpoints.

---

## 5. etcd (Used in EKS)

### 📌 What it is?
`etcd` is a **distributed key-value store** used by Kubernetes to store all cluster data, including **configuration**, **state**, **secrets**, and **service discovery information**.

### 📌 Why is it used?
- Acts as the **single source of truth** for Kubernetes cluster state.
- Stores critical data like **pod specifications**, **node status**, **secrets**, and **service discovery** records.
- Provides **strong consistency** and **fault tolerance** through a Raft consensus algorithm.
- In Amazon EKS, etcd is **fully managed and secured** by AWS and is not directly accessible by users.
- Snapshots and backups are automatically handled to ensure **disaster recovery** and **HA**.

## 6. AWS AppSync In-Memory Cache

### 📌 What it is?
A **caching layer** within AWS AppSync that temporarily stores **GraphQL query responses** in memory at the AppSync endpoint.

### 📌 Why is it used?
- Reduces **latency** and **backend load** by serving repeated identical queries from cache.
- Ideal for read-heavy GraphQL operations where real-time accuracy isn't critical.

### 📌 Key Details:
- **TTL (Time-To-Live)** is configurable between **1–3600 seconds**.
- Cache is stored **in-memory** (not persisted) and is **per API instance**.
- Works alongside AppSync's **resolver-level** caching.

### 📌 Example:
You frequently query user profile data. Instead of hitting DynamoDB every time, AppSync returns the cached response if it's still within the TTL window.

---

## 7. Parallel State (in AWS Step Functions)

### 📌 What it is?
A **Parallel state** in AWS Step Functions allows multiple **branches** of a state machine to run **concurrently**.

### 📌 Why is it used?
- Optimizes workflows by executing **independent tasks simultaneously**.
- Reduces total execution time in multi-step automation.

### 📌 Key Details:
- Each branch can contain a full state machine.
- All branches must succeed unless catch or error handling is specified.
- Common for **data processing**, **batch jobs**, and **multimedia workflows**.

### 📌 Example:
Processing a video file:
- One branch extracts audio.
- Another generates thumbnails.
- A third performs speech-to-text transcription.

### 📌 Sample Syntax:
```json
"ParallelState": {
  "Type": "Parallel",
  "Branches": [
    { "StartAt": "ExtractAudio", "States": { ... } },
    { "StartAt": "GenerateThumbnails", "States": { ... } }
  ],
  "Next": "NextState"
}
```

---

## 8. amplify init

### 📌 What it is?
A CLI command (`amplify init`) to **initialize a new AWS Amplify project** locally.

### 📌 Why is it used?
- Bootstraps a local Amplify environment.
- Connects your project to the Amplify backend.
- Prepares the project for adding features like **Auth**, **API**, **Storage**, etc.

### 📌 What it does?
- Creates an `amplify/` directory.
- Generates `amplifyconfiguration.json`.
- Prompts for:
  - Project name and environment
  - AWS profile to use
  - Default editor and runtime
  - Backend environment setup

### 📌 Example:
```bash
amplify init
```

---

## 9. Amazon DynamoDB Streams

### 📌 What it is?
A **change data capture** feature for DynamoDB that records a time-ordered sequence of **item-level changes** (INSERT, MODIFY, REMOVE).

### 📌 Why is it used?
- Enables **real-time event-driven architectures**.
- Allows triggering **Lambda functions** based on data changes.
- Supports use cases like **replication**, **auditing**, and **notifications**.

### 📌 Key Features:
- Stores stream records for **24 hours**.
- Delivers records **in order per partition key**.
- Can be **enabled per table**, and configured to capture `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, or `NEW_AND_OLD_IMAGES`.

### 📌 Example:
A new order is added to the `Orders` table. A stream sends the event to a **Lambda function** that sends a confirmation email to the customer.

