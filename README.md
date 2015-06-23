# snowball

Old version of Snowball version of Porter stemmer for Lithuanian language is in the file `lithuanian.sbl`.

New version is in the file `conservative.sbl`.

The difference between the new and old versions is that the new one is less aggressive. This means that there should be fewer words that are overstemmed.

The new stemmer was created with search applications in mind. Therefore, nouns are considered as more important then adjectives, verbs, etc. This means that some suffixes, such as -ut- like in 'kalakutas', are left untouched during stemming. On the other hand, this leaves some adjectives understemmed, e.g. 'sveikutis -> sveikut'. There will always be trade-offs.
