
# Traveller Romani morphological analyser                      
INTRODUCTION TO MORPHOLOGICAL ANALYSER OF Traveller Romani

# Definitions for **Multichar_Symbols** 

## Analysis symbols
The morphological analyses of wordforms for Traveller Romani
are presented in this system in terms of the following symbols.
(It is highly suggested to follow existing standards when adding new tags).

The parts-of-speech are:
* **+N +A +Adv +V** 
* **+Pron +CS +CC +Adp +Po +Pr +Interj +Pcle +Num** 

Gender: 
* **+Msc +Fem +Neu** 

The parts of speech are further split up into:
* **+Prop +Pers +Dem +Interr +Refl +Recipr +Rel +Indef** 

The Usage extents are marked using following tags:
* **+Err/Orth** 
* **+Use/-Spell** 

The nominals are inflected in the following (Case and) Number
* **+Sg +Pl** 
* **+Nom**  needed?
* **+Gen**  needed?
* **+Acc**  needed ?

The comparative forms are:
* **+Comp +Superl** 
Numerals are classified under:
* **+Attr +Card** 
* **+Ord** 
Verb moods are:
* **+Ind +Prs +Prt +Imprt**  hmm, no Ind marked...
Other verb forms are
* **+Inf +Neg +PrsPtc +PrfPtc** 

* **+ABBR +ACR** 
* **+Symbol**  = independent symbols in the text stream, like £, €, ©
Special symbols are classified with:
* **+CLB +PUNCT +LEFT +RIGHT** 
The verbs are syntactically split according to transitivity: (well, not yet)
* **+TV +IV** 
Special multiword units are analysed with:
* **+Multi** 
Non-dictionary words can be recognised with:
* **+Guess** 

Question and Focus particles:
* **+Qst +Foc** 

Semantics are classified with (so far the 4 first only)
* **+Sem/Mal** 
* **+Sem/Fem** 
* **+Sem/Sur** 
* **+Sem/Plc** 
* **+Sem/Org** 
* **+Sem/Obj** 
* **+Sem/Ani** 
* **+Sem/Hum** 
* **+Sem/Plant** 
* **+Sem/Group** 
* **+Sem/Time** 
* **+Sem/Txt** 
* **+Sem/Route** 
* **+Sem/Measr**  
* **+Sem/Wthr** 
* **+Sem/Build**  
* **+Sem/Edu** 
* **+Sem/Veh** 
* **+Sem/Clth** 

Derivations are classified under the morphophonetic form of the suffix, the
source and target part-of-speech.
* **+V→N +V→V +V→A** 
* **+Der/Adv** 
* **+Der/xxx** 

Morphophonology
To represent phonologic variations in word forms we use the following
symbols in the lexicon files: (still no such)

* a2 for gaje - gajer

## Flag diacritics
We have manually optimised the structure of our lexicon using following
flag diacritics to restrict morhpological combinatorics - only allow compounds
with verbs if the verb is further derived into a noun again:
|  @P.NeedNoun.ON@ | (Dis)allow compounds with verbs unless nominalised
|  @D.NeedNoun.ON@ | (Dis)allow compounds with verbs unless nominalised
|  @C.NeedNoun@ | (Dis)allow compounds with verbs unless nominalised

For languages that allow compounding, the following flag diacritics are needed
to control position-based compounding restrictions for nominals. Their use is
handled automatically if combined with +CmpN/xxx tags. If not used, they will
do no harm.
|  @P.CmpFrst.FALSE@ | Require that words tagged as such only appear first
|  @D.CmpPref.TRUE@ | Block such words from entering ENDLEX
|  @P.CmpPref.FALSE@ | Block these words from making further compounds
|  @D.CmpLast.TRUE@ | Block such words from entering R
|  @D.CmpNone.TRUE@ | Combines with the next tag to prohibit compounding
|  @U.CmpNone.FALSE@ | Combines with the prev tag to prohibit compounding
|  @P.CmpOnly.TRUE@ | Sets a flag to indicate that the word has passed R
|  @D.CmpOnly.FALSE@ | Disallow words coming directly from root.

Use the following flag diacritics to control downcasing of derived proper
nouns (e.g. Finnish Pariisi -> pariisilainen). See e.g. North Sámi for how to use
these flags. There exists a ready-made regex that will do the actual down-casing
given the proper use of these flags.
|  @U.Cap.Obl@ | Allowing downcasing of derived names: deatnulasj.
|  @U.Cap.Opt@ | Allowing downcasing of derived names: deatnulasj.

**LEXICON Root** is where it all begins.
The word forms in Romany language start from the lexeme roots of basic
word classes, or optionally from prefixes. The basic lexica are:
Adjectives ; 
Adverbs ; 
Conjunctions ; 
Interjections ; 
Nouns ; 
Numerals ; 
Prefixes ; 
Prepositions ; 
Pronouns ; 
Propernouns ; 
Punctuation ; 
Subjunctions ; 
Symbols ; 
Verbs ; 

* * *

<small>This (part of) documentation was generated from [src/fst/root.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/root.lexc)</small>

---
