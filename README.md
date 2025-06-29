# ⚖️ Load Balancer Simulator in C++

## 📌 Project Overview

This project simulates a **Load Balancer System** written in C++. It demonstrates how various load balancing strategies handle incoming network requests in a multi-server environment. The system includes three widely used algorithms:

- ✅ **Least Connection**
- 🔁 **Routed (Hash-Based)**
- 🔄 **Round Robin**

Each request is routed to a suitable destination (server) based on the chosen algorithm and destination server load.

---

## 🚀 Features

### ✅ Three Load Balancing Algorithms
- **Least Connection**: Directs the request to the server with the fewest active connections.
- **Routed**: Hashes the request ID to consistently route similar requests to the same server.
- **Round Robin**: Distributes requests cyclically across all servers.

### 🧪 Simulated Request Processing
- Requests are asynchronously processed using `std::thread`.
- Each server maintains a count of currently processed requests.
- Servers have a **threshold limit** beyond which they reject new requests.

### 💻 Interactive CLI
- User can choose a load balancing strategy at runtime.
- Requests are generated with unique IDs and routed accordingly.

---

## 🧠 Concepts Used

- **Object-Oriented Programming (OOP)**  
  Classes like `Request`, `Destination`, `Service`, and `LoadBalancer` are used to encapsulate logic.

- **Polymorphism**  
  Load balancing strategy selection is achieved via the virtual method `balanceLoad`.

- **Multithreading**  
  Simulates asynchronous processing of requests using detached `std::thread`.

- **Data Structures**  
  Utilizes STL containers like `unordered_map`, `queue`, `set`, and `vector` for efficient request routing and server management.

---

## 🔧 How It Works

1. **Setup**  
   Three destination servers (`192.168.0.1`, `192.168.0.2`, `192.168.0.3`) are added to a service.  
   Each server has a defined **threshold** (maximum concurrent requests it can handle).

2. **Load Balancer Selection**  
   The user chooses a load balancing algorithm from the menu.

3. **Routing**  
   Based on the chosen algorithm, a server is selected to handle the request.  
   If the server is under the threshold, it accepts and starts processing.

4. **Request Completion**  
   Each request is simulated to "process" for 100 seconds using a separate thread.  
   After that, the server’s active request count is decremented.

---

## ▶️ How to Run

### 🛠️ Compile the Code

```bash
g++ -std=c++11 -pthread load_balancer.cpp -o load_balancer
```

### ▶️ Run the Program

```bash
./load_balancer
```

### 🧭 Follow the Prompts
- Choose a load balancing algorithm.
- Enter a unique request ID.
- Watch how the request is routed and processed.

---

## 📂 File Structure

```
load_balancer.cpp   # Main C++ source file with all logic
README.md           # Project documentation
```

---

## 📈 Future Improvements

- Add a GUI/web interface to visualize server loads in real-time.
- Support request cancellation or dynamic threshold configuration.
- Persist logs of server load and request flow.
- Simulate network latency and server failures.

---

## 📚 Learning Outcomes

This project helped reinforce:

- ✅ OOP principles like inheritance and polymorphism
- 🧵 Multithreaded programming using `std::thread`
- 🌐 Real-world concepts of load balancing in distributed systems

---

## 📬 Author

**Vedant Savani**  
> Feel free to fork, enhance, or suggest improvements!
