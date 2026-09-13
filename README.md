***WORDPIECE TOKENIZATION***

A from-scratch implementation of WordPiece Tokenization using Python. This project demonstrates how words are split into subword units, how WordPiece scores are calculated, how the best subword pair is merged, and how the final tokens are converted into token IDs.

**Overview**

WordPiece is a subword tokenization algorithm widely used in Natural Language Processing (NLP). Instead of representing every word as a single token, WordPiece can divide words into smaller subword units.

**For example:**

played → play + ##ed

The "##" prefix indicates that the subword is a continuation of the previous token.

This implementation demonstrates the basic WordPiece workflow from training data to final token IDs.

**Features**

- Training word frequency representation
- Initial character-level token splitting
- Token frequency calculation
- Pair frequency calculation
- WordPiece score calculation
- Best pair selection
- Subword pair merging
- Vocabulary creation
- New word tokenization
- Token-to-ID conversion
- Unknown word handling using "[UNK]"

**Technologies Used**

- Python
- Collections Counter
- Natural Language Processing (NLP) concepts

Project Workflow

Training Data
      ↓
Initial Splits
      ↓
Token Frequencies
      ↓
Pair Frequencies
      ↓
WordPiece Scores
      ↓
Best Pair Selection
      ↓
Merge Pair
      ↓
Vocabulary
      ↓
Tokenization
      ↓
Token IDs
      ↓
Unknown Word Handling

Training Data

The project uses a small sample vocabulary:

words = {
    "cat": 3,
    "cats": 2,
    "dog": 1
}

The values represent the frequency of each word in the training data.

Initial Splits

Each word is initially divided into character-level subwords:

cat  → c + ##a + ##t
cats → c + ##a + ##t + ##s
dog  → d + ##o + ##g

WordPiece Scoring

For each adjacent token pair, a WordPiece score is calculated using:

Score = Pair Frequency / (Frequency of First Token × Frequency of Second Token)

The pair with the highest score is selected for merging.

Pair Merging

The best-scoring pair is merged to create a new subword token.

For example:

d + ##o → do

The updated tokenization can then be used for further processing.

Tokenization

The tokenizer searches for the longest matching subword in the vocabulary.

Example:

Input:
dog

Output:
do + ##g

If a word cannot be completely represented using the available vocabulary, the tokenizer returns:

[UNK]

Token IDs

After tokenization, each token is mapped to a numerical ID.

Example:

Tokens:
['do', '##g']

Token IDs:
[8, 7]

Token IDs allow NLP models to process text as numerical data.

Unknown Word Handling

The implementation also tests an unknown word:

xyz → [UNK]

"[UNK]" represents an unknown token that is not available in the vocabulary.

Sample Output

========================================
        WORDPIECE TOKENIZER
========================================

Training words:
{'cat': 3, 'cats': 2, 'dog': 1}

Initial splits:
cat -> ['c', '##a', '##t']
cats -> ['c', '##a', '##t', '##s']
dog -> ['d', '##o', '##g']

Token frequencies:
c = 5
##a = 5
##t = 5
##s = 2
d = 1
##o = 1
##g = 1

Tokenization:
dog -> ['do', '##g']

Token IDs:
[8, 7]

Unknown word test:
xyz -> ['[UNK]']

WordPiece process completed!

Learning Outcomes

Through this project, the following concepts are demonstrated:

- Subword tokenization
- Vocabulary construction
- Token and pair frequencies
- WordPiece scoring
- Subword merging
- Greedy longest-match tokenization
- Token-to-ID conversion
- Unknown token handling

Applications

WordPiece Tokenization is useful in:

- Natural Language Processing
- Text Classification
- Sentiment Analysis
- Question Answering
- Language Models
- Transformer-based NLP systems

Project Structure

WordPiece-Tokenization/
│
├── wordpiece_tokenizer.py
└── README.md

How to Run

1. Clone the Repository

git clone <your-repository-link>

2. Open the Project

cd WordPiece-Tokenization

3. Run the Python File

python wordpiece_tokenizer.py

**Conclusion**

This project provides a simple from-scratch implementation of WordPiece Tokenization using Python. It demonstrates the complete basic process of calculating token and pair frequencies, selecting the best pair using WordPiece scores, merging subwords, tokenizing new words, and converting tokens into numerical IDs.

---

**Author**

Aswini.S

Computer Science with Artificial Intelligence

