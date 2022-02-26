# Traveller Norwegian description 

All documents in one file

# Adjective inflection
The Traveller Romani language adjectives compare.

**TODO!** the grammar lists *-e* and *-t* forms.
These should get morphosyntactic tags (here ad hoc
marked as *+Pl* and *+Der/Adv+Adv*.

**LEXICON a1**

**LEXICON a2** is here given plural *-a* and redirected to **a1**.

**LEXICON comp** *-are, -ast, -aste*, the latter marked *+Def*.

* * *

<small>This (part of) documentation was generated from [src/fst/affixes/adjectives.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/affixes/adjectives.lexc)</small>

---

# Noun inflection
The Traveller Romani language nouns inflect in number and definiteness

**TODO:** The lexica *m1 - m4* may be unified and their inflection 
differences handled in twolc. *f1, f2* and *n* have different suffixes
and should be kept.

**LEXICON mx** for uninflected (for now)

**LEXICON f1m2** split in two

**LEXICON f1m1** split  in two

**LEXICON f** goes to f2

**LEXICON pl** with no gender info

**LEXICON m1** 

**LEXICON m1pl** pl only

**LEXICON m2**

**LEXICON m3**

**LEXICON m4**

**LEXICON f1**

**LEXICON f2**

**LEXICON n**

* * *

<small>This (part of) documentation was generated from [src/fst/affixes/nouns.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/affixes/nouns.lexc)</small>

---

# Proper noun inflection
The Traveller Romani language proper nouns inflect in the same cases as regular
nouns, but with a colon (':') as separator.

**LEXICON prop-fem**
**LEXICON prop-mal**
**LEXICON prop-plc**
**LEXICON prop-obj**

* * *

<small>This (part of) documentation was generated from [src/fst/affixes/propernouns.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/affixes/propernouns.lexc)</small>

---


# Symbol affixes

**LEXICON Noun_symbols_possibly_inflected**

**LEXICON Noun_symbols_never_inflected**

**LEXICON SYMBOL_connector**

**LEXICON SYMBOL_NO_suff**

**LEXICON SYMBOL_suff**

* * *

<small>This (part of) documentation was generated from [src/fst/affixes/symbols.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/affixes/symbols.lexc)</small>

---

# Verb inflection
The Traveller Romani language verbs inflect in tense and participle.
The lexica v1, v2, v3 are taken from the grammar.
The distinction lies in the past tense suffix (null for v1 vs. dde for v2).

**LEXICON v1** 

**LEXICON v2** 

**LEXICON v3** 

* * *

<small>This (part of) documentation was generated from [src/fst/affixes/verbs.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/affixes/verbs.lexc)</small>

---

=================================== !
# The Traveller Romani morphophonological/twolc rules file 
=================================== !

## Alphabet
* a b c d e f g h i j k l m n o p q r s t u v w x y z æ ø å
  á é ó ú í à è ò ù ì ä ë ö ü ï â ê ô û î ã ý þ ñ ð ß ç
* 
* A B C D E F G H I J K L M N O P Q R S T U V W X Y Z Æ Ø Å
  Á É Ó Ú Í À È Ò Ù Ì Ä Ë Ö Ü Ï Â Ê Ô Û Î Ã Ý þ Ñ Ð

* %> ; this is the suffix boundary

## Sets

* Vow = a e i o u y æ ø å basic vowels
* á é ó ú í à è ò ù ì ä ë ö ü ï â ê ô û î ã ý ; these just in case
* Cns = b c d f g h j k l m n p q r s t v w x z ð þ ; consonants

## Rules

**RULE: Deleting stem-final e in front of vowel-initial suffix** =   

**RULE: Deleting stem-internal a before r in bisyllabic stems** =   

* * *

<small>This (part of) documentation was generated from [src/fst/phonology.twolc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/phonology.twolc)</small>

---


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
* **+Inf +Neg +PrsPrc +PrfPrc** 

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
Nouns ; 
Verbs ; 
Adjectives ; 
Adverbs ; 
Pronouns ; 
Propernouns ; 
Numerals ; 
Prefixes ; 
Punctuation ; 
Symbols ; 

* * *

<small>This (part of) documentation was generated from [src/fst/root.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/root.lexc)</small>

---

# Adjectives
Adjectives in the Traveller Romani language have two sblexica, *a1, a2*.

**LEXICON Adjectives** 

* latjo a1 "god" ;
* sjukkar a2 "fin" ;  "fin, pen. sjukkart fint, pent. sjukkre ~ sjukkra fine, pene" ;
* savo a1 "slik" ;
* norsk a2 "norsk" ; (?)
* vavri a1 "annen" ;
* vaver a2 "annen" ;
* aven-dukkalo a1 "misunnelig " ;
* baro a1 "stor" ;
* baro-kasjt m2 "stor-pinne" ;
all in all appr. 70 adjectives for now.

* * *

<small>This (part of) documentation was generated from [src/fst/stems/adjectives.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/adjectives.lexc)</small>

---

# Traveller Romani adverbs

For now, this file contains not only adverbs (they should stay), 
but also a rest category of things to be moved to their respective
stem files (one file for each part-of-speech).

**LEXICON adv** adds the tag **+Adv**

**LEXICON cs** adds the tag  **+CS**

**LEXICON cc** adds the tag  **+CC**

**LEXICON pr** adds the tag  **+Pr**

**LEXICON vaux** adds the tag  **++V+Ind**, this lexicon is probably not needed

**LEXICON ij** adds the tag  **+Interj**

**LEXICON Adverbs** lists the adverbs themselves (as well as the restcategory, for now)
* ehe ij "ja" ;
* alonom adv "aleine" ;

* ifann adv "ifra" ;
* ipali adv "igjen" ;

* * *

<small>This (part of) documentation was generated from [src/fst/stems/adverbs.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/adverbs.lexc)</small>

---

# Nouns
This is the noun stem file. Nouns in the Traveller Romani are divided in m, f, n.

**TODO** Conflate m1-m4.

**LEXICON Nouns** 

* tjavo m1 "gut" ;
* trulsing m2 "dokke" ;
* hisjpa m3 "hus" ;
* danje m4 "tann" ;
* busjni f1 "geit" ;
* gaje f2 "kvinne" ;
* bæsj n "år" ;

* * *

<small>This (part of) documentation was generated from [src/fst/stems/nouns.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/nouns.lexc)</small>

---

# Numerals
This is a list of whatever was found in the dictionary.

**TODO** Make a systematic list

**LEXICON num** just adds the tag **+Num**.

**LEXICON Numerals** splits layers of numerals in sublexca

**LEXICON TEENS** where *dypansj-* is redirected to **1to9**.

**LEXICON 1to9** contains the basic numerals

**LEXICON TENS** contains 10, 20, .. 90.

**LEXICON TENSsplit** splits 20, ... 90 into 20 vs 21, 22, ...
num ; num ;  * @CODE* here the tens go to +Num: snes, trinn-dypansj, ..
-å- 1to9 ; -å- 1to9 ;   * @CODE* here the tens go to 1to9: snes-å-dy, trinn-dypansj-å-jikk, ..

**LEXICON numeralcompounds** is a lexicon to be looked into.

* * *

<small>This (part of) documentation was generated from [src/fst/stems/numerals.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/numerals.lexc)</small>

---

# Prefixes
Prefixes in the Traveller Romani language ...

Nothing has been done on this, it is a dummy file.
The intention is to add eventual prefixes such as Norwegian *u-*.

* * *

<small>This (part of) documentation was generated from [src/fst/stems/prefixes.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/prefixes.lexc)</small>

---

# Pronouns
This is a list of pronouns in the Traveller Romani language.

**TODO** The lis should be completed and given morphosyntactic tags
when needed.

**LEXICON pers** adds the tags *+Pron+Pers*

**LEXICON Pronouns** lists personal pronouns

* * *

<small>This (part of) documentation was generated from [src/fst/stems/pronouns.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/pronouns.lexc)</small>

---

# Traveller Romani propernouns

Here, we should use the nob file.

**LEXICON Propernouns** 

* Norge prop-plc ;
* India prop-plc ;

* * *

<small>This (part of) documentation was generated from [src/fst/stems/propernouns.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/propernouns.lexc)</small>

---

# Verbs
This is the list of verbs in the Traveller Romani language.

**LEXICON Verbs**
* dabba v1 "slå" ;
* ka v2 "ete" ;
* dabbas v3 "slåst" ;
* ava v1 "komme" ;
* bekkna v1 "selge " ;
* besja v1 "sitte, sette; stå " ;
* bæsja v1 "sitte, sette; stå " ;
* blava v1 "henge " ;
* bliddra v1 "bli" ;
* boddra v1 "bo " ;
* brasja v1 "fryse" ;
* brukkla v1 "bruke = bruttla" ;
* bruktara v1 "bruke" ;
* brusja v1 "regne (om vær) " ;
* ... etc.
All in all some 100 verbs for now.

* * *

<small>This (part of) documentation was generated from [src/fst/stems/verbs.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/fst/stems/verbs.lexc)</small>

---



retroflex plosive, voiceless			t`  ʈ	    0288, 648 (` = ASCII 096)
retroflex plosive, voiced			d`	ɖ		0256, 598
labiodental nasal					F 	ɱ		0271, 625
retroflex nasal						n` 	ɳ		0273, 627
palatal nasal						J 	ɲ		0272, 626
velar nasal							N 	ŋ		014B, 331
uvular nasal							N\	ɴ		0274, 628
	
