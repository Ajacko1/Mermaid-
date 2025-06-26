# DDoS Attack Sequence Diagram

Below shows how a typical Distributed Denial of Service (DDoS) attack happens against a company’s web server. It walks through the steps taken by the attacker and their botnet of infected machines, and how the firewall and server respond during the attack. 

mermaid
sequenceDiagram
    participant Attacker
    participant BotNet
    participant Firewall
    participant WebServer

  Attacker->BotNet: Command bots to start the main attack 

  Flood request
    Botnet->Firewall: Massive HTTP requests
    Firewall->Webserver: Forward requests

Firewall->Firewall: Detects the traffic anomaly
Firewall->BotNet: Blocks suspicious IPs
Firewall->Webserver: Drops excess requests
Webserver->Firewall: Status Gets Overloaded
Firewall->Attacker: Alert goes out after a DDoS attack is detected
    

  
