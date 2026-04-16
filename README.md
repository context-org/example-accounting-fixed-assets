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

### 2. Use it in your Python agent
from capsule_sdk import CapsuleLoader, Injector

capsule = CapsuleLoader.load("accounting/fixed-assets")
injector = Injector(capsule)

# Get the depreciation tool
calculate = injector.get_tool("calculate_straight_line")
depreciation = calculate(cost=10000, salvage=1000, life=5)
print(depreciation)  # 1800.0
