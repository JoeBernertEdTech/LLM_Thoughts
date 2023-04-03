# LLM_Thoughts
A place to organise and share my writings on LLM use in the education context

LLM Hallucinations - Not What You Think

Since LLMs came to general attention, we have heard a lot about their tendency to “hallucinate” factual details while providing confident sounding responses.  Discussions about this phenomenon will often be accompanied with example screenshots side-by-side with real data and point out the inconsistencies. The inference that the LLM is not going to be useful for working with this or that particular kind of information is often drawn. I think this is the wrong way to view the phenomenon of LLM hallucination. 

The key observation is that an LLM is not a search engine. It’s not a database either. It is a reasoning engine; that is, by having seen many fragments of text it has learnt a series of conceptual relationships which it is able to use to make plausible sounding strings of text. When those strings of text deal with simple declarative facts that are well represented in the training data (e.g. What is the capital of France? A: Paris), the gap between plausible token generation and factual retrieval drops to zero. When the string completion demands data or facts the model simply doesn’t know, it will fall back on the concepts it does know in order to hallucinate something plausible. I contend that this a good thing. 

Suppose you had two students, and you planned to choose one to assist you with a research project about telecommunications in the 20th century United States. In order to determine which student would be more helpful, you might ask a question related to the proposed research to assess the student’s ability to reason about the kind of data you will be using. Suppose you ask “What were the census figures for the number of typists in the united states between 1930 and 2020?”

Student A answers: I don’t know. 

Student B answers: I’m not sure, but something like this possibly?

1930 - 80,000
1940 - 120,000
1950 - 190,000
1960 - 890,000
1970 - 1,900,500
1980 - 2,250,000
1990 - 1,900,000
2000 - 900,000
2010 - 250,000
2020 - 40,000

Which student are you inclined to take with you to the library? Student B already has a good idea of what the data they will be working with “looks like” - it’s reasonable to assume student B would have an easier time finding and manipulating the correct data. There are stronger guarantees too; the hallucinated data is not ludicrous on its faces we might expect Student B to reject the veracity of a table of supposed census data that said something like:

1930 - 300,000,000
1940 - 120
1950 - 190,000
1960 - 150,000,000
1970 - 1
1980 - 2,250,000
1990 - 1,900,000
2000 - 123,456
2010 - 250,000
2020 - 40,000

as being implausible. The ability to generate fake information up to some standard of plausibility is the same as the ability to find data and judge its likely veracity. This becomes important when we address the concept of tool-use by GPT like systems - the so-called “toolformer” model, which we will discuss in another post. For now it is enough to note that these hallucinations are the exact mechanism that allows GPT to reason about external data it is given access to by tools. 

A Side Note on Math: Think out loud i your head the words “Six times six is…”. Did you automatically complete the thought to “Six times six is thirty six”? Did you calculate the product (6 x 6) in your head, or did you complete it linguistically? I think most people do the latter. This is how GPT is with math, when using the language model by itself. It can do most few digit multiplications by linguistic completion, and then it starts to break up when there are more digits, as these products are a) less likely to have appeared verbatim in the training data, and b) the structure of the number field becomes more complex as the size increases so the model may have learned a set of heuristics for e.g. outputting correct answers to 3 digit multiplications it has never seen, but these heuristics do not extend to the 5 digit field etc. The importance of all this is to say if you were to hand both GPT and a human a calculator that occasionally gave the wrong results - the GPT would likely notice fist. A readout of (1296 * 1296 = 1678826) is as startling and obviously incorrect to the GPT as a readout of (6 x 6 = 29) is to the average person. 

