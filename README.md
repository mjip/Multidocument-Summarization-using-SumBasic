# Multidocument Summarization using SumBasic
Multidocument summarization using the SumBasic implementation, with three variations to give varied results. Uses Python3 and nltk.

sumbasic.py implements the algorithm from the paper: 
Ani Nenkova and Lucy Vanderwende. The Impact of Frequency on Summarization. Microsoft Research,
Redmond, Washington, Tech. Rep. MSR-TR-2005-101. 2005. <https://www.cs.bgu.ac.il/~elhadad/nlp09/sumbasic.pdf>

The variations also implemented were:
1. orig: The original version, including the non-redundancy update of the word scores.
2. best_avg: A version of the system that picks the sentence that has the highest average probability
in Step 2, skipping Step 3.
3. simplified: A simplified version of the system that holds the word scores constant and does not
incorporate the non-redundancy update.
4. leading, which takes the leading sentences of one of the articles, up until the word length limit is reached.

Each cluster of testing articles is stored in the docs/ folder. Each file follows docA-B.txt convention, where A is an
positive integer corresponding to the cluster number, and B is another positive integer corresponding to
the article number within that cluster.

## Usage
`python3 sumbasic.py <method_name> <file_n>*` where <method_name> is one of orig, best_avg, simplified, or leading, and <file_n>* 
is a regex expression of the file path of the cluster, e.g. `docs/doc1-*.txt`.
