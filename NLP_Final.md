# NLP Notes
---
## Important:


Total 04 Questions:
- NLP Processing Pipeline
- Text Pre-Processing in NLP with Programming Example
- Word Representation with its different aspects and types
- MCQs from above topics

---
### Table Of Contents:
- [🧠 NLP Pipeline – Step by Step](#nlp-pipeline--step-by-step)
- [Text Preprocessing in NLP - Easy Guide](#Text-Preprocessing-in-NLP---Easy-Guide)
---

# 📘 Introduction to Natural Language Processing (NLP)

Natural Language Processing (NLP) helps computers understand human language. While computers are great at working with numbers and structured data, understanding text and speech (which are unstructured) is hard for them. NLP bridges this gap, making it possible for machines to read, listen, and understand us like humans.

Let’s learn about NLP in simple words in this README.

---

## ✅ Why Do We Need NLP?

Every day, tons of text and speech are generated — from books and emails to videos and voice messages. To make sense of this data, machines need NLP.

NLP helps in:
- Reading and understanding large texts.
- Figuring out what people are saying in different ways.
- Solving confusing sentences like:
  
  **Example:** “The boy radiated fire-like vibes.”  
  Is this about his personality or something magical? NLP tries to figure that out.

---

## NLP Pipeline – Step by Step

To understand language, NLP breaks it down into small steps:

### 1. 📌 Sentence Segmentation
Break a big paragraph into smaller sentences.  
**Example:**  
**Input:** *San Pedro is a town. It has 16,444 people.*  
**Output:**  
- Sentence 1: San Pedro is a town.  
- Sentence 2: It has 16,444 people.

---

### 2. 🧩 Word Tokenization
Split each sentence into words (called tokens).  
**Input:** *San Pedro is a town.*  
**Output:** [‘San’, ‘Pedro’, ‘is’, ‘a’, ‘town’]

---

### 3. 🏷️ Parts of Speech (POS) Tagging
Label each word as a noun, verb, etc.  
**Input:** *San Pedro is a town.*  
**Output:**  
- ‘San Pedro’ → Noun  
- ‘is’ → Verb  
- ‘a’ → Article  
- ‘town’ → Noun

---

### 4. 🌱 Lemmatization
Change words to their base form.  
**Input:** *There are buffaloes in the field.*  
**Output:** *buffalo* (root word)

---

### 5. 🚫 Stop Word Removal
Remove common words like "a", "the", "and" that don’t add much meaning.

---

### 6. 🔗 Dependency Parsing
Understand how words are related to each other.  
**Input:** *San Pedro is an island in Belize.*  
**Output:**  
- ‘San Pedro’ → subject  
- ‘is’ → verb  
- ‘island’ → object

Also helps find noun phrases like:  
**“second-largest town”** from “The second-largest town in Belize”.

---

### 7. 🗺️ Named Entity Recognition (NER)
Find names of people, places, organizations, etc.  
**Input:** *San Pedro is a town in Belize.*  
**Output:**  
- San Pedro → Place  
- Belize → Country

---

### 8. 🔁 Coreference Resolution
Find words that refer to the same thing.  
**Input:** *San Pedro is a town. It has 16,444 people.*  
**Output:** *"It"* refers to *San Pedro*.

---

## 🧠 Semantics vs. Pragmatics

| Concept     | Meaning                                                                 |
|-------------|-------------------------------------------------------------------------|
| **Semantics** | Meaning of words and sentences (without context).                     |
| **Pragmatics** | Meaning based on context and situation (how we use language daily).  |

---

## ⚙️ Techniques Used in NLP

### 1. 🧾 Rule-Based Methods
- Use hand-written rules (e.g., “If word = ‘cat’, then it's a noun”). These involve manually created rules and heuristics to process language data. For example, defining patterns in language to extract meaning.

### 2. 🤖 Machine Learning & Deep Learning
- Learn patterns from lots of text.
- Use smart models like:
  - Decision Trees
  - Support Vector Machines
  - **Deep Learning**: RNNs, Transformers (like BERT, GPT)

---

## 🚀 Applications of NLP

1. 🎤 **Speech Recognition** – Convert voice to text (e.g., Siri, Alexa).
2. 🌍 **Language Translation** – Translate text between languages (e.g., Google Translate).
3. 💬 **Chatbots** – Talk to users (e.g., customer service bots).
4. ✂️ **Text Summarization** – Make long articles shorter.
5. 😊 **Sentiment Analysis** – Understand emotions (e.g., is a review happy or angry?).
6. 🔍 **Information Retrieval** – Improve search results using meaning, not just keywords.

---

## 📚 Conclusion

Natural Language Processing is helping computers understand how we talk and write. It breaks complex language into steps and uses smart methods to analyze, learn, and respond.

NLP is all around us — from Google Search to chatbots — and it's becoming more powerful every day.

---

Let me know if you’d like a visual version (with diagrams or flowcharts) or want to turn this into a presentation!

Sure! Here's a simplified and well-organized `README.md` version of your NLP tools classification in easy words:

---

# 📘 Natural Language Processing (NLP) Tools Classification

Natural Language Processing (NLP) is all about helping computers understand human language. There are many products and tools built using NLP. This document explains how we can group (classify) these tools and what they do.

---

## 🔹 1. Based on What They Do (Functionality)

### 🗣️ A. Conversational AI / Virtual Assistants  
Tools that can talk or chat with you and help with tasks.  
**Examples:**  
- **Siri (Apple)** – iPhone voice assistant  
- **Alexa (Amazon)** – Smart home voice helper  
- **Google Assistant** – Google voice assistant  
- **Cortana (Microsoft)** – Windows assistant (now discontinued)  
- **DeepSeek** – Smart chatbot with good memory  

---

### 📄 B. Text and Document Tools  
Used to check grammar, summarize, or understand documents.  
**Examples:**  
- **Grammarly** – Fixes grammar mistakes  
- **Hugging Face Transformers** – Open-source tools for developers  
- **DocuSign** – Understands and processes documents  

---

### 🌐 C. Language Translation Tools  
Used to change text from one language to another.  
**Examples:**  
- **Google Translate** – Supports 100+ languages  
- **DeepL** – Known for better quality translations  
- **Microsoft Translator** – Works with Microsoft tools  

---

### 🔊 D. Speech and Text Tools  
Convert speech to text or text to voice.  
**Examples:**  
- **Amazon Polly** – Turns text into lifelike voice  
- **Google Speech-to-Text** – Turns speech into text  
- **IBM Watson Text-to-Speech** – Converts text to spoken voice  

---

### ❓ E. Q&A and Information Search  
Answers your questions or searches for info.  
**Examples:**  
- **ChatGPT (OpenAI)** – Smart chatbot for answers  
- **Perplexity AI** – Accurate question answering  
- **WolframAlpha** – Solves math and gives detailed facts  

---

## 🔹 2. Based on Where They're Used (Application)

### 🏠 A. Consumer Use  
For normal people using phones or smart devices.  
**Examples:** Siri, Alexa, Google Assistant  

### 🏢 B. Business Use  
For companies to analyze data or automate tasks.  
**Examples:** IBM Watson NLP, AWS Comprehend, Azure Text Analytics  

### 🧪 C. Research & Development  
Used by developers and researchers to build new models.  
**Examples:** Hugging Face, OpenAI GPT API, AlphaCode  

### 🏥 D. Medical Use  
Helps doctors by understanding medical text.  
**Examples:** IBM Watson Health, Google Health AI  

---

## 🔹 3. Based on Interaction Type

### 🎙️ A. Voice-based  
You talk to it.  
**Examples:** Alexa, Siri, Google Assistant  

### 📝 B. Text-based  
You type to it.  
**Examples:** Grammarly, ChatGPT  

### 🎛️ C. Multimodal  
Works with both voice and text.  
**Examples:** Google Dialogflow, Microsoft Azure AI  

---

## 🔹 4. Based on Platform

### 📱 A. In Smart Devices  
Built into phones and gadgets.  
**Examples:** Siri in iPhone, Alexa in Echo  

### 💼 B. In Business Software  
Used in office or work apps.  
**Examples:** Cortana in Windows, IBM Watson in enterprise  

### 🧩 C. As APIs/SDKs for Developers  
Developers can use them in their own apps.  
**Examples:** OpenAI API, Google Cloud NLP API  

# NLP Tasks & Tools

### 🏷️ Text Classification  
- **Sentiment Analysis:** Tells if a review is good or bad  
- **Topic Classification:** Groups text by topic (sports, news)  
- **Summarization:** Makes text shorter  
- **POS Tagging:** Shows grammar role (noun, verb)  
- **Syntactic Analysis:** Checks sentence structure  

---

### 📍 Information Extraction  
- **NER:** Finds names of people, places  
- **IE:** Pulls out dates, phone numbers  
- **QA:** Answers questions from documents  

---

### ✍️ Text Generation  
- **Translation:** Language conversion (e.g., English ↔ Urdu)  
- **Chatbots:** Helps customers on websites  
- **Text Creation:** Writes articles, stories  
- **Speech Recognition:** Converts speech to text  

---

## 🔹 NLP Libraries for Developers

- **spaCy:** Fast library for NLP  
- **NLTK:** Classic Python toolkit  
- **Textacy:** Built on top of spaCy for analysis  

---

## 🔹 Tool Comparison

| Tool/Product           | Strengths                                   | Weaknesses                                  |
|------------------------|---------------------------------------------|----------------------------------------------|
| **ChatGPT** (OpenAI)   | Great for writing, answering, conversations | Needs strong computer power, can be wrong    |
| **Google BERT**        | Understands text deeply                     | Not good for writing/generating              |
| **IBM Watson NLP**     | Many features, business ready               | Expensive, setup is hard                     |
| **AWS Comprehend**     | Works well with AWS, handles big data       | May not fit small/unique needs               |
| **Azure Text Analytics** | Easy to use in Azure, works fast          | May not support all languages equally        |

---

## 🔹 Voice Assistant Comparison

| Feature              | Siri       | Alexa        | DeepSeek      |
|----------------------|------------|--------------|---------------|
| Voice Commands        | ✅         | ✅           | ✅            |
| Works in Devices      | Apple only | Many devices | Not confirmed |
| Personalization       | ✅         | Limited      | ✅            |
| Third-party Skills    | Limited    | Many         | Unknown       |
| Conversational Skills | Basic      | Advanced     | Advanced      |

## 📌 Conclusion

NLP tools are everywhere – in your phone, your browser, and even in hospitals and businesses. They help understand, generate, translate, and respond to human language in smart ways.

> **Whether you're a student, developer, or just curious — understanding these categories will help you know how NLP is shaping the future of tech!**

---

Let me know if you'd like this as a downloadable file or want it in PDF format too.

# 🧠 NLP Tools: Open-Source Libraries & Commercial Platforms

This document gives a simple overview of **popular NLP tools**, both **open-source** and **commercial cloud-based services**, used for processing and understanding human language.

---

## 📚 Open-Source NLP Libraries & Frameworks

These tools are **free** to use and are mostly used by developers, researchers, and students.

### 🔹 Python-Based Tools

| Library | Description |
|--------|-------------|
| **spaCy** | Fast and great for real-world projects. Used in production apps. |
| **NLTK (Natural Language Toolkit)** | Good for learning NLP. Covers many basic and advanced tasks. |
| **Gensim** | Best for topic modeling and comparing documents. |
| **TextBlob** | Very easy to use. Good for tasks like sentiment analysis and part-of-speech tagging. |
| **Hugging Face Transformers** | Powerful! Lets you use pre-trained models like BERT, GPT, and more. Great for text generation and understanding. |

---

### 🔹 Java-Based Tools

| Library | Description |
|--------|-------------|
| **Stanford CoreNLP** | A complete toolkit that handles many NLP tasks like parsing, NER, etc. |
| **OpenNLP** | Another good Java library for basic NLP features like sentence detection, POS tagging, and more. |

---

## ☁️ Commercial NLP Platforms & Services

These are cloud-based services that offer NLP features without needing to build your own models.

### 🔸 Cloud-Based NLP APIs

| Platform | Description |
|----------|-------------|
| **Google Cloud Natural Language API** | Detects sentiment, entities, syntax. Easy to use with Google Cloud. |
| **Amazon Comprehend** | Provides NLP features like entity recognition and sentiment detection. Works well with other AWS tools. |
| **IBM Watson Natural Language Understanding** | A full-featured NLP service for businesses. Handles emotion, categories, and more. |
| **Microsoft Azure Text Analytics** | Part of Azure services. Supports key phrase extraction, language detection, etc. |

---

### 🔸 Other NLP Platforms

| Platform | Description |
|----------|-------------|
| **MonkeyLearn** | Lets you build custom NLP models (like no-code for NLP). |
| **Aylien** | Good for analyzing large amounts of text data (e.g., news). |
| **Rasa** | Open-source tool to build smart chatbots and virtual assistants. |
| **Eden AI** | One API to access different NLP providers (like a marketplace for NLP services). |

---

## 📝 Note

This list is **not complete**, but it gives a good starting point. The **best NLP tool** depends on:

- Your project’s goal (e.g., chatbot, translation, text summarization)
- Your skills (Python, Java, etc.)
- Whether you want free or paid tools
- How much data you’re working with

---
Sure! Here's your content rewritten in **easy-to-understand language** and formatted as a `README.md` file:

---

# Text Preprocessing in NLP - Easy Guide

Natural Language Processing (NLP) is used in many apps like chatbots, translations, and sentiment analysis. But before using text in these apps, we need to **clean and prepare the text**. This process is called **text preprocessing**.

Good preprocessing helps models work better and faster. This README explains all the important steps in a simple way.

---

## 📚 Table of Contents
- [Why Text Preprocessing is Important?](#why-text-preprocessing-is-important)
- [Text Preprocessing Techniques](#text-preprocessing-techniques)
  - [Regular Expressions](#regular-expressions)
  - [Tokenization](#tokenization)
  - [Lemmatization and Stemming](#lemmatization-and-stemming)
  - [Parts of Speech (POS) Tagging](#parts-of-speech-pos-tagging)
- [Example: Step-by-Step Text Preprocessing](#example-step-by-step-text-preprocessing)
- [Extra Concepts](#extra-concepts)
  - [Handling Contractions](#handling-contractions)
  - [Handling Emojis and Emoticons](#handling-emojis-and-emoticons)
  - [Spell Checking](#spell-checking)

---

## ❓ Why Text Preprocessing is Important?

Real-world text is messy. It may contain:
- Typos
- Slang
- Short forms (like "can't")
- Irrelevant or noisy words

**Text preprocessing helps to:**
- 🧼 Clean the text
- 🚀 Improve model performance
- ⚡ Make processing faster

---

## ⚙️ Text Preprocessing Techniques

### 🔍 Regular Expressions
Used for finding patterns in text.
- Example: Find all emails or remove special characters.

### ✂️ Tokenization
Breaks the text into smaller parts:
- **Words**: "I love NLP" → ["I", "love", "NLP"]
- **Sentences**: "I love NLP. It's fun." → ["I love NLP.", "It's fun."]

### 🌱 Lemmatization and Stemming
Both reduce words to their root form.

| Stemming | Lemmatization |
|----------|---------------|
| Cuts off endings | Finds real word root |
| "playing" → "play" | "better" → "good" |

**Stemmers:** Porter, Lovins, Krovetz, etc.

### 🧠 Parts of Speech (POS) Tagging
Labels each word:
- "I eat apples" → `I/Pronoun eat/Verb apples/Noun`

---

## 🧪 Example: Step-by-Step Text Preprocessing

You can try these steps using Python in **Google Colab**, **Jupyter**, or any Python IDE.

### 1️⃣ Text Cleaning

```python
import re, string
from bs4 import BeautifulSoup

def clean_text(text):
    text = text.lower()
    text = re.sub(r'\d+', '', text)
    text = text.translate(str.maketrans('', '', string.punctuation))
    text = re.sub(r'\W', ' ', text)
    text = BeautifulSoup(text, "html.parser").get_text()
    return text
```

```python
corpus = [
    "I can't wait for the new season of my favorite show!",
    "The COVID-19 pandemic has affected millions of people worldwide.",
    "U.S. stocks fell on Friday after news of rising inflation.",
    "<html><body>Welcome to the website!</body></html>",
    "Python is a great programming language!!! 😃"
]

cleaned = [clean_text(doc) for doc in corpus]
print(cleaned)
```

---

### 2️⃣ Tokenization

```python
from nltk.tokenize import word_tokenize
import nltk
nltk.download('punkt')

tokens = [word_tokenize(doc) for doc in cleaned]
print(tokens)
```

---

### 3️⃣ Stop Words Removal

```python
from nltk.corpus import stopwords
nltk.download('stopwords')

stop_words = set(stopwords.words('english'))
filtered = [[word for word in doc if word not in stop_words] for doc in tokens]
print(filtered)
```

---

### 4️⃣ Stemming and Lemmatization

```python
from nltk.stem import PorterStemmer, WordNetLemmatizer
nltk.download('wordnet')

stemmer = PorterStemmer()
lemmatizer = WordNetLemmatizer()

stemmed = [[stemmer.stem(word) for word in doc] for doc in filtered]
lemmatized = [[lemmatizer.lemmatize(word) for word in doc] for doc in filtered]

print("Stemmed:", stemmed)
print("Lemmatized:", lemmatized)
```

---

## ➕ Extra Concepts

### 5️⃣ Handling Contractions

```python
import contractions

expanded = [contractions.fix(doc) for doc in cleaned]
print(expanded)
```
> Example: `"can't"` → `"cannot"`

---

### 6️⃣ Handling Emojis and Emoticons

```python
import emoji

emoji_text = [emoji.demojize(doc) for doc in cleaned]
print(emoji_text)
```

#### Emoticon vs Emoji:
| Emoticon | Emoji |
|----------|-------|
| Made with keyboard symbols like `:)` | Small icons like 😃 |
| Text-based | Image-based |

---

### 7️⃣ Spell Checking

```python
from spellchecker import SpellChecker

spell = SpellChecker()
corrected = [[spell.correction(word) for word in doc] for doc in tokens]
print(corrected)
```

> Corrects common typos like `fridge` → `Friday` (sometimes may be wrong!)

---

## ✅ Final Output
After applying all these steps, your text data is:
- Clean ✅
- Simple ✅
- Ready for NLP Models ✅

---

## 📎 Sources
- [GeeksForGeeks: Text Preprocessing in NLP](https://www.geeksforgeeks.org/text-preprocessing-for-nlp-tasks/)
- Google Generative AI
- [Google Colab](https://colab.research.google.com/)

---

Let me know if you want this saved as a downloadable file too!
---
***
# Topics For Final 

# Word Processing:
## Word Representations or Word Embedding in Natural Language Processing (NLP)

Here's a detailed explanation of **each heading** and subheading in the document you've shared on **Word Representations or Word Embeddings in NLP**:

---

### 🔹 **Word Representations or Word Embedding in Natural Language Processing (NLP)**

**Main Topic Overview**:
This heading introduces the central idea: how words are represented as numbers (vectors) in NLP, which allows machines to understand and work with human language in a meaningful way.

---

### 🔸 **Key aspects of Word Embeddings**

These are the essential characteristics and benefits of using word embeddings.

#### ✅ **Numerical Representation**

* Words are converted into numbers (vectors), making them usable for machine learning models.
* This is foundational since machines don't "understand" text like humans.

#### ✅ **Semantic and Syntactic Information**

* Embeddings capture **semantic** (meaning-based) and **syntactic** (grammar-based) relationships.
* Example: "walk" and "walked" are related in syntax and meaning.

#### ✅ **Clustering of Similar Words**

* Words with similar meanings are grouped close together in the embedding space.
* Useful for similarity detection and language understanding.

#### ✅ **Applications**

* Embeddings are used in:

  * **Sentiment Analysis**
  * **Text Classification**
  * **Machine Translation**
  * And more NLP tasks.

---

### 🔸 **Popular Embedding Methods**

#### 🧠 **Word2Vec**

* A deep learning method for generating word vectors using context-based prediction.

##### 📍 **CBOW (Continuous Bag of Words)**

* Predicts a target word based on its context (surrounding words).

##### 📍 **Skip-gram**

* Predicts the context given a target word (opposite of CBOW).

---

### 🔸 **Example**

A semantic analogy:

* `"king" - "man" + "woman" ≈ "queen"`
  Shows how vector math can reflect real-world relationships.

---

### 🔸 **What are Word Representations?**

* Definition of the core concept: converting words into numbers so machines can process them.

---

### 🔸 **Why Do We Need Them?**

Explains the **motivation** behind using embeddings:

* Machines understand only numbers.
* Word embeddings bridge the gap between text and numerical data processing.

---

### 🔸 **Types of Word Representations**

#### 1. **One-Hot Encoding**

* Each word is a sparse vector with a single `1`.
* Disadvantage: no relationship between words is captured.

#### 2. **Distributed Representations (Word Embeddings)**

Dense, meaningful vectors capturing similarity.

##### a. **Word2Vec**

* Learns from the context of words.
* Famous for vector arithmetic showing meaning.

##### b. **GloVe (Global Vectors)**

* Uses global co-occurrence statistics for learning word meanings.

##### c. **FastText**

* Enhances Word2Vec by breaking words into subwords (n-grams).
* Good for handling rare/morphological variations.

#### 3. **Contextual Embeddings (Dynamic representations)**

These embeddings **change** based on the sentence.

##### a. **ELMo**

* Embedding changes depending on full sentence.
* Example: “bank” in different contexts gets different vectors.

##### b. **BERT (and Transformers)**

* Deep models using attention to generate **context-aware embeddings**.
* State-of-the-art in NLP.

---

### 🔸 **Summary Table**

Comparison of different embedding types:

| Method   | Type    | Context-Aware? | Sparse or Dense | Famous For                         |
| -------- | ------- | -------------- | --------------- | ---------------------------------- |
| One-Hot  | Basic   | ❌              | Sparse          | Simplicity                         |
| Word2Vec | Static  | ❌              | Dense           | Vector math with meaning           |
| GloVe    | Static  | ❌              | Dense           | Global co-occurrence               |
| FastText | Static  | ❌              | Dense           | Subword info (handles rare words)  |
| ELMo     | Dynamic | ✅              | Dense           | Contextualized embeddings          |
| BERT     | Dynamic | ✅              | Dense           | SOTA (state-of-the-art) embeddings |

---

### 🔸 **1. Visual Example — What Do Word Embeddings "Look" Like?**

Describes how similar words are close in vector space.

* Uses a **2D visualization** (from a high-dimensional space) to show relationships like:

  ```
  king —— queen
   |         |
  man —— woman
  ```

---

### 🔸 **Intuition**

* Embeddings like Word2Vec/GloVe place similar words near each other in a dense space.
* PCA or t-SNE can be used to visualize these vectors.

---

### 🔸 **2. Code Snippets — Generating Embeddings**

Shows **real Python code** to generate embeddings using different models.

#### a. **Word2Vec (gensim)**

* Creates a model from sample data and finds similar words.

#### b. **GloVe (via spaCy)**

* Loads pre-trained GloVe vectors and checks similarity.

#### c. **BERT (transformers library)**

* Demonstrates how to tokenize and get contextual embeddings using BERT.
* Shows that each word gets a unique vector **based on context**.

---

### 🔸 **3. Comparison Example — Same Word, Different Representations**

#### Sentence 1:

> "He went to the bank to deposit money."

#### Sentence 2:

> "She sat by the river bank and watched the water."

✅ **With Word2Vec/GloVe**:

* "bank" has the **same** vector in both sentences (not context-aware).

✅ **With BERT**:

* "bank" has **different** vectors depending on the meaning in context.

---

### 🔸 **Final Thought**

Analogy of embedding types as **human-like behavior**:

* **One-Hot**: People wear name tags but don’t know anyone.
* **Word2Vec/GloVe**: People know their friends but don’t change behavior.
* **BERT/ELMo**: People adapt their behavior based on the environment and conversation.

---

### 🔸 **Visualization of Word2Vec Clustering**

Describes how embeddings cluster similar words like:

* `"king"` and `"queen"`
* `"paris"` and `"france"`

---

### 🔸 **Contextual Comparison with BERT (Theoretical Output)**

Explains what a **contextual comparison with BERT** would look like.

* Tokenizes two sentences.
* Gets 768-dimensional embeddings for each word.
* Measures **cosine similarity** between different contexts of "bank".

  * Lower similarity = different meanings understood.

---

### 🔸 **Summary Table (Again)**

Reiterates comparison of **Word2Vec vs BERT** for the word "bank":

| Model    | Word | Same Vector? | Context-Aware? | Result              |
| -------- | ---- | ------------ | -------------- | ------------------- |
| Word2Vec | bank | ✅            | ❌              | Always same         |
| BERT     | bank | ❌            | ✅              | Varies with context |

---

### 🔸 **BERT Contextual Embedding Comparison Script**

Python script to:

* Load BERT
* Tokenize two example sentences
* Extract embeddings for "bank"
* Compare them using cosine similarity

## 🐍 Simple Python Code Examples

✅ Example 1: Word2Vec with Gensim
```python
from gensim.models import Word2Vec

# Tiny example corpus
sentences = [["king", "queen", "man", "woman"]]

# Train model
model = Word2Vec(sentences, vector_size=50, window=2, min_count=1, sg=1)

# Get vector for "king"
print("Vector for 'king':", model.wv['king'])

# Find similar words
print("Most similar to 'king':", model.wv.most_similar('king'))
```

✅ Example 2: GloVe with spaCy

```python
import spacy

# Load medium English model (with GloVe vectors)
nlp = spacy.load("en_core_web_md")

word1 = nlp("king")
word2 = nlp("queen")

print("Similarity:", word1.similarity(word2))  # Closer to 1 = more similar

```

✅ Example 3: BERT (Contextual Embedding)
```python
from transformers import BertTokenizer, BertModel
import torch

# Load pre-trained BERT
tokenizer = BertTokenizer.from_pretrained("bert-base-uncased")
model = BertModel.from_pretrained("bert-base-uncased")

# Example sentence
sentence = "The river bank was flooded."

# Get token embeddings
inputs = tokenizer(sentence, return_tensors="pt")
outputs = model(**inputs)
embeddings = outputs.last_hidden_state

print("Shape:", embeddings.shape)  # (1, sequence_length, 768)


```


It shows that:

* Even though the same word ("bank") is used, BERT gives **different** vectors in different contexts.

---

If you'd like, I can turn this into a printable summary sheet or presentation as well — just let me know!
