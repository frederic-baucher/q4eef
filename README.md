<!-- https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes -->
# q4eef

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
![Use case diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/frederic-baucher/q4eef/main/doc/usecases1.puml)

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
├── bank
│   ├── pivots4adapt
│   │   ├── getmarked
|   │   └── any_new_adapter...    
│   ├── ready2import
│   │   ├── kahoot
│   │   ├── moodle
│   │   ├── quizziz
│   │   ├── wooclap
│   │   └───any_new_tool_of_reuser ...             
│   └── repo4export
...
└── tools
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
bank
├── pivots4adapt
│   └── getmarked
│       └── SEMAT0094.serious_games.getmarked.txt
├── ready2import
│   ├── kahoot
│   │   ├── EXG2131.en.png
│   │   ├── EXG2131.scrum_in_essence_constructs.kahoot.xlsx
│   │   └── SEMAT0094.serious_games.kahoot.xlsx
│   ├── moodle
│   │   ├── EXG2131.scrum_in_essence_constructs.moodle.xml
│   │   └── SEMAT0094.serious_games.aiken.txt
│   ├── quizziz
│   │   ├── EXG2131.scrum_in_essence_constructs.quizizz.xlsx
│   │   └── SEMAT0094.serious_games.quizizz.xlsx
│   └── wooclap
│       ├── EXG2131.scrum_in_essence_constructs.moodle.xml
│       └── SEMAT0094.serious_games.moodle.xml
└── repo4export
    ├── EXG2131.scrum_in_essence_constructs
    │   ├── EXG2131.en.png
    │   ├── EXG2131.fr.png
    │   └── EXG2131.scrum_in_essence_constructs.matching.gift.txt
    └── SEMAT0094.serious_games
        └── SEMAT0094.serious_games.quizizz.html
```

## To go further
- [Creator's and Facilitator's Manual](creator.md)

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

<!--
# How to README.md

## How to color text in README.md

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


## Insert a geographic map
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




## Insert excerpt of files in README.md

```
https://github.com/frederic-baucher/q4eef/blob/f5c82be6d71f65c6cfb2e8caef1e51fe4a601fe5/README.md?plain=1#L14
```
https://github.com/frederic-baucher/q4eef/blob/f5c82be6d71f65c6cfb2e8caef1e51fe4a601fe5/README.md?plain=1#L14
.
.
.
.
.
```
https://github.com/frederic-baucher/q4eef/blob/2138e6129d5493369d7f65c617416258c2ab2c72/doc/usecases.puml?plain=#L36-L37
```
https://github.com/frederic-baucher/q4eef/blob/2138e6129d5493369d7f65c617416258c2ab2c72/doc/usecases.puml?plain=#L36-L37

-->


