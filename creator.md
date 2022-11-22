# Creator's and Facilitator's living manual

## Recommended export for native format by creator tools
<!-- edit the table below by copy-pasting in https://www.tablesgenerator.com/markdown_tables -->
|         | type(s)   | format preferred (first) | preferred (second) |
|---------|-----------|-------------------|--------------------|
| [Moodle]  | [MCQ]       | [aiken]           | [moodle_xml]         |
|           | [Matching]  | [gift]        | [moodle_xml]                   |
| [Quizizz] | [MCQ]       | [quizizz_HTML]   |                    |
|           | [Matching]  | [not tested]            |                    |

[Moodle]: https://github.com/frederic-baucher/q4eef/blob/main/doc/tools/moodle.md
[Quizizz]: https://github.com/frederic-baucher/q4eef/blob/main/doc/tools/quizizz.md
[Kahoot]: https://github.com/frederic-baucher/q4eef/blob/main/doc/tools/kahoot.md
[GetMarked]: https://github.com/frederic-baucher/q4eef/blob/main/doc/tools/getmarked.md

[MCQ]: https://github.com/frederic-baucher/q4eef/blob/main/doc/types/mcq.md
[Matching]: https://github.com/frederic-baucher/q4eef/blob/main/doc/types/matching.md

[aiken]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/aiken.md
[gift]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/gift.md
[moodle_xml]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/moodle_xml.md
[quizizz Excel]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/quizizz_excel.md
[quizizz_HTML]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/quizizz_html.md
[not tested]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/not_tested.md

## Storage repository : pivots
The file exported from the creator tool has to be stored in the [__native pivots__](https://github.com/frederic-baucher/q4eef/tree/main/bank/repo4export) directory of this Github repository. Any additional file (for instance, images) has to be stored in the same place. All the files must follow the __q4eef naming convention__.

## Naming convention : q4eef
Any exported exercise file __MUST__ have a name (stored in a dedicated sub-directory of _repo4export_) __COMPLIANT__ with the naming convention.

### Pattern for the dedicated sub-directory
- \bank\repo4exported $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{label}}$

#### Examples
- $\textcolor{red}{\text{SEMAT}}\textcolor{orange}{\text{0094}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious-games}}$
  - a sub-directory of repo4export containing all the files of the exercise SEMAT0094 (authored by SEMAT as indicated in the table _Registered authors_)
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}$
  - a sub-directory of repo4export containing all the files of the exercise EXG2131 (authored by INSA as indicated in the table _Registered authors_)
#### Legend
- $\textcolor{red}{\text{creator}}$ : creator question bank identifier (upper case alphabets [A-Z]), as registered in the table _Registered authors_ (below)
- $\textcolor{orange}{\text{id}}$ : id of the exercise (upper case numbers [0-9], unique inside the creator repository)
- $\textcolor{grey}{\text{label}}$ : label (only low-case alphabets [a-z], minus separated if necessary)

### Pattern for file
- $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{[.}}\textcolor{grey}{\text{label}}\textcolor{black}{\text{][-][}}\textcolor{blue}{\text{lang}}\textcolor{black}{\text{][.}}\textcolor{pink}{\text{type}}\textcolor{black}{\text{][.}}\textcolor{green}{\text{format}}\textcolor{black}{\text{].}}\textcolor{purple}{\text{extension}}$
  - in directory \bank\repo4exported\ $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{label}}$
#### Examples
- $\textcolor{red}{\text{SEMAT}}\textcolor{orange}{\text{0094}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious-games}}\textcolor{black}{\text{.}}\textcolor{green}{\text{quizizz}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{html}}$ or $\textcolor{red}{\text{SEMAT}}\textcolor{orange}{\text{0094}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious-games}}\textcolor{blue}{\text{-en}}\textcolor{black}{\text{.}}\textcolor{pink}{\text{mcq}}\textcolor{black}{\text{.}}\textcolor{green}{\text{quizizz}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{html}}$
  - a file containing an exercise created in the SEMAT repository, under id 0094. All defaults can be ommited : for info, the default type is _mcq_ (multiple-choice question) and the default language is _en_ (english)
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}\textcolor{black}{\text{.}}\textcolor{pink}{\text{matching}}\textcolor{black}{\text{.}}\textcolor{green}{\text{gift}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{txt}}$
  - a file containing a matching exercise in GIFT format stored in a txt file (for info, AIKEN does not support matching type).
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{blue}{\text{fr}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{png}}$
  - a file containing an image localised in french to be used with exercise EXG2131
#### Legend
- $\textcolor{red}{\text{creator}}$ : creator question bank identifier (upper case alphabets [A-Z]), as registered in the table below
- $\textcolor{orange}{\text{id}}$ : id of the exercise (upper case numbers [0-9], unique inside the creator repository)
- $\textcolor{grey}{\text{label}}$ : label (only low-case alphabets [a-z], minus separated if necessary)
- $\textcolor{blue}{\text{lang}}$ : language code compliant with ISO 639-1 (default : en)
- $\textcolor{pink}{\text{type}}$ : type of exercise (default : mcq) 
- $\textcolor{green}{\text{format}}$ : logical format name (among the format list)
- $\textcolor{purple}{\text{extension}}$ : technical format name (xlsx, txt, csv, ...)

## Registered authors

<!-- edit the table below by copy-pasting in https://www.tablesgenerator.com/markdown_tables -->
| author's id | author's bank product | bank's operator | author's reference      | facilitator's reference                                          |
|-------------|---------------|-----------------|-------------------------|------------------------------------------------------------------|
| SEMAT       | [Quizizz]       | _Saas_          | https://semat.org       | [Frédéric BAUCHER] |
| EXG         | [Moodle]        | [INSA-ROUEN]      | [Frédéric BAUCHER] |       |
| welcome     | new           | new             | you                                                                                | you   |

To  let any creator choose its identification numbering of exercise (and yet have a unique id for any exercise in q4eef), a creator MUST have a creator id. This table list the creators already registered. To add a new creator, you can edit the table below in [this README.md file](https://github.com/frederic-baucher/q4eef/edit/main/README.md) (a new branch will be created and the q4eef needs to merge it before publication) or you can request before a write access [by filling a new issue](https://github.com/frederic-baucher/q4eef/issues/new) to this Github repository.

[INSA-ROUEN]: https://moodle.insa-rouen.fr
[Frédéric BAUCHER]: https://fr.linkedin.com/in/fr%C3%A9d%C3%A9ric-baucher-3026481a

