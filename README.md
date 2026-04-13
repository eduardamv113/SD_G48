**Distributed Time-Series Event Store**

This project was developed for the Distributed Systems (Sistemas Distribuídos) course at the University of Minho.

The goal was to build a high-performance Java server capable of managing billions of product sale events across multiple days. The system allows concurrent clients to register sales, query statistics (averages, maximums, volumes), and subscribe to real-time event notifications.

*Technical Core*

1. Custom Binary Protocol: Implemented using DataInputStream and DataOutputStream over raw TCP sockets (no high-level serialization libraries).

2. Concurrency & Performance: Optimized for low contention using Java threads, ensuring that slow requests from a client don't block other concurrent requests from the same user.

3. Intelligent Storage: * Lazy Aggregation: Calculations are performed on-demand and cached for future use.

4. Memory Management: Implements a strict memory limit ($S < D$), swapping data between RAM and disk to handle datasets larger than the available memory.

5. Advanced Synchronization: Features blocking operations for specific event patterns (e.g., waiting for two specific products to be sold simultaneously).

*Project Components*

1. Server: The multithreaded core managing persistence, authentication, and concurrency.

2. Client Library: A reusable Java API for interacting with the service.

3. UI/Test Suite: A client interface for performance benchmarking and robustness testing.


Final Grade: 15/20
