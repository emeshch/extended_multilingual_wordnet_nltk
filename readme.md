

# How to use Extended Open Multilingual Wordnet via NLTK interface?

So, you found yourself in a situation when you need to browse Afrikaans WordNet. Or Cherokee, Azerbaijani, Old English or any other low-resource language from a list of 150 languages that are represented in EOMW –  [Extended Open Multilingual Wordnet](http://compling.hss.ntu.edu.sg/omw/summx.html). There is a simple online [search interface](http://compling.hss.ntu.edu.sg/omw/cgi-bin/wn-gridx.cgi?gridmode=gridx), but you are looking for a way to browse the wordnet via NLTK Wordnet Interface because a number of cool features are already implemented there:
* find synsets by word
* get semantically related synsets
* compute  various similarity measures for a pair of synsets.

NLTK WordNet Interface supports OMW – Open Multilingual Wordnet (http://compling.hss.ntu.edu.sg/omw/), but EOMW, being built automatically, is considered to be of lower confidence, and therefore is not currently supported (see https://github.com/nltk/nltk/issues/1611). Yet, there is a way.

1. Check that you've installed NLTK and downloaded Wordnet and OMW 'corpora' for NLTK:
```python
nltk.download('omw')
```

Find nltk_data/ directory with /corpora/omw/ and a subdirectory for all available languages in it.


2. Download EOMW (http://compling.hss.ntu.edu.sg/omw/summx.html) and locate the target language file. In case of Old English this would be /wikt/wn-wikt-ang.tab.


3. Create a dir for your language in /nltk_data/corpora/omw/ and put the file from EOMW in it. Thanks to a great stackoverflow answer (https://stackoverflow.com/a/45218884), we now know that a language dir/file name should be named according to the pattern:
/nltk_data/corpora/omw/xxx/wn-data-xxx.tab
where xxx may be, for example, the ISO-639 language code (ang for Old English).

4. Now you're good to go:
```python
>>> from nltk.corpus import wordnet as wn
>>> wn.synsets('wer',lang=('ang'))
[Synset('man.n.01')]
```






NLTK WordNet Interface (https://www.nltk.org/howto/wordnet.html)

Open Multilingual Wordnet (http://compling.hss.ntu.edu.sg/omw/)

Extended Open Multilingual Wordnet (http://compling.hss.ntu.edu.sg/omw/summx.html)


