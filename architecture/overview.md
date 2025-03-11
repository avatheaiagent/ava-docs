# Architecture Overview

The Ava Portfolio Manager implements a sophisticated multi-agent architecture designed for autonomous DeFi portfolio management across multiple blockchains. This document provides a high-level overview of the system architecture, its key components, and their interactions.

## System Architecture

Ava's architecture follows a distributed, event-driven design with specialized agents working together to provide comprehensive DeFi portfolio management capabilities. The system consists of several interconnected layers:

![Architecture Diagram](../assets/architecture-diagram.png)

### Architecture Layers

1. **Frontend Layer**: User interface and interaction components
2. **Agent Layer**: Specialized autonomous agents for different tasks
3. **Service Layer**: Shared services used by multiple agents
4. **Integration Layer**: Connectors to external protocols and chains
5. **Blockchain Layer**: Underlying blockchain networks and protocols

## Core Components

### Frontend Application

The frontend application provides the user interface for interacting with the Ava system. It includes:

- **Chat Interface**: Natural language communication with the system
- **Portfolio Dashboard**: Visualization of portfolio status and performance
- **Transaction History**: Record of executed transactions
- **System Status**: Real-time status of agents and operations

### Event Bus

The event bus serves as the central communication mechanism between all system components. It:

- Enables asynchronous communication between agents
- Follows a publish-subscribe pattern
- Supports topic-based routing of events
- Provides reliable delivery of messages
- Enables loose coupling between components

### Storage System

The storage system provides persistence capabilities to the agents:

- **State Storage**: Maintains agent state and configuration
- **Transaction Records**: Stores transaction history and results
- **User Preferences**: Stores user preferences and settings
- **System Logs**: Records detailed system logs for debugging

### Agent Framework

The agent framework provides the foundation for all agents in the system:

- **Base Agent Class**: Common functionality for all agents
- **Agent Lifecycle Management**: Agent initialization and shutdown
- **Event Handling**: Processing of events from the event bus
- **Error Handling**: Standardized error management

## Agent Ecosystem

The Ava system consists of multiple specialized agents working together:

### Core Agents

- **Task Manager Agent**: Coordinates complex operations across agents
- **Observer Agent**: Monitors blockchain state and portfolio performance
- **Executor Agent**: Executes transactions on blockchains

### Protocol-Specific Agents

- **Sonic Agent**: Interacts with Sonic Protocol for DEX operations
- **Move Agent**: Manages interactions with Move-based blockchains
- **Hedera Agent**: Specializes in Hedera network operations
- **SXT Analytics Agent**: Provides data analytics via Space and Time
- **CDP Agent**: Manages collateralized debt positions
- **Zircuit Agent**: Interfaces with Zircuit Protocol
- **Sei Money Market Agent**: Manages lending and borrowing on Sei

### Supporting Agents

- **Safe Wallet Agent**: Manages Safe smart accounts
- **Superchain Bridge Agent**: Facilitates cross-chain operations
- **Eliza Agent**: Provides natural language understanding
- **Enso Agent**: Interfaces with Enso Finance
- **CoW Trading Agent**: Optimizes trading via CoW Protocol
- **Lit Agent Wallet**: Manages key management and signing

## Communication Patterns

Agents communicate using standardized event patterns:

### Request-Response Pattern

```
UserRequest → Observer → TaskManager → SpecializedAgent → TaskManager → Observer → UserResponse
```

### Event-Based Pattern

```
BlockchainEvent → Observer → TaskManager → SpecializedAgents → Actions
```

### Notification Pattern

```
AgentAction → EventBus → InterestedAgents
```

## Data Flow

Data flows through the system in a structured manner:

1. **Input**: User requests via natural language or UI actions
2. **Processing**: Request analysis and task creation
3. **Execution**: Delegation to specialized agents
4. **Result Collection**: Gathering and aggregating results
5. **Presentation**: Formatting and presenting results to users

## Security Architecture

The system implements multiple security layers:

- **Authentication**: Secure user authentication via web3 wallets
- **Authorization**: Permission-based access to system functions
- **Encryption**: Secure storage of sensitive data
- **Transaction Validation**: Multi-stage validation before execution
- **Audit Logging**: Comprehensive logging of all system actions

## Deployment Architecture

Ava can be deployed in various configurations:

### Self-Hosted Deployment

- **Server**: Node.js backend running the agent system
- **Database**: Persistent storage for agent state
- **Frontend**: Next.js web application
- **Event Bus**: In-memory or Redis-based message queue

### Cloud Deployment

- **Compute**: Containerized agents running in Kubernetes
- **Storage**: Cloud-based storage services
- **Frontend**: CDN-distributed web application
- **Event Bus**: Managed message queue service

## Extensibility

The architecture is designed for extensibility:

- **Plugin System**: Support for custom plugins
- **New Agents**: Easy addition of new specialized agents
- **Protocol Integration**: Standardized protocol integration framework
- **Chain Support**: Framework for adding new blockchain support

## Scalability Considerations

The system is designed to scale with:

- **Horizontal Scaling**: Adding more instances of agents
- **Load Distribution**: Distributing work across multiple agents
- **Resource Optimization**: Efficient resource utilization
- **Caching**: Strategic caching for performance

## Fault Tolerance

Ava includes several fault tolerance mechanisms:

- **Agent Recovery**: Automatic recovery from agent failures
- **Task Retry**: Retry mechanisms for failed tasks
- **State Persistence**: Preservation of state during failures
- **Circuit Breakers**: Prevention of cascading failures

## Future Architecture

The architectural roadmap includes:

- **Sharded Agents**: Specialized agent instances for different users
- **Machine Learning Components**: Enhanced decision making
- **Cross-Agent Optimization**: Coordinated optimization of operations
- **Enhanced Privacy**: Cryptographic privacy for user operations 