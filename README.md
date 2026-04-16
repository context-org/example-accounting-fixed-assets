# Fixed Assets (GAAP) – Context Capsule

**ID:** `accounting/fixed-assets`
**Version:** 1.0.0
**Author:** Context Org
**License:** MIT

---

# Overview

This capsule turns any AI agent into a **fixed-asset accounting assistant** under **US GAAP**.

It provides:

* Straight-line depreciation calculation (tool + formula)
* Rules of thumb for useful lives and salvage value
* A simple workflow for depreciation processing

No model training or fine-tuning is required.
Load the capsule and the agent immediately gains the domain capability.

---

# When to Use This Capsule

Use this capsule when:

* Computing **annual depreciation for a fixed asset**
* Explaining **GAAP depreciation rules** to a client or junior accountant
* Building **automation that processes asset ledgers**

**Not intended for:**

* Accelerated depreciation methods (double-declining, etc.)
* Tax depreciation (Section 179, bonus depreciation)

Future capsule versions may include these.

---

# Quick Start

## 1. Install the capsule

```bash
capsule install accounting/fixed-assets
```

---

## 2. Use it in a Python agent

```python
from capsule_sdk import CapsuleLoader, Injector

capsule = CapsuleLoader.load("accounting/fixed-assets")
injector = Injector(capsule)

# Retrieve the depreciation calculation tool
calculate = injector.get_tool("calculate_straight_line")

depreciation = calculate(
    cost=10000,
    salvage=1000,
    life=5
)

print(depreciation)
# Output: 1800.0
```

---

## 3. Allow the agent to reason with the capsule

When loaded, the capsule injects:

* domain rules
* a process graph
* accounting knowledge

into the agent's system context.

The agent can then:

* explain depreciation
* guide a user through the calculation
* perform the calculation automatically

---

# Capsule Contents

| File                        | Purpose                             |
| --------------------------- | ----------------------------------- |
| `manifest.yaml`             | Capsule identity and metadata       |
| `process_graph.json`        | Depreciation workflow               |
| `knowledge/knowledge.jsonl` | GAAP rules with citations           |
| `src/tools.py`              | Straight-line depreciation function |
| `tests/`                    | Unit tests                          |
| `sources.csv`               | Source provenance                   |

---

# Process Graph

The capsule includes a workflow describing the depreciation process:

```
Load Asset
   ↓
Select Depreciation Method
   ↓
Calculate Depreciation
   ↓
Record Journal Entry
```

Agents can use this structure to reason about the task.

---

# Validating the Capsule

After cloning or downloading the capsule repository:

```bash
pytest tests/
```

All tests should pass.

This capsule is **Self-Certified (Level 1)**, meaning it passes automated validation checks.

Future releases may support **community or professional verification levels**.

---

# Source Integrity

Every rule in this capsule is linked to a **public, verifiable source**.

Examples include:

* IRS Publication 946
* FASB ASC references
* Other publicly available accounting guidance

All citations and licenses are listed in:

```
sources.csv
```

No proprietary textbooks or copyrighted content are used.

---

# Contributing

Contributions are welcome.

If you find an issue or want to add additional depreciation methods:

1. Fork the repository
2. Make your changes
3. Update `sources.csv` with citations
4. Submit a pull request

---

# License

MIT License.

This capsule may be used in **commercial or open-source projects**.

Attribution is appreciated but not required.

---

**"Expertise, injected." – The Context Capsule Project**
