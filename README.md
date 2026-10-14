
# Hello, World!

> <sub>In the of this section there is arrows explaining words that could be hard to understand this will work as a diconary</sub>

This is a simple "Hello, world!" project that demonstrates how to use the [FixedIT Data Agent](https://fixedit.ai/products-data-agent/) to print messages to the standard output of the Telegraf process, which will be captured by the FixedIT Data Agent and displayed in the `Logs` tab.

<div align=left>
<details>
<summary><b>What is Telegraf?</b></summary>

an agent that collects information from computers and systems. This is only possible because of plugins, small building blocks that each handle one specific task

</details>
</div>

## How it works

The data moves through three stages:

**1. Two inputs create data**

Both inputs use the `inputs.mock` plugin, which generates fake test data.
- The first input creates a "Hello, World!" message plus a random number and a fixed number. It runs on the global interval, which is once per minute by default.
- The second input creates a sine wave every 5 seconds.

**2. One output collects it**

All data is sent to the `outputs.file` plugin, which turns it into JSON text and prints it.

**3. You see it in the Logs tab**

The FixedIT Data Agent captures the printed text and shows it in the **Logs** tab.

Color scheme:

- Light green: Input nodes / data ingestion
- Light red: Output nodes
- Light gray: Configuration and agent

```mermaid
flowchart TD
    X0["⚙️ Configuration Variables:<br/>SYNC_INTERVAL_SECONDS, TELEGRAF_DEBUG"] --> X1
    X1["Telegraf Agent"]

    X2["Configuration override:<br/>'interval'"] --> A2

    A1["📥 Mock Input 1<br/>Global Interval"] --> C
    A2["📥 Mock Input 2<br/>5s Override Interval"] --> C
    C["📤 Output to stdout<br/>JSON format"]

    style X0 fill:#f5f5f5,stroke:#9e9e9e,color:#000000
    style X1 fill:#f5f5f5,stroke:#9e9e9e,color:#000000
    style X2 fill:#f5f5f5,stroke:#9e9e9e,color:#000000
    style A1 fill:#90EE90,stroke:#43a047,color:#000000
    style A2 fill:#90EE90,stroke:#43a047,color:#000000
    style C fill:#ffebee,stroke:#e53935,color:#000000
```
## Why this approach?

Normally, building an app that runs directly on an Axis camera means learning the ACAP SDK and writing C or C++. With the FixedIT Data Agent, you only write a config file, and Telegraf does the rest. This makes it possible for developers, system integrators and IT professionals to build their own automations on the camera.

This project is the smallest possible example: two inputs, one output and nothing else. It's a good starting point for understanding how the agent's configuration works.

<details>
<summary><b>What is ACAP?</b></summary>

ACAP (Axis Camera Application Platform) lets you build custom applications that run directly on Axis devices, such as cameras, intercoms and speakers.

</details>

<details>
<summary><b>What is an SDK?</b></summary>

An SDK (Software Development Kit) is a package of tools, code libraries, documentation and examples that help programmers build software for a specific platform.

</details>



