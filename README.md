# NetworkIdentifier

**NetworkIdentifier** is a Rust-based command-line tool designed to provide key information about the network properties of a system. It identifies various aspects such as NAT (Network Address Translation) type, public IP address, Internet Service Provider (ISP) details, geographical location, and DNS status. This program helps users and network administrators to better understand the configuration and behavior of their network, offering a simple and efficient way to gather critical network data.

## Features

### 1. **NAT Type Detection**
- Detects if the system is behind a NAT (Network Address Translation) and determines the type of NAT being used (e.g., full cone, restricted cone, symmetric NAT).
- Helps in identifying potential issues with connectivity for applications that require direct peer-to-peer connections.

### 2. **Public IP Address Identification**
- Retrieves the current public IP address of the system.
- Displays both IPv4 and IPv6 addresses (if available).
- Useful for verifying the IP address exposed to the internet, especially in cases where a dynamic IP is assigned by the ISP.

### 3. **Internet Service Provider (ISP) Identification**
- Uses the public IP address to determine the ISP responsible for the network connection.
- Provides information on the provider's name and ASN (Autonomous System Number).
- Can be useful for troubleshooting or auditing network connections.

### 4. **Geographical Location**
- Determines the physical location associated with the public IP address, including country, region, and city.
- Can be helpful for verifying the routing and location of network traffic.

### 5. **DNS Status and Configuration**
- Checks the system’s DNS configuration, including the primary and secondary DNS servers in use.
- Verifies DNS resolution performance and can identify any potential issues such as DNS hijacking, slow DNS resolution, or misconfigured servers.

### 6. **Connectivity and Latency Tests**
- Performs basic ping tests to check the reachability and latency of common services such as DNS servers or public IP endpoints.
- Displays round-trip time (RTT) to identify network speed and latency issues.

## Installation

To install **NetworkIdentifier**, you need to have **Rust** and **Cargo** installed on your machine. You can install them by following the instructions at [Rust's official website](https://www.rust-lang.org/).

Once Rust is installed, you can clone the repository and build the program:

```bash
git clone https://github.com/yourusername/NetworkIdentifier.git
cd NetworkIdentifier
cargo build --release
```

## Usage

After building the project, you can run the executable to start gathering network information:

```bash
./target/release/networkidentifier
```

The program will output detailed network properties, including NAT type, public IP, ISP, geographical location, and DNS configuration.

### Example Output

```bash
NetworkIdentifier - Network Properties:
-------------------------------------------------
NAT Type: Full Cone NAT
Public IP: 203.0.113.10
IPv6 Address: 2001:db8::1
ISP: Example ISP (ASN 12345)
Location: New York, United States
DNS Servers: 8.8.8.8, 8.8.4.4
DNS Resolution: Successful
Ping to DNS Server: 12ms (Average RTT)
-------------------------------------------------
```

## Future Enhancements
- **Support for VPN Detection**: Identify if the user is connected through a VPN and detect the exit node's location.
- **Traceroute Integration**: Offer a detailed traceroute feature to map the route packets take to their destination.
- **Network Security Analysis**: Identify potential security vulnerabilities in the network setup, such as open ports or weak encryption protocols.
- **Logging**: Option to log the results to a file for further analysis or auditing purposes.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.

---

**NetworkIdentifier** is designed to provide a clear and comprehensive view of the network properties, making it easier for users and administrators to troubleshoot, audit, and optimize their network configurations. Built with Rust, the program is designed to be fast, reliable, and secure.