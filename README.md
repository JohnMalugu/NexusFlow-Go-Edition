# NexusFlow (Go Edition)

### **The High-Performance Execution Engine**
NexusFlow (Go Edition) is a cloud-native distributed task engine built for speed and massive concurrency. This implementation showcases the power of **Golang** in building lightweight infrastructure agents that can handle thousands of simultaneous task executions with minimal resource overhead.



## 📖 Detailed Description
While the Java edition focuses on orchestration, the Go edition is built for pure **execution performance**. In this project, the system acts as a high-speed consumer that pulls tasks from a central queue and executes them using a pool of **Goroutines**. This "Muscle" service is designed to be stateless and horizontally scalable, meaning you can spin up 100 instances in seconds to handle sudden spikes in automation demand.

The use of the **Gin Gonic** framework ensures that the internal API remains low-latency. Real-time observability is achieved through a **Redis-backed heartbeat system**, which allows the cluster to monitor the health of every worker node dynamically. If a worker goes offline, the system detects the missing heartbeat and can re-route tasks to healthy nodes.

## 🛠️ Technical Modules
- **Concurrency Manager:** Uses Channels and Goroutines to manage a dynamic pool of workers.
- **Event Consumer:** High-throughput RabbitMQ client with pre-fetch limits to prevent worker overload.
- **Task Executors:** Modular drivers for executing Shell scripts, HTTP requests, and custom logic.
- **Health System:** Periodic heartbeat emitter to Redis for cluster membership management.

## 💡 Why This Architecture?
* **Efficiency:** Go’s memory footprint is significantly lower than JVM-based alternatives, reducing infrastructure costs.
* **Speed:** Near-instant startup times make this implementation ideal for containerized or serverless deployments.
* **Non-blocking I/O:** Perfect for tasks that spend a lot of time waiting on network calls or file system operations.

## 🚀 Getting Started
1. **Clone:** `git clone https://github.com/your-username/nexusflow-go.git`
2. **Dependencies:** `go mod download`
3. **Run:** `go run main.go`
