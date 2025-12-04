# Elsevier LaTeX Bibliography Style Files

## 📦 Repository Overview

This repository provides two essential Elsevier bibliography style (`.bst`) files that are required for formatting references in Elsevier journal LaTeX templates:

- **`cas-model2-names.bst`** - The newer CAS template style
- **`model1-num-names.bst`** - The classic elsarticle style

## ❓ Why This Repository Exists

Elsevier's official LaTeX templates have an inconsistency: they reference both `.bst` files but only include one.

**The Problem:**

- ✅ `cas-model2-names.bst` is included in templates
- ❌ `model1-num-names.bst` is referenced but **not included**

When users try to use the missing style:

```
\bibliographystyle{model1-num-names}  % ← Error: File not found!
\bibliographystyle{cas-model2-names}  % ← Works fine
```

This repository solves this problem by providing both files.

## 🔍 Style Comparison

### **`cas-model2-names.bst`** (Newer CAS Style)

**Format Example:**

```
Huang, B., Smith, A., 2024. Example Article. Journal Name 10, 100–110. 
https://doi.org/10.1016/j.example.2024.100110
```

**Features:**

- ✅ Sorted by author and year
- ✅ Author format: "Last name, First initial"
- ✅ Year appears next to authors
- ✅ Displays DOI/URL/arXiv/PubMed links
- ✅ Default in newer CAS templates

### **`model1-num-names.bst`** (Classic elsarticle Style)

**Format Example:**

```
[1] B. Huang, A. Smith, Journal Name 10 (2024) 100–110.
```

**Features:**

- ✅ References in citation order (unsorted)
- ✅ Author format: "Initials + Last name"
- ✅ Year inside volume: `10(2024)`
- ❌ DOI/URL often not displayed
- ❌ Missing from most templates

## 🎯 Choosing the Right Style

| Use Case | Recommended Style |
| --- | --- |
| CAS template (`cas-sc`, `cas-dc`) | `cas-model2-names.bst` |
| Want sorted references + DOI support | `cas-model2-names.bst` |
| Classic elsarticle format | `model1-num-names.bst` |
| References in citation order | `model1-num-names.bst` |
| Older Elsevier Model 1 papers | `model1-num-names.bst` |

## 📥 Installation & Usage

### **Step 1: Download Files**

Download both `.bst` files from this repository.

### **Step 2: Place Files**

Copy the files to either:

- Your LaTeX project folder (recommended for sharing)
- Your system's LaTeX directory (for all projects)

**Project Folder Structure:**

```
your-paper/
├── main.tex
├── references.bib
├── cas-model2-names.bst    ← Add these
└── model1-num-names.bst    ← Add these
```

### **Step 3: Select Style in LaTeX**

```
% For CAS Model 2 (newer style)
\bibliographystyle{cas-model2-names}

% For Model 1 (classic style)  
\bibliographystyle{model1-num-names}
```

### **Step 4: Complete Example**

```
\documentclass[a4paper,fleqn]{cas-sc}  % CAS template
\usepackage[numbers]{natbib}

% Choose your style
\bibliographystyle{cas-model2-names}

\begin{document}

Here is a citation \cite{example2024}.

% Bibliography section
\bibliography{references}  % Your .bib file

\end{document}
```

## 🎯 Repository Purpose

This repository was created to:

1. **Provide the missing file** - Supply `model1-num-names.bst` that Elsevier templates reference but exclude
2. **Enable choice** - Allow users to select between both official Elsevier bibliography styles
3. **Solve errors** - Help students and researchers avoid the frustrating "missing .bst file" error
4. **Simplify workflows** - Make it easier to format references correctly for Elsevier journals
