# Adversarial Safety Data for Multilingual Conversational AI

## Overview
Conversational AI systems are vulnerable to adversarial, dialectal, and code-switched language that can bypass safety detection and evaluation pipelines.  
This repository contains multilingual adversarial datasets, linguistic taxonomies, and evaluation artifacts designed to stress-test and improve the safety, robustness, and reliability of conversational AI systems across speech and text modalities.

The initial focus is on Arabic (MSA and dialects), with particular attention to linguistic phenomena that are underrepresented in English-centric safety datasets, such as dialect variation, code-switching, orthographic variation, and Unicode-based obfuscation.

---

## Problem Statement
Safety evaluation and red-teaming for conversational AI often fails in multilingual settings due to:
- Dialectal variation and non-standard spellings
- Code-switching between languages (e.g., Arabic–English)
- Orthographic and Unicode-based obfuscation
- Cultural euphemisms and indirect harmful language

These failure modes reduce the effectiveness of automated safety systems and human evaluation pipelines.  
This project addresses these gaps by providing structured adversarial data and evaluation tooling grounded in linguistic analysis.

---

## Project Goals
- Build adversarial safety datasets for multilingual conversational AI
- Capture linguistically motivated attack patterns and evasion strategies
- Support model evaluation across ASR and NLG components
- Provide clear safety taxonomies and evaluation guidelines
- Enable reproducible evaluation through validation and normalization scripts

---

## Dataset Scope
- **Languages:** Arabic (MSA & dialects), with planned expansion to English and mixed AR/EN content
- **Modalities:** Text (with ASR-derived text considered where relevant)
- **Domains:** Conversational assistants, content moderation, safety evaluation
- **Annotation Focus:** Expected safety behavior rather than surface toxicity alone

---

## Dataset Structure
Adversarial examples are stored in JSONL format with the following core fields:

```json
{
  "id": "ar_adv_001",
  "language": "ar",
  "language_variant": "msa | dialect | mixed",
  "task": "assistant_reply | chat | moderation",
  "input_text": "...",
  "attack_type": "obfuscation | code_switching | euphemism | dialect | unicode_trick",
  "safety_category": "harassment | hate | self_harm | fraud | sexual | extremism",
  "expected_behavior": "allow | refuse | safe_complete",
  "rationale": "Explanation of expected model behavior",
  "notes": "Linguistic or cultural context"
}