bilabial trill						B\ 	ʙ		0299, 665
uvular trill							R\ 	ʀ		0280, 640
alveolar tap							4	ɾ		027E, 638
retroflex flap						r` 	ɽ		027D, 637
bilabial fricative, voiceless		p\ 	ɸ		0278, 632
bilabial fricative, voiced			B 	β		03B2, 946
dental fricative, voiceless			T 	θ		03B8, 952
dental fricative, voiced				D 	ð		00F0, 240
postalveolar fricative, voiceless	S	ʃ		0283, 643
postalveolar fricative, voiced		Z 	ʒ		0292, 658
retroflex fricative, voiceless		s` 	ʂ		0282, 642
retroflex fricative, voiced			z` 	ʐ		0290, 656
palatal fricative, voiceless			C 	ç		00E7, 231
palatal fricative, voiced			j\ 	ʝ		029D, 669
velar fricative, voiced	        	G 	ɣ		0263, 611
uvular fricative, voiceless			X	χ		03C7, 967
uvular fricative, voiced				R 	ʁ		0281, 641
pharyngeal fricative, voiceless		X\ 	ħ		0127, 295
pharyngeal fricative, voiced			?\ 	ʕ		0295, 661
glottal fricative, voiced			h\	ɦ		0266, 614

alveolar lateral fricative, vl.		K 
alveolar lateral fricative, vd.		K\

labiodental approximant				P (or v\) 
alveolar approximant					r\ 
retroflex approximant				r\` 
velar approximant					M\

retroflex lateral approximant		l` 
palatal lateral approximant			L 
velar lateral approximant			L\
Clicks

