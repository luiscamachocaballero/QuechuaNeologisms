# QuechuaNeologisms
Code to automate borrowing of neologisms to Quechua from any other language


This method avoids the rephonologization of the proposed neologisms since they have been selected by our algorithm precisely because they meet the requirement of fitting the phonology of the target language.  Our method requires phonetic notation of the source languages. We found two sources of IPA representation of several languages: Open Dictionary and Wikipron. The Open Dictionary project aims to collect open-licensed multilingual dictionary data and provide it in a variety of accessible formats for use by humans and computers.
WikiPron[9] is a command-line tool and Python API for mining multilingual pronunciation data from Wiktionary, as well as a database of pronunciation dictionaries mined using this tool.
These two sources were processed separately. The first source is made up of csv files and the second source is made up of tsv files. Each of these files corresponds to a different language, in each file, there are two columns: the words are located in the first one and their corresponding IPA transcriptions are located in the second one, in the same row. The GettingNeologisms.ipynb script collects all the spelling and pronunciation rules mentioned in the previous section. After executing the script, two intermediate files are obtained that collect all the words with the requested phonology present in the csv and tsv directories, respectively. Since the files in the csv directory are labeled according to the ISO639-1 terminology, they had to be relabeled following the correspondence table to obtain the labels with the current ISO639-5 nomenclature.

The two intermediate files were inputs to the SincronizationWordNet.ipynb script which identifies the words and their respective languages ​​present in the intermediate files; if the script finds both in WordNet it delivers the English translation. To be exact, the English synset is searched for in WordNet and then all the lemmas associated with that synset are listed. 

As the next step, we translated the IPA notation of the selected neologisms to the Quechua orthography. Finally, we used the GOOGLETRANSLATE function of Google Spreadsheets to translate the neologisms from their original language to Spanish.
