# Antigravity Global Rules & Development Standards

Central repository for managing and distributing universal operational rules, behavioral guardrails, and engineering standards for Google Antigravity across all development environments and workstations under **santosh.mvvnl@gmail.com** (`santosh-mvvnl`).

---

## 🚀 Quick Setup on Any New Computer

When setting up Antigravity on a new desktop, laptop, or virtual machine, run **one** of the following commands in **PowerShell** (Windows) or **Terminal** (Linux/macOS).

### Option 1: Git Clone Method (Recommended — Enables Easy Updates)
Clones this repository directly into Antigravity's global configuration folder:

```powershell
git clone https://github.com/santosh-mvvnl/antigravity-rules.git "$HOME\.gemini\config\rules"
```

*For Linux / macOS:*
```bash
git clone https://github.com/santosh-mvvnl/antigravity-rules.git ~/.gemini/config/rules
```

---

### Option 2: Direct Single-File Download (Zero Git Dependency)
If Git is not configured or you prefer a direct file download without repository tracking, run this single PowerShell command:

```powershell
New-Item -ItemType Directory -Path "$HOME\.gemini\config\rules" -Force; Invoke-WebRequest -Uri "https://raw.githubusercontent.com/santosh-mvvnl/antigravity-rules/main/global.md" -OutFile "$HOME\.gemini\config\rules\global.md"
```

*For Linux / macOS:*
```bash
mkdir -p ~/.gemini/config/rules && curl -fsSL https://raw.githubusercontent.com/santosh-mvvnl/antigravity-rules/main/global.md -o ~/.gemini/config/rules/global.md
```

---

## 🔄 How to Pull the Latest Rules on Any Machine

Whenever you update `global.md` in this GitHub repository, update any machine with:

```powershell
cd "$HOME\.gemini\config\rules"
git pull
```

---

## 📁 Repository Structure
```text
antigravity-rules/
├── README.md        # This setup guide and reference manual
└── global.md        # The unified master rule specification (always_on)
```

---

## 📋 Summary of Enforced Standards in `global.md`

### Part 1: Universal Operational Rules
1. **Mandatory Confirmation Before Codebase Changes:**  
   The agent must ask for explicit user confirmation before creating, modifying, or deleting any file in the codebase.
2. **Automatic Git Add, Commit & Push:**  
   Immediately stages (`git add -A`), commits with a concise descriptive message, and pushes to remote whenever changes are applied.
3. **Mandatory 6-Section Structured Responses:**  
   Every response addressing user prompts or implementations must output:
   1. *Assumptions Made*
   2. *Root Cause of Issue(s)*
   3. *Corrective Measures Taken*
   4. *Commands Executed*
   5. *Important Functions, Packages, and Drivers Used*
   6. *Important Instructions for the User*
4. **Strict Zero Synthetic Data Policy (Pure Authentic Portal Data):**  
   Zero tolerance for mock, synthetic, fake, or formula-generated data across all layers, controllers, scrapers, and dashboards. 100% summary-to-list count parity must be preserved from authoritative source reports.
5. **Automatic Synchronization of Global Rules to `antigravity-rules` GitHub Repository:**  
   Whenever any rule is created, updated, or removed in `global.md`, it is immediately synchronized to the central GitHub repository (`https://github.com/santosh-mvvnl/antigravity-rules.git`) along with an updated `README.md`.

### Part 2: Global Development & Data Standards
6. **Summary Hyperlinks and Strict 1:1 Data Parity:**  
   Every numerical summary cell or KPI count must be clickable, downloading strictly that exact subset of records with 1:1 row count parity (excluding header).
7. **Contextual Dropdown Filters with Checkboxes Above Summaries (Excel AutoFilter Semantics):**  
   Dynamic multi-select dropdown filters featuring individual checkboxes immediately adjacent to each option in the list. By default, all options are checked (`value=True`) upon loading. Features a permanent top search input box with pure Microsoft Excel AutoFilter semantics: manual search selection with explicit Add-to-Filter branching (search results unchecked by default, isolating to selected search items when 'Add current selection' is unchecked, or merging with prior search results when checked), persistent pre-search base snapshot (`committed_base`) ensuring reliable multi-search accumulation, dynamic `(Select All)` checkbox when search is empty, full bidirectional & upstream cascading (selecting downstream entities like a Division automatically narrows upstream Circle, Zone, and DISCOM to only qualifying parents), and persistent user choice memory without push buttons inside dropdowns. Bulk selection is driven purely via master checkboxes with independent filter state isolation, reserving global reset exclusively for the dedicated "Reset All Filters" button.
8. **Indian Number Formatting:**  
   Standard `en-IN` comma grouping (`1,00,000`, `1,00,00,000`) across all user-facing displays without converting underlying numeric types.
9. **Avoid Hard-Coding & Build Generalized, Configurable Solutions:**  
   Modular, configuration-driven code with externalized settings and parameterized queries.
10. **Validation, Testing, and Regression Prevention:**  
    Mandatory 8-point checklist verifying count parity, filter consistency, boundary cases, and automated regression tests.
11. **Mandatory Working Procedure & Scope/Priority:**  
    Formal pre-modification inspection and post-implementation validation workflow across all projects.