bilabial								O\	(O = capital letter) 
dental								|\
(post)alveolar						!\ 
palatoalveolar						=\ 
alveolar lateral						|\|\
Ejectives, implosives

ejective								_>	e.g. ejective p		p_>
implosive							_<	e.g. implosive b	b_<
Vowels

close back unrounded					M
close central unrounded 				1 
close central rounded				} 
lax i								I 
lax y								Y 
lax u								U

close-mid front rounded				2 
close-mid central unrounded			@\ 
close-mid central rounded			8 
close-mid back unrounded				7

schwa	ə							@

open-mid front unrounded				E 
open-mid front rounded				9
open-mid central unrounded			3 
open-mid central rounded				3\ 
open-mid back unrounded				V 
open-mid back rounded				O

ash (ae digraph)						{ 
open schwa (turned a)				6

open front rounded					& 
open back unrounded	        		A 
open back rounded					Q
Other symbols

voiceless labial-velar fricative		W 
voiced labial-palatal approx.		H 
voiceless epiglottal fricative		H\ 
voiced epiglottal fricative			<\ 
epiglottal plosive					>\

alveolo-palatal fricative, vl. 		s\ 
alveolo-palatal fricative, voiced	z\ 
alveolar lateral flap				l\ 
simultaneous S and x					x\ 
tie bar								_
Suprasegmentals

primary stress						" 
secondary stress						% 
long									: 
half-long							:\ 
extra-short							_X 
linking mark							-\
Tones and word accents

level extra high						_T 
level high							_H
level mid							_M 
level low							_L 
level extra low						_B
downstep								! 
upstep								^	(caret, circumflex)

contour, rising						 
contour, falling						_F 
contour, high rising					_H_T 
contour, low rising					_B_L 

contour, rising-falling				_R_F 
(NB Instead of being written as diacritics with _, all prosodic 
marks can alternatively be placed in a separate tier, set off 
by < >, as recommended for the next two symbols.)
global rise						<R> 
global fall						<F>
Diacritics						
									
voiceless						_0	(0 = figure), e.g. n_0
voiced							_v 
aspirated						_h 
more rounded						_O	(O = letter) 
less rounded						_c 
advanced							_+
retracted						_-
centralized						_" 
syllabic							=	(or _=) e.g. n= (or n_=) 
non-syllabic						_^ 
rhoticity						`
									
breathy voiced					_t 
creaky voiced					_k
linguolabial						_N 
labialized						_w 
palatalized						'	(or _j) e.g. t' (or t_j) 
velarized						_G 
pharyngealized					_?\
									
dental							_d 
apical							_a 
laminal							_m
nasalized						~	(or _~) e.g. A~ (or A_~) 
nasal release					_n
lateral release					_l 
no audible release				_}

velarized or pharyngealized		_e 
velarized l, alternatively		5 
raised							_r 
lowered							_o 
advanced tongue root				_A 
retracted tongue root			_q

* * *

<small>This (part of) documentation was generated from [src/phonetics/txt2ipa.xfscript](https://github.com/giellalt/lang-rmg/blob/main/src/phonetics/txt2ipa.xfscript)</small>

---



We describe here how abbreviations are in Traveller Norwegian are read out, e.g.
for text-to-speech systems.

For example:

* s.:syntynyt # ;  
* os.:omaa% sukua # ;  
* v.:vuosi # ;  
* v.:vuonna # ;  
* esim.:esimerkki # ; 
* esim.:esimerkiksi # ; 

* * *

<small>This (part of) documentation was generated from [src/transcriptions/transcriptor-abbrevs2text.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/transcriptions/transcriptor-abbrevs2text.lexc)</small>

---



% komma% :,      Root ;
% tjuohkkis% :%. Root ;
% kolon% :%:     Root ;
% sárggis% :%-   Root ; 
% násti% :%*     Root ; 

* * *

<small>This (part of) documentation was generated from [src/transcriptions/transcriptor-numbers-digit2text.lexc](https://github.com/giellalt/lang-rmg/blob/main/src/transcriptions/transcriptor-numbers-digit2text.lexc)</small>

---

# Tokeniser for rmg

Usage:
```
$ make
$ echo "ja, ja" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "Juos gorreválggain lea (dárbbašlaš) deavdit gáibádusa boasttu olmmoš, man mielde lahtuid." | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "(gáfe) 'ja' ja 3. ja? ц jaja ukjend \"ukjend\"" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "márffibiillagáffe" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

Pmatch documentation:
<https://github.com/hfst/hfst/wiki/HfstPmatch>

Characters which have analyses in the lexicon, but can appear without spaces
before/after, that is, with no context conditions, and adjacent to words:
* Punct contains ASCII punctuation marks
* The symbol after m-dash is soft-hyphen `U+00AD`
* The symbol following {•} is byte-order-mark / zero-width no-break space
`U+FEFF`.

Whitespace contains ASCII white space and
the List contains some unicode white space characters
* En Quad U+2000 to Zero-Width Joiner U+200d'
* Narrow No-Break Space U+202F
* Medium Mathematical Space U+205F
* Word joiner U+2060

Apart from what's in our morphology, there are
1. unknown word-like forms, and
2. unmatched strings
We want to give 1) a match, but let 2) be treated specially by
`hfst-tokenise -a`
Unknowns are made of:
* lower-case ASCII
* upper-case ASCII
* select extended latin symbols
ASCII digits
* select symbols
* Combining diacritics as individual symbols,
* various symbols from Private area (probably Microsoft),
so far:
* U+F0B7 for "x in box"

