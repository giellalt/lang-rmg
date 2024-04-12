# Noun inflection
This file contains the noun inflection for Traveller Romani.
The nouns inflect in number and definiteness

**TODO:** The lexica *m1 - m4* may be unified and their inflection 
differences handled in twolc. *f1, f2* and *n* have different suffixes
and should be kept.

## The lexicons

### Lexicons pointing to other lexicons

**LEXICON f1m2** split in two

**LEXICON f1m1** split  in two

**LEXICON f** goes to f2

**LEXICON pl** with no gender info, just gives *+N+Pl*

### Lexicons for masculine nouns

**LEXICON mx** for uninflected (for now)

**LEXICON m1**  now points to m2, let us test this

**LEXICON m1pl** pl only

**LEXICON m2** is now the sole masculine lexicon, with suffixes -en, -ar, -ane. The adjustments of m1, m3, m4 suffixes are being taken care of by morphophonology.

**LEXICON m3** now points to m2, let us test this

**LEXICON m4** now points to m2, let us test this

### Lexicons for feminine nouns

**LEXICON f1** is now the sole lexicon, let us test this, -a, -a2r, -ane suffixes, and the variation handled in the morphophonology

**LEXICON f2** now points to f1

### Lexicons for neuter nouns

**LEXICON n** is the sole n lexicon, suffixes -e, -Ø, -a, -ane.

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/affixes/nouns.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/morphology/affixes/nouns.lexc)</small>
