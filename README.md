## Table of Contents

- [Llegos: A strongly-typed Python DSL for multi-agent systems](#llegos-a-strongly-typed-python-dsl-for-multi-agent-systems)
  - [Features](#features)
  - [Quick Start Guide](#quick-start-guide)
    - [Installation](#installation)
    - [Need help?](#need-help)
  - [Core Concepts](#core-concepts)
    - [Objects](#objects)
    - [Messages](#messages)
    - [Actors](#actors)
    - [Scenes](#scenes)
  - [FAQ](#faq)
  - [Contributing](#contributing)
  - [Is it any good?](#is-it-any-good)

# Llegos: A strongly-typed Python DSL for multi-agent systems

> *"More of a PyTorch, less of a Keras", "More of a FastAPI, less of a Django"*

Llegos is a DSL for developing multi-agent systems in Python. It offers a set of building blocks that can be used to create complex, multi-layered environments where different groups of agents can interact within their sub-contexts. Llegos is designed to be flexible and generalizable, and it is not tied to any specific way of calling LLMs. Any logic, any combination of libraries in any order can be used in your agent implementation. Llegos elevates your agents into a multi-agent system.

You only need this 1 sentence to get an intuitive understanding of Llegos:

**"llegos.Actors send llegos.Messages and share llegos.Objects in llegos.Scenes."**

## Features

0. **Simple, made easy:** The whole API can can be conceptually grokked with the mnemonic **"llegos.Actors send llegos.Messages and share llegos.Objects in llegos.Scenes."**

1. **Strongly typed message passing:** At the heart of Llegos is its use of pedantic models for message passing. This ensures precision and clarity in communication, allowing for dynamically generated, well-structured messages crucial for complex multi-agent interactions.

2. **Messaging with email semantics** Llegos introduces an intuitive, email-like messaging system. Messages have parents, enabling functionalities like replying and forwarding, which enhances clarity and traceability in the system's communication.

3. **Bring your own libraries:** Whether that's Langchain, LlamaIndex, CamelAI, transformers... use Llegos Actors to elevate your agents into a multi-agent system, and coordinate them using a Scene.

4. **Flexibility and generalizability:** Llegos Scenes are themselves Actors, and can be nested within each other. This allows for the creation of complex, multi-layered environments where different groups of actors can interact within their sub-contexts.

## Quick Start Guide

Read through the `tests/` folder, in order, it has examples with comments showcasing Llegos' flexibility.

Requires: `python = ">=3.10,<=3.12"`

### Installation

```bash
pip install "git+https://github.com/shaman-ai/llegos.git@main"
poetry add "git+https://github.com/shaman-ai/llegos.git#main"
```

### Need help?

[DM Cyrus](https://x.com/CyrusOfEden)

## Core Concepts

Llegos is built upon several foundational elements that work together to enable complex interactions and behaviors within static and dynamic multi-agent systems.  Here's an overview of the key concepts that form the backbone of Llegos:

### Objects
- **Definition:** Objects are the fundamental entities in Llegos, defined using Pydantic models. They represent the base class from which other more specialized entities like Messages and Actors derive.
- **Customization:** Users can extend the Object class to create their own scene objects, complete with validation and serialization capabilities.
- **Dynamic Generation:** Users can dynamically generate objects using OpenAI function calling, [Instructor](https://github.com/jxnl/instructor), [Outlines](https://github.com/outlines-dev/outlines), etc.

### Messages

- **Purpose:** Messages serve as the primary means of communication between agents. They carry information, requests, commands, or any data that needs to be transmitted from one entity to another.
- **Structure and Handling:** Each message has an identifiable structure and is designed to be flexible and extensible. The system provides mechanisms for message validation, forwarding, replying, and tracking within conversation threads.
- **Email Semantics:** They are organized into hierarchical trees, allowing for the creation of complex communication patterns and protocols. Multiple replies can be sent to a single message, and each reply can have its own set of replies, and so on.

### Actors

- **Roles:** Actors are specialized objects that represent autonomous agents within the system. Each actor has its unique behavior, state, and communication abilities.
- **Interactions:** Actors interact with each other and the environment primarily through strongly-typed messages, responding to received information and making decisions based on their internal logic and objectives.

### Scenes

- **Contextual Containers:** Scenes act as containers or contexts in which actors operate and interact. They define the boundaries and properties of the environment that the agents are situated in.
- **Hierarchical Structure:** Scenes are Actors, allowing for the creation of complex, multi-layered environments where different groups of actors can interact within their sub-contexts.


## FAQ

**Q: What is the difference between Llegos and other multi-agent systems like AutoGen, CamelAI, ChatDev, Agent Actors?**

All those works are innovating in their own right as implementations of different interaction paradigms. Llegos is unique in that it makes it easier for you to express the design space of interaction paradigms, rather than offering you ready-built paradigms. It is a framework for building multi-agent systems, rather than configuring a specific multi-agent system.

**Q: How does Llegos relate to libraries like Langchain, LlamaIndex, Outlines, DSPy, Instructor?**

Llegos is a framework for building multi-agent systems, and it is designed to be flexible and generalizable, and it is not tied to any specific way of calling LLMs. Any combination of libraries in any order can be used in the implementation of your Llegos Actors, however you please.

## Contributing

We welcome contributions to Llegos! Whether you're interested in fixing bugs, adding new features, or improving documentation, your help is appreciated. Here's how you can contribute:

1. **Having discussions:** You can use the discussions feature of this Github repo to ask questions, share ideas, and discuss Llegos.
2. **Reporting Issues:** If you find a bug or have a suggestion for improvement, please open an issue through our issue tracker.
3. **Submitting Pull Requests:** Contributions to the codebase are welcomed. Please submit pull requests with clear descriptions of your changes and the benefits they bring.

## Is it any good?

Yes.
