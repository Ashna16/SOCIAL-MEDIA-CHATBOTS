# SOCIAL-MEDIA-CHATBOTS

Implementation:

1. Begin by importing our natural language toolkit.

We use NLTK (natural language toolkit) for 2 things:

•	breaking up sentences into words (tokenization): “have a nice day” tokenizes to a list of individual words: “have”, “a”, “nice”, “day”
•	reducing words to their stem (stemming): “have” stems to “hav” which allows it to be matched with “having” (same stem)
 There are various stemmers that we can use, we’ll use the Lancaster stemmer.

2.  Next step is to provide some training data. A few sentences that are associated with each intent (a “class”). If the user says “good day”, we want that to be the “greeting” intent.
You’ll notice that this is a list [] or dictionaries {}. Each dictionary has attributes: “class” and “sentence”. You could easily add additional attributes such as “responses” which could be what the chat-bot responds with when the intent is classified.
This is minimal data to show the inner workings of this algorithm, in a real use-case you might have hundreds of intents (classes), each with several training sentences.


3. The next step is to organize our data in structures that can be worked algorithmically.
Notice the “corpus” (an NLP term) a collection of all stemmed words. The stem of “make” is “mak” so that it matches the stems for “making”, as a simple example.
We’ve now organized our data into 2 dictionaries: corpus_words (each stemmed word and the # of occurances) class_words (each class and the list of stemmed words within it). Our algorithm will use these data structures to do its thing.

4. Our next step is to code our algorithm; our first version will treat each word with equal weight.
Notice that each word from the given sentence is tokenized, stemmed, and lower cased, this is consistent with the transforms we applied to the corpus data. In other words: our input data is transformed consistently with our training data.


5.We can significantly improve our algorithm by accounting for the commonality of each word. The word “is” should carry a lower weigh than the word “sandwich” in most cases, because it is more common.

And then Let’s try classifying the sentence “good day for us to have lunch?” again. The results are much better, because “day” and “have” are more common terms (in this corpus) they carry lower weight and help to distinguish the correct class.


6.Our last step is to abstract the algorithm so it can be used simply.


