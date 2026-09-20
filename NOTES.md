# Honeypot Threat Intelligence Project — Notes

## Day 1

### Environment
- OS: Kali Linux
- User: kali
- Architecture: x86_64
- Kernel: 6.18.12
- VirtualBox networking: NAT
- Kali IP: 10.0.2.15

### Network
- Checked listening ports using `ss -tulpn`
- PostgreSQL is running on localhost port 5432
- PostgreSQL is not externally exposed
- No SSH service is currently listening

### Docker
- Installed Docker 28.5.2
- Enabled Docker service
- Docker service verified as active/running
- Successfully ran the `hello-world` Docker container

### Commands Learned
- `whoami` — displays current user
- `uname -a` — displays system/kernel information
- `ip addr` — displays network interfaces and IP addresses
- `ss -tulpn` — displays listening TCP/UDP ports and processes
- `systemctl status docker` — checks Docker service status
- `docker run hello-world` — tests Docker by running a container

### Key Learning
Docker allows applications to run inside isolated containers.
This will be used later to run the Cowrie SSH honeypot.

### Project Goal
Build a honeypot-based threat intelligence system that:
1. Collects attacker activity
2. Analyzes honeypot logs
3. Performs exploratory data analysis
4. Extracts security-related features
5. Uses machine learning for attack/anomaly detection
6. Performs graph analysis of attacker behavior
7. Presents findings through a dashboard

### Next
- Learn Docker fundamentals
- Understand Cowrie
- Deploy Cowrie in an isolated container

## Day 2

* Learned: honeypot = fake vulnerable system to safely study attacker behavior
* Low-interaction vs high-interaction honeypots — Cowrie is a low-interaction honeypot that emulates SSH/Telnet and does not provide attackers with a real underlying shell
* Practiced Docker: ran an Ubuntu container interactively using `docker run -it ubuntu bash`
* Practiced checking Docker containers and images using `docker ps -a` and `docker images`
* Pulled the `cowrie/cowrie` Docker image successfully (278MB)
* Key learning: image = blueprint/template, container = running instance of that image
* Next: configure and launch Cowrie — first verify that port 22 is free so there is no conflict with a real SSH service
