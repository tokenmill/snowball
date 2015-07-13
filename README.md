# snowball

Old version of Snowball version of Porter stemmer for Lithuanian language is in the file `lithuanian.sbl`.

New version is in the file `conservative.sbl`.

The difference between the new and old versions is that the new one is less aggressive. This means that there should be fewer words that are overstemmed.

The new stemmer was created with search applications in mind. Therefore, nouns are considered as more important then adjectives, verbs, etc. This means that some suffixes, such as -ut- like in 'kalakutas', are left untouched during stemming. On the other hand, this leaves some adjectives understemmed, e.g. 'sveikutis -> sveikut'. There will always be trade-offs.


NOTE:

Current stemmer version uses length of the string to prevent overstemming. Stemmer created with `snowball`* program extends `org.tartarus.snowball.SnowballProgram` class and gets length of the `current` string using Java's `current.length()` call.

Whereas Lucene 4.10.1 implements `SnowballProgram` in such a way that attribute `current` is private, therefore `current.length()` doesn't compile for Lucene. Workaround is to substitute `current.length()` with `getCurrent().length()` on line 589.

* `snowball` program was downloaded from [here](http://snowball.tartarus.org/dist/snowball_code.tgz).
