# Fixed Assets (GAAP) – Context Capsule

**ID:** `accounting/fixed-assets`  
**Version:** 1.0.0  
**Author:** Context Org  
**License:** MIT  

## What This Capsule Gives You

This capsule turns any AI agent into a **fixed‑asset accounting assistant** under US GAAP. It provides:

- ✅ **Straight‑line depreciation calculation** (tool + formula)
- ✅ **Rules of thumb** for useful lives and salvage value
- ✅ **A simple process graph** for depreciation workflow

You don’t need to train or fine‑tune your model. Just load the capsule and your agent instantly knows how to handle fixed‑asset tasks.

## When to Use This Capsule

- You need to compute annual depreciation for an asset.
- You want to explain GAAP depreciation rules to a client or a junior accountant.
- You’re building an automation that processes asset ledgers.

> **Not for**: Assets with accelerated depreciation (e.g., double‑declining) or tax‑specific calculations (e.g., Section 179). Those will be added in future versions.

## Quick Start

### 1. Install the capsule

```bash
capsule install accounting/fixed-assets
2. Use it in your Python agent
python
from capsule_sdk import CapsuleLoader, Injector

capsule = CapsuleLoader.load("accounting/fixed-assets")
injector = Injector(capsule)

# Get the depreciation tool
calculate = injector.get_tool("calculate_straight_line")
depreciation = calculate(cost=10000, salvage=1000, life=5)
print(depreciation)  # 1800.0
3. Or let your agent reason with the capsule’s knowledge
The capsule injects rules and a process graph into your agent’s system prompt. Your agent will then “know” GAAP fixed‑asset principles and can explain them step by step.

What’s Inside
File	Purpose
manifest.yaml	Capsule identity and metadata.
process_graph.json	The workflow (load asset → select method → compute → record).
knowledge/knowledge.jsonl	GAAP rules with public source citations.
src/tools.py	Depreciation calculation function.
tests/	Unit tests for the tool and graph.
sources.csv	Provenance for every rule (IRS Pub 946, FASB ASC).
Validating the Capsule
After cloning or# Fixed Assets (GAAP) – Context Capsule

**ID:** `accounting/fixed-assets`  
**Version:** 1.0.0  
**Author:** Context Org  
**License:** MIT  

## What This Capsule Gives You

This capsule turns any AI agent into a **fixed‑asset accounting assistant** under US GAAP. It provides:

- ✅ **Straight‑line depreciation calculation** (tool + formula)
- ✅ **Rules of thumb** for useful lives and salvage value
- ✅ **A simple process graph** for depreciation workflow

You don’t need to train or fine‑tune your model. Just load the capsule and your agent instantly knows how to handle fixed‑asset tasks.

## When to Use This Capsule

- You need to compute annual depreciation for an asset.
- You want to explain GAAP depreciation rules to a client or a junior accountant.
- You’re building an automation that processes asset ledgers.

> **Not for**: Assets with accelerated depreciation (e.g., double‑declining) or tax‑specific calculations (e.g., Section 179). Those will be added in future versions.

## Quick Start

### 1. Install the capsule

```bash
capsule install accounting/fixed-assets
2. Use it in your Python agent
python
from capsule_sdk import CapsuleLoader, Injector

capsule = CapsuleLoader.load("accounting/fixed-assets")
injector = Injector(capsule)

# Get the depreciation tool
calculate = injector.get_tool("calculate_straight_line")
depreciation = calculate(cost=10000, salvage=1000, life=5)
print(depreciation)  # 1800.0
3. Or let your agent reason with the capsule’s knowledge
The capsule injects rules and a process graph into your agent’s system prompt. Your agent will then “know” GAAP fixed‑asset principles and can explain them step by step.

What’s Inside
File	Purpose
manifest.yaml	Capsule identity and metadata.
process_graph.json	The workflow (load asset → select method → compute → record).
knowledge/knowledge.jsonl	GAAP rules with public source citations.
src/tools.py	Depreciation calculation function.
tests/	Unit tests for the tool and graph.
sources.csv	Provenance for every rule (IRS Pub 946, FASB ASC).
Validating the Capsule
After cloning or downloading, run:

bash
pytest tests/
All tests should pass. This capsule is self‑certified (Level 1) – it passes automated checks. Future versions may seek community or professional verification.

Source Integrity
Every rule in this capsule traces back to a public, verifiable source. See sources.csv for the exact URLs and licenses. We do not use copyrighted textbooks or proprietary content.

Contributing
Found a mistake or want to add more depreciation methods? Fork the repository, add your changes, and submit a pull request. Please update sources.csv with your sources.

License
MIT – use freely, even in commercial products. Attribution appreciated but not required.

“Expertise, injected.” – The Context Capsule Project downloading, run:

bash
pytest tests/
All tests should pass. This capsule is self‑certified (Level 1) – it passes automated checks. Future versions may seek community or professional verification.

Source Integrity
Every rule in this capsule traces back to a public, verifiable source. See sources.csv for the exact URLs and licenses. We do not use copyrighted textbooks or proprietary content.

Contributing
Found a mistake or want to add more depreciation methods? Fork the repository, add your changes, and submit a pull request. Please update sources.csv with your sources.

License
MIT – use freely, even in commercial products. Attribution appreciated but not required.

“Expertise, injected.” – The Context Capsule Project
