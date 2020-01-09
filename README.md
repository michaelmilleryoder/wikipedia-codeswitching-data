# wikipedia-codeswitching-data
Wikipedia talk page code-switching features and editor success scores data. Accompanying paper:

[Michael Miller Yoder, Shruti Rijhwani, Carolyn Penstein Rose, Lori Levin. (2017). Code-Switching as a Social Act: The Case of Arabic Wikipedia Talk Pages. *Proceedings of the Second Workshop on Natural Language Processing and Computational Social Science (NLP+CSS)*](https://www.aclweb.org/anthology/W17-2911.pdf).

Contact yoder@cs.cmu.edu for scripts for dataset construction or other questions.

## Data columns
Columns in `arabic_talk_cs_features.csv` are explained here. The above paper has more detail on these features.

* `article`: the name of the Wikipedia article from which the talk page conversations are drawn and from which editor scores are calculated.
* `thread_title`: the name of the talk page discussion thread
* `editor_anonym`: an anonymized ID that corresponds to which editor made the talk contribution
* `editor_talk`: that editor's contributions to the discussion thread, concatenated
* `other_talk`: other editors' contributions to the discussion thread, concatenated
* `#editor_turns`: the number of discussion turns contributed by that editor
* `#other_turns`: the number of discussion turns contributed by other editors
* `editor_score`: a measure of that editor's success in editing the article page. This is the proportion of modifications the editor made that are still present 24 hours after the last contribution in the discussion thread. Details can be found in the accompanying [paper](https://www.aclweb.org/anthology/W17-2911.pdf), where this measure is the outcome to be predicted from features in the talk.

Code-switching features

* `latin_cs`: binary variable if the editor talk contains code-switching to languages with Latin script.
* `other_latin_cs`: binary variable if the talk from other editors in the thread contains code-switching to languages with Latin script.
* `editor_prop_latin`: proportion of tokens in the editor talk that contain Latin script.
* `other_prop_latin`: proportion of tokens in the other editors' talk that contain Latin script.
* `editor_prop_switches`: proportion of word boundaries in the editor text which switch between languages in Arabic and Latin script.
* `other_prop_switches`: proportion of word boundaries in the others' text which switch between languages in Arabic and Latin script.
* `editor_talk_latin`: extracted text from the editor in this thread that contains Latin script.
* `editor_talk_arabic`: extracted text from the editor in this thread that contains Arabic script.
* `editor_talk_non_arabic`: extracted text from the editor in this thread that contains anything other than tokens with Arabic script.
* `editor_two_quotes`: binary variable indicating whether the editor talk in this thread contains at least 2 quote marks (and likely is quoting).
* `editor_latin_named_entities`: whether the Latin script in the editor talk is likely named entities.
* `{language}_prop`: proportion of the editor talk that is identified by a language identification system as being from that language.
* `{language}_cs`: binary variable that is 'true' if there is a nonzero proportion of this language based on output from a language identification system.
* `categories`: which categories that Wikipedia article page belongs to.
