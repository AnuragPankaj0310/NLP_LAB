# README  

## 1. Overview  
- This project implements **statistical language models** using n-grams.  
- Based on **tokenized Hindi news articles (Assignment-1)**.  
- Four models are built: unigram, bigram, trigram, and quadrigram.  
- Three smoothing techniques are applied.  
- Sentence probabilities are computed for **1000 random sentences**.  

---

## 2. Tasks Implemented  

### **Task 1: Build 4 N-Gram Models**  
- **Unigram** → frequency of single words.  
- **Bigram** → frequency of consecutive word pairs.  
- **Trigram** → frequency of 3 consecutive words.  
- **Quadrigram** → frequency of 4 consecutive words.  
- Built using `collections.Counter` on the tokenized corpus.  

### **Task 2: Apply Smoothing Techniques**  
- To handle **zero probabilities** for unseen n-grams:  

  - **Add-One Smoothing (Laplace):**  
    \[
    P(w_i | context) = \frac{\text{count}(ngram) + 1}{\text{count}(context) + V}
    \]  

  - **Add-K Smoothing (k = 0.6):**  
    \[
    P(w_i | context) = \frac{\text{count}(ngram) + k}{\text{count}(context) + kV}
    \]  

  - **Token-Type Smoothing:**  
    \[
    P(w_i | context) = \frac{\text{count}(ngram) + V}{\text{count}(context) + V^2}
    \]  
    ⚠️ May not sum to 1 → not a valid probability distribution.  

- `save_ngram_probs()` saves top N n-grams with all smoothing probabilities into separate `.csv` files.  

### **Task 3: Sentence Probability Computation**  
- 1000 random sentences extracted.  
- For each sentence:  
  - Split into tokens.  
  - Compute **log probability** under each model (uni → quadri).  
  - Use each smoothing scheme (Add-One, Add-K, Token-Type).  
  - **Unseen n-grams fallback:** probability = `1e-12`.  
- Results saved in `output.csv` as:  
