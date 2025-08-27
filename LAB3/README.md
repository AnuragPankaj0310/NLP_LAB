# README – Trie-Based Stemming and Frequency Analysis

## 1. Overview
This assignment has two main tasks:

1. **Trie-Based Stemming**  
   - Implement **prefix and suffix tries** to store words from `brown_nouns.txt`.  
   - Identify **stems** and **suffixes** for each word.  
   - Analyze which trie type is more effective for stemming.

2. **Frequency Distribution and Stop Word Removal**  
   - Create a **frequency distribution** of a tokenized dataset (Assignment-1).  
   - Plot the **most frequent 100 words**.  
   - Identify and remove **stop words** based on frequency thresholds.  
   - Plot frequency distributions after stop word removal for **three different thresholds**.

---

## 2. Task 1 – Trie-Based Stemming

### **Methodology**
- Store all words in a **prefix trie** and a **suffix trie**.  
- Each **node** in the trie keeps:
  - Children nodes  
  - Frequency count of words passing through the node  
- **Stem and Suffix Identification**:
  - Traverse each word in the trie.  
  - Node with **maximum branching** is treated as the **stem-suffix split point**.  
  - Stem = part before maximum branching, Suffix = remaining part.  
