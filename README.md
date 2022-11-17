# q4eef

# Introduction 

## Usage
q4eef is a solution for sharing Essence exercises and support the Essence adoption in education.

### Glossary
The actors of this solution are :
- __creator__ : any teacher, consultant, ... willing to share with q4eef an exercise she/he created in a Questions_Bank of her/his choice (Moodle, ...).
- __reuser__ : any teacher that wants to reuse exercise stored in q4eef
- __moderator__ : designated teacher(s) monitoring the access to q4eef
- __maintainer__ : any creator or moderator that generate the target pivots

Other terms :
- __native pivot__ : file exported from the creator tool
- __target pivot__ : file to be imported in the reuser tool (in case the creator and the reuser have the same export and import format respectively), the target pivot is a copy of the native pivot.

Use cases :
- Convert exercise : in case the exported format is not very convenient as a native pivot (like [Quizizz](https://github.com/frederic-baucher/q4eef/blob/main/doc/export_from_quizizz.md)), the creator can convert it with a dedicated tools (regex tools, spreadsheet, ...).

### Diagram
![Use case diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/frederic-baucher/q4eef/main/doc/usecases.puml)

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

# Creator tools

## Recommended export by creator tools
|         | type(s)   | format preferred (first) | preferred (second) |
|---------|-----------|-------------------|--------------------|
| moodle  | MCQ       | [aiken]           | [moodle_xml]         |
|         | Matching  | [gift]        | [moodle_xml]                   |
| quizizz | MCQ       | [quizizz Excel]   |                    |
|         | Matching  | [not tested]            |                    |

[aiken]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/aiken.md
[gift]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/gift.md
[moodle_xml]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/moodle_xml.md
[quizizz Excel]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/quizizz_excel.md
[not tested]: https://github.com/frederic-baucher/q4eef/blob/main/doc/formats/not_tested.md

## Storage repository : pivots
The file exported from the creator tool has to be stored in the [__native pivots__](https://github.com/frederic-baucher/q4eef/tree/main/bank/repo4export) directory of this Github repository. Any additional file (for instance, images) has to be stored in the same place. All the files must follow the __q4eef naming convention__.

## Naming convention : q4eef
Any exported exercise file __MUST__ have a name __COMPLIANT__ with the naming convention.

### Pattern
- $\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{label}}\textcolor{black}{\text{[-}}\textcolor{blue}{\text{lang}}\textcolor{black}{\text{][.}}\textcolor{pink}{\text{type}}\textcolor{black}{\text{][.}}\textcolor{green}{\text{format}}\textcolor{black}{\text{].}}\textcolor{purple}{\text{extension}}$
### Example
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{1472}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{serious-games}}\textcolor{black}{\text{.}}\textcolor{green}{\text{aiken}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{txt}}$
  - a file containing an exercise (by default, the type is mcp and the language is english) created in the EXG repository, under id 1472.
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}\textcolor{black}{\text{.}}\textcolor{pink}{\text{matching}}\textcolor{black}{\text{.}}\textcolor{green}{\text{gift}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{txt}}$
  - a file containing a matching exercise in AIKEN format stored in a txt file
- $\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{2131}}\textcolor{black}{\text{.}}\textcolor{grey}{\text{scrum-in-essence-constructs}}\textcolor{black}{\text{-}}\textcolor{blue}{\text{fr}}\textcolor{black}{\text{.}}\textcolor{purple}{\text{png}}$
  - a file containing an image localised in french to be used with exercise EXG2131
### Legend
- $\textcolor{red}{\text{creator}}$ : creator question bank identifier (upper case alphabets [A-Z]), as registered in the table below
- $\textcolor{orange}{\text{id}}$ : id of the exercise (upper case numbers [0-9], unique inside the creator repository)
- $\textcolor{grey}{\text{label}}$ : label (only low-case alphabets [a-z] underscore separated if necessary)
- $\textcolor{blue}{\text{lang}}$ : language code compliant with ISO 639-1 (default : en)
- $\textcolor{pink}{\text{type}}$ : type of exercise (default : mcq) 
- $\textcolor{green}{\text{format}}$ : logical format name (among the format list)
- $\textcolor{purple}{\text{extension}}$ : technical format name (xlsx, txt, csv, ...)

## Registered creators
To  let any creator choose its identification numbering of exercise (and yet have a unique id for any exercise in q4eef), a creator MUST have a creator id. This table list the creators already registered. To add a new creator, you can edit the table below in [this README.md file](https://github.com/frederic-baucher/q4eef/edit/main/README.md) (a new branch will be created and the q4eef needs to merge it before publication) or you can request before a write access [by filling a new issue](https://github.com/frederic-baucher/q4eef/issues/new) to this Github repository.

| id      | creator's tool | tool's operator | creator reference                                                          |
|---------|----------------|-----------------|----------------------------------------------------------------------------|
| EXG     | Moodle         | INSA-ROUEN      | [Frédéric BAUCHER](https://fr.linkedin.com/in/fr%C3%A9d%C3%A9ric-baucher-3026481a) |
| welcome | new            | new             | you                                                                        |

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

-->


