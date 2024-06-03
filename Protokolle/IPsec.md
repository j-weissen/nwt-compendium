**IPsec** (Internet Protocol Security) is a suite of protocols that secures communication over IPv6 and IPv4 networks. It works by encrypting data packets and authenticating the sender and receiver. IPsec operates in two different modes: **Tunnel Mode** and **Transport Mode**. Authentication is possible via pre-shared keys, certificates, and Kerberos.
Firewalls need to be properly configured so IPSec can be used trespassing them.

**Key Differences:**

| Feature            | Tunnel Mode                                 | Transport Mode                                          |
| ------------------ | ------------------------------------------- | ------------------------------------------------------- |
| **Encryption**     | Entire IP packet (header & data)            | Only data (payload)                                     |
| **Authentication** | ESP Header to ESP Trailer                   | ESP Header to ESP Trailer                               |
| **Use Case**       | VPN connections between two LANs            | Remote client connection to a server                    |
| **Advantages**     | Highest security, hides client IP addresses | Lower overhead, good for bandwidth-limited applications |
| **Disadvantages**  | Higher overhead, complex configuration      | Less protection, client IP addresses exposed            |

- **AH (Authentication Header):** data integrity protection, but no encryption
- **ESP (Encapsulating Security Payload):** confidentiality and data integrity protection
- **IKE (Internet Key Exchange):** key exchange and authentication, current version is IKEv2

### Used in
- VPNs
- remote access connections
- LAN-to-LAN connections