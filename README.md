$\textcolor{red}{\text{creator}}\textcolor{orange}{\text{id}}\textcolor{grey}{\text{label}}\textcolor{blue}{\text{lang}}$

$\textcolor{red}{\text{EXG}}\textcolor{orange}{\text{1472}}$


# q4eef

# Quizz taxonomies

<!-- if needed, a nicer edition is possible by copy-paste on https://www.tablesgenerator.com/markdown_tables -->
| tools>                   | quizizz     | moodle          | kahoot | wooclap        | mentimeter | digitaliser |
|--------------------------|-------------|-----------------|--------|----------------|------------|-------------|
| multiple choice question | OK          | OK              | OK     |                | 2          |             |
| One choice question      |             |                 | OK     |                | 2          |             |
| true/false               | $           | OK              | OK     |                | 2          |             |
| matching                 | $ drag&drop | dropdown merged | N/A    | radio unmerged | N/A        |             |
| open                     |             | OK              |        |                |            |             |

# Reuser tools

# Creator tools

|         | type(s)   | format preferred (first) | preferred (second) |
|---------|-----------|-------------------|--------------------|
| moodle  | MCQ       | aiken             | moodle_xml         |
|         | Matching  | moodle_xml        |                    |
| quizizz | MCQ       | [quizizz Excel](doc/export_from_quizizz.md)     |                    |
|         | Matching$ | not tested            |                    |

## Naming convention
Any exercise is exported in file that MUST BE COMPLIANT with the naming convention
- creator repository identifier (upper case alphabets [A-Z])
- id of the exercise (upper case numbers [0-9], unique inside the creator repository)
- label (only low-case alphabets [a-z] underscore separated if necessary)
- language
- format name (among the format list)
- format extension (xlsx, txt, csv, ...)

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


