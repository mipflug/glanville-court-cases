# Glanville-Court-Cases
## Introduction
This repository contains in-progress XML files of transcribed court documents pertaining to the entomologist Eleanor Glanville (1655-1709).
Approximately 35 court cases were photographed by Michele D. Pflug at the UK National Archives in summer 2022. I began transcribing the largest case, Ashfield v. Goodricke (C5/222/25) in fall 2022 in Eugene, Oregon. Encoding began in Spring 2023 using Leaf-Writer.

This project has been supported by the following institutions:
American Society for Eighteenth Century Studies, Graduate Women International, Oregon Humanities Center, Center for the Study of Women and Society, 
University of Oregon Global Studies Institute, and the Department of History at the University of Oregon.

XML files are for research purposes only. Do not publish, reproduce, or distribute the content in any way.

### Contact Information
Principal Researcher: Michele D. Pflug, PhD Candidate, Department of History, mpflug@uoregon.edu

## Methodology
### Transcribing Conventions
- Transcriptions were made using Notion code blocks. I chose this option because the code blocks were linked to her Notion index of primary sources and her notion biography index. Transcribing in Notion made retrieval easier.
- Transciptions followed the semi-diplomatic editorial conventions in Healther Wolfe's [Alphabet Book](https://folgerpedia.folger.edu/mediawiki/media/images_pedia_folgerpedia_mw/7/79/AlphabetBook2020.pdf)
- exceptions include: "ff" transcribed as "F", "u/v" are modernized, "i/j" are modernized, and unknown letters are transcribed as "x"
- Notion does not have a superscript function in code blocks, so I enclosed interlinear insertions in <add>example</add>
- IMG numbers, folio numbers, recto/verso, and textual notes recorded in //

### Folder and File Naming Conventions
Folder and file naming conventions follow the structure of the archive. The structure of Chancery Court case records can be broken down by class, box, and piece. 

For example, C5/222/25 = 
- C5 = class 5
- 222 = box 222
- 25 = piece 25

In this repository, each court record has its own folder. The folder name for the above record is C5-222-25.

Each piece often contains multiple folios. For the records involved in this project, The National Archives do not record folio numbers in their catalogue or on the documents. I have assigned folio numbers based in order of appearance.

The case C5/222/25 is unique in that it consists of 2 pieces, both labelled 25, but only 1 piece is catalogued. For my own record keeping purposes, I have divided the pieces into "bundle 1" and "bundle 2" with non-continuous foliation. So C5-222-25-b-1-f-4 = Class 5, box 222, piece 25, bundle 1, folio 4. Additionally, I have supplied my own titles for each folio and appended the title to the reference number of the file, following the convention DocumentType-litigant. For example, C5-222-25-b-1-f-4-complaint-ashfield.xml = Class 5, box 222, piece 25, bundle 1, folio 4, complaint of Edmund Ashfield.

### Encoding Conventions
In March 2022, I began encoding documents [LEAF-Writer editor](https://leaf-writer.leaf-vre.org/), following TEI P5 Guidelines. The following
resources were used: 

- [MsDesc](https://msdesc.github.io/consolidated-tei-schema/msdesc.html)
- [Text Encoding Initiative](https://tei-c.org/release/doc/tei-p5-doc/en/html/MS.html)

The first iteration of encoding captures key textual features recorded in the Notion code blocks. I prioritized features not retained when copied and pasted into an XML editior. Tags used in the first iteration include:

- `<lb/>` = line break
- `<expan>` = expanded abbreviation
- `<unclear>` = unclear or missing text. Any letters supplied are approximate guesses.
- `<p>` = paragraph breaks
- `<del>` = deletion
- `&amp;` = &

The process followed the following steps sequentially:
- add `<lb/>` and `<p>` directly in Notion
- copy and paste into MS Word. In order to retain formatting features from Notion, hit `CMD + A` to copy rather than clicking the copy button. I chose to use MS Word because it has advanced find & replace options based on formatting. 
- In MS Word, find and replace `<lb/>` with `<lb/>^p` --the ^p adds an enter after the `<lb/>`
- find and replace `<p>` with `<p>^p`. Repeat for closed tag.
- find and replace `&` with `&amp;`
- find and replace [ with `<unclear>`
- find and replace ] with `</unclear>`
- advanced find and replace `italics` with `<expan>^&</expan>`
- advanced find and replace `strikethrough` with `<del>^&</del>`
- copy and paste into Visual Studio Code to validate. Very occassionaly, improper nesting occured with the `<unclear>` and `<expan>` tags. VSC highlights these errors. I fixed the errors in MS Word and validated again in VSC.
- open new blank template file in leaf-writer
- save file via GitHub according to file naming conventions
- copy and paste from VSC into Leaf-Writer `edit Raw XML` view.
- click `change`
