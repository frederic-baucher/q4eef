<!-- https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes -->
# q4eef

https://github.com/frederic-baucher/q4eef/blob/f5c82be6d71f65c6cfb2e8caef1e51fe4a601fe5/README.md?plain=1#L14

https://github.com/frederic-baucher/q4eef/blob/2138e6129d5493369d7f65c617416258c2ab2c72/doc/usecases.puml?plain=#L36-L37

# Introduction 

## Usage
q4eef is a solution for sharing Essence exercises and support the Essence adoption in education.



### Glossary
The actors of this solution are :
- __author__ : any teacher, consultant, ... that creates an exercise in a Questions_Bank of her/his choice (Moodle, ...).
- __facilitator__ : any teacher, consultant, ... willing to share, on q4eef, herself/himself or on behalf of the author (after checking the copyright concerns)
- __creator__ : a person who is the author and faciltator of an exercise available on q4eef
- __reuser__ : any teacher that wants to reuse exercise stored in q4eef
- __moderator__ : designated teacher(s) monitoring the access to q4eef
- __maintainer__ : any creator or moderator that generate the target pivots

Other terms :
- __native pivot__ : file exported from the creator tool
- __target pivot__ : file to be imported in the reuser tool (in case the creator and the reuser have the same export and import format respectively), the target pivot is a copy of the native pivot.

Use cases :
- Convert exercise : in case the exported format is not very convenient as a native pivot (like [Quizizz](https://github.com/frederic-baucher/q4eef/blob/main/doc/export_from_quizizz.md)), the creator can convert it with a dedicated tools (regex tools, spreadsheet, ...).

### Diagram
<!-- to update the image in Github, modify THIS README.md file -->


## Implementation
q4eef is implemented in this Github repository
- a __creator__ must have an account on Github and be granted with write access to q4eef repository


### Directory tree

The main directories for user's of q4eef are as follow :
- __repo4export__ : stores the files exported by creator of exercise from their tools of choice (in the format recommended in the table _Creator tools_).
- __ready2import__ : organised by tools, stores the files to be imported in the LMS (_moodle_, ...) or quizz (_kahoot, quizizz, wooclap, ..._) tools. These files are copies or conversion of the original files stored in __pivots__.
- __pivots4adapt__ : organised by tools, stores the files to be converted by an adapter. An adapter is a tool able to generate many formats from one pivot, like _digitaliser_ operated by _getmarked_ that can generate _Quizizz Excel, Kahoot Excel_ from a _getmarked_ pivot format).

```bash
q4eef
├───bank
│   ├───pivots4adapt
│   │   └───getmarked
    │   └───any_new_adapter...    
│   ├───ready2import
│   │   ├───kahoot
│   │   ├───moodle
│   │   ├───quizziz
│   │   └───wooclap
│   │   └───any_new_tool_of_reuser ...             
│   └───repo4export
```

### Files in directory tree

This tree shows two exercises identified by id SEMAT0094 (mcq type) and id EXG2131 (matching type).
- SEMAT0094 has been created in Quizizz and is made available in AIKEN format for other tools.
- EXG2131 has been created in Moodle and is made available in GIFT format for other tools.

In __repo4export__ directory, we see the native pivot of __any__ shared exercise :
- _SEMAT0094.serious_games.aiken.txt_
- _EXG2131.scrum_in_essence_constructs.gift.txt_
  - _EXG2131.scrum_in_essence_constructs-en.png, EXG2131.scrum_in_essence_constructs-fr.png_ : additional files that can be used (if allowed in target tool) for enhancing the student experience.

The __native pivots__ has been converted in format allowed for import by the tools listed __ready2import__.
- kahoot : contains __some (not necessary all)__ exercises available in _repo4export_ ready to be imported in Kahoot
  - _SEMAT0094.serious_games.kahoot.xlsx_ : file to be imported in Kahoot to create SEMAT0094 exercise
  - _EXG2131.scrum_in_essence_constructs.kahoot.xlsx_ : file to be imported in Kahoot to create EXG2131 exercise
  - _EXG2131.scrum_in_essence_constructs-en.png_ : image to be uploaded manually in Kahoot to enhance EXG2131 quizz in english
- quizizz : contains some (not necessary all) exercises available in repo4export ready to be imported in Quizizz
  - _EXG2131.scrum_in_essence_constructs.quizizz.xlsx_ : no image because it is embedded in the quizizz Excel format that allow reference to an image.
- other tools : if a reuser tool does not exist, she/he can ask for creating it her/himself

If other conversion are necessary in the future, adapters pivot format can also be copied in __pivots4adapt__ :
- _SEMAT0094.serious_games.getmarked.txt_ : pivot format to be converted by getmarked

```bash
├── bank
│   ├── pivots4adapt
│   │   └── getmarked
│   │       └── SEMAT0094.serious_games.getmarked.txt
│   ├── ready2import
│   │   ├── kahoot
│   │   │   ├── SEMAT0094.serious_games.kahoot.xlsx
│   │   │   ├── EXG2131.scrum_in_essence_constructs-en.png
│   │   │   └── EXG2131.scrum_in_essence_constructs.kahoot.xlsx
│   │   ├── moodle
│   │   │   ├── SEMAT0094.serious_games.aiken.txt
│   │   │   └── EXG2131.scrum_in_essence_constructs.moodle.xml
│   │   ├── quizziz
│   │   │   ├── SEMAT0094.serious_games.quizizz.xlsx
│   │   │   └── EXG2131.scrum_in_essence_constructs.quizizz.xlsx
│   │   └── wooclap
│   │       ├── SEMAT0094.serious_games.moodle.xml
│   │       └── EXG2131.scrum_in_essence_constructs.moodle.xml
│   └── repo4export
│       ├── SEMAT0094.serious_games.aiken.txt
│       ├── EXG2131.scrum_in_essence_constructs-en.png
│       ├── EXG2131.scrum_in_essence_constructs-fr.png
│       └── EXG2131.scrum_in_essence_constructs.gift.txt
```

# Creator tools

## Recommended export by creator tools
<!-- edit the table below by copy-pasting in https://www.tablesgenerator.com/markdown_tables -->
|         | type(s)   | format preferred (first) | preferred (second) |
|---------|-----------|-------------------|--------------------|
| [Moodle]  | [MCQ]       | [aiken]           | [moodle_xml]         |
|           | [Matching]  | [gift]        | [moodle_xml]                   |
| [Quizizz] | [MCQ]       | [quizizz Excel]   |                    |
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
[not tested]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/not_tested.md

## Storage repository : pivots
The file exported from the creator tool has to be stored in the [__native pivots__](https://github.com/frederic-baucher/q4eef/tree/main/bank/repo4export) directory of this Github repository. Any additional file (for instance, images) has to be stored in the same place. All the files must follow the __q4eef naming convention__.

## Naming convention : q4eef
Any exported exercise file __MUST__ have a name (and a sub-directory of _repo4export_) __COMPLIANT__ with the naming convention.

### Pattern for directory
- $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{label}}$

#### Examples
- $\textcolor{red}{\text{SEMAT}}\textcolor{orange}{\text{0094}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious-games}}$
  - a subdirectory of repo4export containing all the files of the exercise SEMAT0094 (authored by SEMAT as indicated in the table _Registered authors_)
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}$
  - a subdirectory of repo4export containing all the files of the exercise EXG2131 (authored by INSA as indicated in the table _Registered authors_)
