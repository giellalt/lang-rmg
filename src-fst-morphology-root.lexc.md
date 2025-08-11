
# Traveller Romani morphological analyser                      
INTRODUCTION TO MORPHOLOGICAL ANALYSER OF Traveller Romani

# Definitions for **Multichar_Symbols** 

## Analysis symbols
The morphological analyses of wordforms for Traveller Romani
are presented in this system in terms of the following symbols.
(It is highly suggested to follow existing standards when adding new tags).

The parts-of-speech are:
* **+N +A +Adv +V** 
* **+IM** infinitive marker
* **+Pron +CS +CC +Adp +Po +Pr +Interj +Pcle +Num** 

Gender: 
* **+Msc +Fem +Neu** 

The parts of speech are further split up into:
* **+Prop +Pers +Dem +Interr +Refl +Recipr +Rel +Indef** 

The nominals are inflected in the following (Case and) Number
* **+Sg +Pl** 
* **+Nom**  needed?
* **+Gen**  needed?
* **+Acc**  needed ?
* **+Def**

The comparative forms are:

* **+Pos**
* **+Comp**
* **+Superl** 

Numerals are classified under:
* **+Attr +Card** 
* **+Ord** 
Verb moods are:
* **+Ind +Prs +Prt +Imprt**  hmm, no Ind marked...
* **+Imp** (fix Imp / Imprt)

Other verb forms are
* **+Inf +Neg** 
* **+PrsPtc** TODO fix Ptc vs. Prt
* **+PrfPtc** 
* **+PrfPrt**
* **+PrsPrt**

* **+ABBR +ACR** 
* **+Symbol**  = independent symbols in the text stream, like £, €, ©
Special symbols are classified with:
* **+CLB +PUNCT +LEFT +RIGHT +MIDDLE** 
* **+CLBfinal**

The verbs are syntactically split according to transitivity: (well, not yet)
* **+TV +IV** 
Special multiword units are analysed with:
* **+Multi** 
* **+MWE**

Numeral subgroups

* **+Arab**
* **+Rom**
* **+Coll**

Non-dictionary words can be recognised with:
* **+Guess** 

Question and Focus particles:
* **+Qst +Foc** 

The Usage extents are marked using following tags:
* **+Err/Orth** 
* **+Use/-Spell** 

* **+Err/Hyph**
* **+Err/Lex**
* **+Err/MissingSpace**
* **+Err/SpaceCmp**

* **+Use/-PLX**
* **+Use/-PMatch**
* **+Use/Circ**
* **+Use/GC**
* **+Use/NG**
* **+Use/PMatch**
* **+Use/SpellNoSugg**
* **+Use/TTS** – **only** retained in the HFST Text-To-Speech disambiguation tokeniser
* **+Use/-TTS** – **never** retained in the HFST Text-To-Speech disambiguation tokeniser

## Paradigm choice

* **+v1**
* **+v2**

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

* **+Sem/Amount**
* **+Sem/Build-room**
* **+Sem/Cat**
* **+Sem/Curr**
* **+Sem/Date**
* **+Sem/Domain**
* **+Sem/Domain_Hum**
* **+Sem/Dummytag**
* **+Sem/Edu_Hum**
* **+Sem/Event**
* **+Sem/Food-med**
* **+Sem/Group_Hum**
* **+Sem/ID**
* **+Sem/Lang**
* **+Sem/Mat**
* **+Sem/Money**
* **+Sem/Obj-el**
* **+Sem/Obj-ling**
* **+Sem/Org_Prod-audio**
* **+Sem/Org_Prod-vis**
* **+Sem/Part**
* **+Sem/Prod-vis**
* **+Sem/Rule**
* **+Sem/Sign**
* **+Sem/State**
* **+Sem/State-sick**
* **+Sem/Substnc**
* **+Sem/Time-clock**
* **+Sem/Tool-it**
* **+Sem/Year**

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

| Flag diacritic | Explanation
| :------------- |:-----------
| @U.number.one@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.two@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.three@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.four@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.five@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.six@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.seven@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.eight@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.nine@ | Flag used to give arabic numerals in smj different cases ;
| @U.number.zero@ | Flag used to give arabic numerals in smj different cases ;
## Compound tags

* **+CmpNP/First**
* **+CmpNP/None**

## Language tags

* **+OLang/ENG**
* **+OLang/FIN**
* **+OLang/NNO**
* **+OLang/NOB**
* **+OLang/RUS**
* **+OLang/SMA**
* **+OLang/SME**
* **+OLang/SWE**
* **+OLang/UND**

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

<small>This (part of) documentation was generated from [src/fst/morphology/root.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/morphology/root.lexc)</small>