## Unknown handling
Unknowns are tagged ?? and treated specially with `hfst-tokenise`
hfst-tokenise --giella-cg will treat such empty analyses as unknowns, and
remove empty analyses from other readings. Empty readings are also
legal in CG, they get a default baseform equal to the wordform, but
no tag to check, so it's safer to let hfst-tokenise handle them.

Finally we mark as a token any sequence making up a:
* known word in context
* unknown (OOV) token in context
* sequence of word and punctuation
* URL in context

* * *

<small>This (part of) documentation was generated from [tools/tokenisers/tokeniser-disamb-gt-desc.pmscript](https://github.com/giellalt/lang-rmg/blob/main/tools/tokenisers/tokeniser-disamb-gt-desc.pmscript)</small>

---

# Grammar checker tokenisation for rmg

Requires a recent version of HFST (3.10.0 / git revision>=3aecdbc)
Then just:
```
$ make
$ echo "ja, ja" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

More usage examples:
```
$ echo "Juos gorreválggain lea (dárbbašlaš) deavdit gáibádusa boasttu olmmoš, man mielde lahtuid." | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "(gáfe) 'ja' ja 3. ja? ц jaja ukjend \"ukjend\"" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
$ echo "márffibiillagáffe" | hfst-tokenise --giella-cg tokeniser-disamb-gt-desc.pmhfst
```

Pmatch documentation:
<https://github.com/hfst/hfst/wiki/HfstPmatch>

Characters which have analyses in the lexicon, but can appear without spaces
before/after, that is, with no context conditions, and adjacent to words:
* Punct contains ASCII punctuation marks
* The symbol after m-dash is soft-hyphen `U+00AD`
* The symbol following {•} is byte-order-mark / zero-width no-break space
`U+FEFF`.

Whitespace contains ASCII white space and
the List contains some unicode white space characters
* En Quad U+2000 to Zero-Width Joiner U+200d'
* Narrow No-Break Space U+202F
* Medium Mathematical Space U+205F
* Word joiner U+2060

Apart from what's in our morphology, there are
1) unknown word-like forms, and
2) unmatched strings
We want to give 1) a match, but let 2) be treated specially by hfst-tokenise -a
* select extended latin symbols
* select symbols
* various symbols from Private area (probably Microsoft),
so far:
* U+F0B7 for "x in box"

TODO: Could use something like this, but built-in's don't include šžđčŋ:

Simply give an empty reading when something is unknown:
hfst-tokenise --giella-cg will treat such empty analyses as unknowns, and
remove empty analyses from other readings. Empty readings are also
legal in CG, they get a default baseform equal to the wordform, but
no tag to check, so it's safer to let hfst-tokenise handle them.

Finally we mark as a token any sequence making up a:
* known word in context
* unknown (OOV) token in context
* sequence of word and punctuation
* URL in context

* * *

<small>This (part of) documentation was generated from [tools/tokenisers/tokeniser-gramcheck-gt-desc.pmscript](https://github.com/giellalt/lang-rmg/blob/main/tools/tokenisers/tokeniser-gramcheck-gt-desc.pmscript)</small>

---
