# Digital Accessibility in LaTeX Documents  
## Quickstart Guide (Version 0.1)

**Author:** Kris Hollingsworth, PhD  

---

## Table of Contents
- Introduction
- Software Requirements
- Document Requirements
- Summary and Minimal Template
- Repository

---

## Introduction

### Federal Accessibility Requirements

Recent updates to federal accessibility regulations under **Title II of the ADA** require digital content produced by public institutions to meet **WCAG 2.1 Level AA** standards.

For academic environments, this means:

- Accessibility must be built-in, not retrofitted  
- Materials must support:
  - Proper document structure  
  - Logical reading order  
  - Alternative text for images  
  - Navigable tables  
  - Compatibility with assistive technologies  

Compliance Deadline: April 24, 2027 (Recently extended from the original 2026 deadline.)

---

## Software Requirements

- TeX Live 2025+
- LuaLaTeX compiler

---

## Document Requirements

### Automatically Tagging Your PDF

    \DocumentMetadata{
      tagging=on,
      pdfstandard=ua-2,
      lang=en-US,
      testphase={phase-III,math,table}
    }
    \documentclass[12pt,a4paper]{article}

    \usepackage[
      pdfauthor={Author Name},
      pdftitle={Document Title}
    ]{hyperref}

Note:
- \title{} and \author{} do not set PDF metadata  
- hyperref is required

---

### Heading Structure

    \section{}        %H1 Heading
    \subsection{}     %H2 Heading
    \subsubsection{}  %H3 Heading
    \paragraph{}      %H4 Heading
    \subparagraph{}   %H5 Heading

---

### Floating Elements
    \usepackage{float} %% Add to Preamble

    \begin{figure}[H]
    \caption{Insert Caption}
    \end{figure}
    \begin{table}[H]
    \caption{Insert Caption}
    \end{figure}
---

### Tables
    %% Sets first row as default for table header.
    \tagpdfsetup{table/header-rows={1}}

---

### Images and Alt Text
    %% Use built in key.
    \includegraphics{filename}[alt={Sample alternative text.}]
    \begin{tikzpicture}[alt={Sample alternative text.}]

---

## Summary

- Prioritize semantic structure
- Maintain reading order
- Test accessibility iteratively.