#### Legend
- $\textcolor{red}{\text{creator}}$ : creator question bank identifier (upper case alphabets [A-Z]), as registered in the table below
- $\textcolor{orange}{\text{id}}$ : id of the exercise (upper case numbers [0-9], unique inside the creator repository)
- $\textcolor{grey}{\text{label}}$ : label (only low-case alphabets [a-z], minus separated if necessary)

### Pattern for file
- $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{[.}}\textcolor{grey}{\text{label}}\textcolor{black}{\text{][-][}}\textcolor{blue}{\text{lang}}\textcolor{black}{\text{][.}}\textcolor{pink}{\text{type}}\textcolor{black}{\text{][.}}\textcolor{green}{\text{format}}\textcolor{black}{\text{].}}\textcolor{purple}{\text{extension}}$
  - in directory q4eef\banck\repor4exported\ $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{label}}$
#### Examples
- $\textcolor{red}{\text{SEMAT}}\textcolor{orange}{\text{0094}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious-games}}\textcolor{black}{\text{.}}\textcolor{green}{\text{aiken}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{txt}}$
  - a file containing an exercise (by default, the type is mcp and the language is english) created in the SEMAT repository, under id 1472.
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}\textcolor{black}{\text{.}}\textcolor{pink}{\text{matching}}\textcolor{black}{\text{.}}\textcolor{green}{\text{gift}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{txt}}$
  - a file containing a matching exercise in GIFT format stored in a txt file (for info, AIKEN does not support matching type).
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}\textcolor{black}{\text{-}}\textcolor{blue}{\text{fr}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{png}}$
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
To  let any creator choose its identification numbering of exercise (and yet have a unique id for any exercise in q4eef), a creator MUST have a creator id. This table list the creators already registered. To add a new creator, you can edit the table below in [this README.md file](https://github.com/frederic-baucher/q4eef/edit/main/README.md) (a new branch will be created and the q4eef needs to merge it before publication) or you can request before a write access [by filling a new issue](https://github.com/frederic-baucher/q4eef/issues/new) to this Github repository.

<!-- edit the table below by copy-pasting in https://www.tablesgenerator.com/markdown_tables -->
| author's id | author's bank product | bank's operator | author's reference      | facilitator's reference                                          |
|-------------|---------------|-----------------|-------------------------|------------------------------------------------------------------|
| SEMAT       | [Quizizz]       | _Saas_          | https://semat.org       | [Frédéric BAUCHER] |
| EXG         | [Moodle]        | [INSA-ROUEN]      | [Frédéric BAUCHER] |       |
| welcome     | new           | new             | you                                                                                | you   |

[INSA-ROUEN]: https://moodle.insa-rouen.fr
[Frédéric BAUCHER]: https://fr.linkedin.com/in/fr%C3%A9d%C3%A9ric-baucher-3026481a

<!--
How to color text in README.md

$\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{1472}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious}}$
_
$\textcolor{grey}{\text{game}} \textcolor{black}{\text{-}}\textcolor{blue}{\text{en}}\textcolor{black}{\text{.}}\textcolor{green}{\text{aiken}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{txt}}$

```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```

> __Warning__
> This is a warning.

> __Note__
> This is a note.
> 
-->

<!--

# Quizz taxonomies

| tools>                   | quizizz     | moodle          | kahoot | wooclap        | mentimeter | digitaliser |
|--------------------------|-------------|-----------------|--------|----------------|------------|-------------|
| multiple choice question | OK          | OK              | OK     |                | 2          |             |
| One choice question      |             |                 | OK     |                | 2          |             |
| true/false               | $           | OK              | OK     |                | 2          |             |
| matching                 | $ drag&drop | dropdown merged | N/A    | radio unmerged | N/A        |             |
| open                     |             | OK              |        |                |            |             |

# Display a map
```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "id": 1,
      "properties": {
        "ID": 0
      },
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
              [-90,35],
              [-90,30],
              [-85,30],
              [-85,35],
              [-90,35]
          ]
        ]
      }
    }
  ]
}
```


-->


