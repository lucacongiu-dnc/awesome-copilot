# Example: Azure Hub-Spoke Architecture

This is a template for creating Azure hub-spoke network architecture diagrams using draw.io.

## Diagram Overview

A hub-spoke network topology is a common Azure architecture pattern that centralizes shared services in a hub VNet while isolating workloads in spoke VNets.

## Mermaid Diagram

```mermaid
graph TB
    subgraph "Hub VNet (10.0.0.0/16)"
        FW[Azure Firewall<br/>Firewall Subnet: 10.0.1.0/24]
        VPN[VPN Gateway<br/>Gateway Subnet: 10.0.2.0/24]
        Bastion[Azure Bastion<br/>Bastion Subnet: 10.0.3.0/24]
    end

    subgraph "Spoke VNet 1 - Production (10.1.0.0/16)"
        AppGW[Application Gateway<br/>Public Subnet: 10.1.1.0/24]
        Apps[App Services<br/>Private Subnet: 10.1.2.0/24]
        DB[Azure SQL Database<br/>Data Subnet: 10.1.3.0/24]
        NSG1[Network Security Group]
    end

    subgraph "Spoke VNet 2 - Development (10.2.0.0/16)"
        VMs[Virtual Machines<br/>Private Subnet: 10.2.1.0/24]
        Storage[Storage Account<br/>with Private Endpoint]
        NSG2[Network Security Group]
    end

    subgraph "Monitoring"
        Monitor[Azure Monitor]
        LogAnalytics[Log Analytics Workspace]
    end

    FW -.VNet Peering.-> AppGW
    FW -.VNet Peering.-> VMs
    AppGW --> Apps
    Apps --> DB
    VMs --> Storage
    NSG1 --> Apps
    NSG2 --> VMs
    Monitor --> FW
    Monitor --> Apps
    Monitor --> VMs
    LogAnalytics --> Monitor
```

## Key Components

- **Hub VNet**: Centralized network with shared services
  - Azure Firewall for traffic inspection
  - VPN Gateway for hybrid connectivity
  - Azure Bastion for secure VM access

- **Spoke VNets**: Isolated workload environments
  - Production: Web applications with database
  - Development: Test VMs and storage

- **Security**: Network Security Groups on each subnet
- **Monitoring**: Azure Monitor and Log Analytics

## To Use This Template

1. Copy the Mermaid content above
2. Use the draw.io MCP tool: `open_drawio_mermaid`
3. Modify IP ranges, resource names, and components as needed
4. Load Azure icon libraries in draw.io for proper icons
5. Export as PNG, SVG, or PDF
