# Nokia SR-OS RPKI Validation Lab with Containerlab

This project demonstrates the use of Containerlab to set up a Nokia SR-OS topology performing RPKI (Resource Public Key Infrastructure) validation. RPKI is a crucial security mechanism used to verify the legitimacy of IP address ownership in BGP routing, preventing route hijacking and other BGP-related attacks.

This lab was based on the concept by JulioPDX [RPKI in the Lab](https://juliopdx.com/2023/01/02/rpki-in-the-lab/#getting-rpki-in-the-lab-with-routinator)

## Overview

The project provides a reproducible Containerlab-based environment to emulate a network of Nokia SR-OS routers configured for RPKI validation. This lab allows testing and experimentation with RPKI in a controlled setting.

## Features

- Simulation of a Nokia SR-OS network using Containerlab.
- Example configuration for RPKI validation.
- Easily modifiable topology for various test scenarios.
  
## Prerequisites

Before starting, ensure you have the following:

- [Containerlab](https://containerlab.srlinux.dev/) installed for orchestrating the topology.
- Nokia SR-OS container images and a license file.
- Basic understanding of RPKI and BGP routing protocols.

## Topology

The Containerlab topology simulates a network of Nokia SR-OS routers performing BGP route validation with RPKI. This setup emulates real-world scenarios where routers validate routes against ROAs (Route Origin Authorizations) to ensure the authenticity of route announcements.

## Getting Started

### 1. Clone the Repository
Clone this repository to your local environment:

bash
git clone https://github.com/tomncarter/sros-rpki-lab.git
cd sros-rpki-lab

### 2. Deploy the Topology
Use Containerlab to deploy the Nokia SR-OS topology by running the following command:

bash
Copy code
containerlab deploy -t topology.clab.yml
This will set up the topology as defined in the topology.clab.yml file, deploying Nokia SR-OS nodes.

### 3. Access the SR-OS Nodes
Once the topology is deployed, access the Nokia SR-OS nodes using:

bash
Copy code
ssh admin@<node-ip>

### 4. Configure RPKI on SR-OS
After accessing the nodes, follow the example configuration to enable RPKI on the Nokia SR-OS routers and connect them to the RPKI validator in the topology.

## Example Topology
The topology defined in sros-rpki.clab.yaml includes:

## Multiple Nokia SR-OS routers interconnected in a BGP network.
A pre-configured RPKI validator.
Simulated route advertisements and validation for testing.
The topology is easily modifiable to include more nodes, routers, or links to fit your testing needs.

## Usage
Test BGP route validation using RPKI in a Nokia SR-OS network.
Simulate real-world routing scenarios and observe the effect of valid, invalid, and not found ROAs on route validation.
Experiment with route filtering and decision-making based on RPKI validation results.

## Troubleshooting
Ensure the RPKI validator is correctly configured and that the SR-OS devices can communicate with it.
Use appropriate show commands on the SR-OS routers to check the status of RPKI validation and troubleshoot any issues.
Verify connectivity between all devices in the topology.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
