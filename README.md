ark-tweet-nlp-python
====================

Simple Python wrapper around runTagger.sh of ark-tweet-nlp. It passes a list of tweets to runTagger.sh and parses the result into a list of lists of tuples, each tuple represents the (token, type, confidence).

Wraps up:

  * https://github.com/brendano/ark-tweet-nlp
  * http://www.ark.cs.cmu.edu/TweetNLP/

Usage:
   
    >>> import CMUTweetTagger
    >>> print CMUTweetTagger.runtagger_parse(['example tweet 1', 'example tweet 2'])
    >>> [[('example', 'N', 0.979), ('tweet', 'V', 0.7763), ('1', '$', 0.9916)], [('example', 'N', 0.979), ('tweet', 'V', 0.7713), ('2', '$', 0.5832)]]

Note, if you receive:

    >>> ValueError: Cannot find "./runTagger.sh"

Make sure you pass in the correct path to runTagger.sh, e.g. if this script is cloned into a subdirectory of ark-tweet-nlp then you may need to use:

    >>> print CMUTweetTagger.runtagger_parse(['example tweet 1', 'example tweet 2'], run_tagger_cmd="../runTagger.sh")
