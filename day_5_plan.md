---
layout: post
title: Day 5
permalink: /day5.html
---

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=3 orderedList=false} -->
<!-- code_chunk_output -->

* [Aims](#aims)
* [Schedule: Day 5 (Friday, 6 July)](#schedule-day-5-friday-6-july)
	* [Seminar 12: Problems with TEI; alternative markup with LMNL](#seminar-12-problems-with-tei-alternative-markup-with-lmnl)
	* [Computer-Assisted Collation](#computer-assisted-collation)
	* [BONUS material: An XPath and XSLT Primer](#bonus-material-an-xpath-and-xslt-primer)
	* [A Meditation on Digital Editions](#a-meditation-on-digital-editions)

<!-- /code_chunk_output -->

Today will introduce two technologies for transforming xml documents: XPath and XSLT. It will then conclude with a workshop on TextLab, a web-based xml transcription tool that includes TEI, XSLT, and word-and-image correspondence.

## Aims

- Familiarity with alternative markup options.

- Ability to perform electronic collation.

- A facility with searching xml nodes with XPath.

- A basic understanding of how to transform xml documents.

## Schedule: Day 5 (Friday, 6 July)

Time     | Topic                               | Type                    |
:--------| :---------------------------------- |:------------------------|
9.30 | Seminar 12: Problems with TEI; alternative markup with LMNL; Computer-Assisted Collation Overview; Quick introduction to XPath and XSLT | Presentation, Digital lab |
11.30 | Seminar 13: Open discussion on publishing digital editions; course review | Discussion |

### Seminar 12: Problems with TEI; alternative markup with LMNL

#### Reading

1. [Wendell Piez, "TEI in LMNL: Implications for Modeling"](https://journals.openedition.org/jtei/1337) (*jTEI*, 2014)

If you return to the poem you marked up on Day 1, Edward Thomas's "The Child on the Cliffs." Either open the original text file, and paste the text into a blank xml file in oXygen, or use your file that was converted from markdown to xml.

Say we would like to mark up all instances of speakers with `<speaker>` tags (for more on this see the [TEI Guidelines](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/DR.html#DRSP)).

What happens to the XML validation?

Customising TEI in your ODD file.

*An alternative markup:* **LMNL**. LMNL (the Layered Markup and Annotation Language) is a non-hierarchical markup language developed by Wendell Piez.

The document consists of text and a sequence of atoms (mostly characters) with ranges (subsequences) applied to the text. Atoms and ranges may be named and annotated just like xml elements. Text ranges may or may not correspond to each other: the text retains tag types but loses the well-formedness rules of xml. This gives you the ability to retain many of the structural features of xml but with overlapping hierarchies. Therefore, Piez designed LMNL so that it could be implemented with XML.

Alternative markups such as LMNL are best used when the the XML or TEI-XML cannot serve the project's purposes. It is also best to only use alternative markup on small- to medium-scale projects (LMNL, for example, does not provide validation rules like XML does).

Exercise 1

Mark up the Thomas poem in LMNL and make sure to encode the speakers (and any other features) you may find interesting.

How does that compare to TEI encoding?

### Computer-Assisted Collation

The traditional method of collation has been tedious: you literally read versions of texts side-by-side and note the differences in a collation table.

The Hinman collater.

In most cases, machine-collation can detect differences that human eyes often miss: punctuation differences, capitalization, even entire lines of text. Two very effective methods of machine-collation can be achieved with Juxta and Collatex. Juxta is easier to use, and quite effective, but it lacks flexibility, and some texts require a lot more nuanced treatment. For more bespoke text projects with a lot of textual variation, Collatex is an ideal program. It is faster and fully customizable, yet it lacks the accessible interface of Juxta. Like any other editorial project, your decision of what to use depends on your documents, and how you would like to present those documents.

#### Juxta Commons Exercise

Juxta Commons is a web-based interface for comparing versions of texts and creating editions from those versions.

<strong>Instructions</strong>

* Go to [Juxta Commons](http://www.juxtacommons.org/) (http://www.juxtacommons.org/)
* Create a [free account](http://www.juxtacommons.org/signup)
(http://www.juxtacommons.org/signup)
* Download the two versions of Mark Twain's "A Scrap of Curious History"
  * [Holograph manuscript transcription (c. 1894)](../readings/a-scrap-of-curious-history-ms.txt)
  * [1914 published text](../readings/a-scrap-of-curious-history-harpers-1914.txt)

If you already have some versions of a text prepared, feel free to use those.
* Click on "Add Source" (top-left of the screen) and upload the files you just downloaded.
* When you have uploaded your sources, under "Sources" click on the right arrow ("Prepare Witness"). The source will then appear in the top-middle pane, "Witnesses."
* Select the witnesses that you would like to compare by clicking on the box next to its title and then "Create set" (you will then select "Create with Witnesses").
* Add the appropriate metadata to the set, then click "Create and collate".

A good example of an edition using Juxta: The [Fluid Text edition of Herman Melville's *Moby-Dick*](https://mel.hofstra.edu/expurgating-moby-dick.html).

For a more detailed user guide, go to <http://www.juxtacommons.org/guide?nocontrols#screencast>.

#### CollateX

Download Python 3, preferably the Anaconda distribution

* pip install --pre collatex
* pip install python-levenshtein (but see the note below for Windows)
* pip install graphviz (either through a package manager such as apt-get or MacPorts, or go to http://www.graphviz.org/Download.php and accept the license)
* pip install graphviz

If these instructions do not make sense, consult [David Birnbaum's site](http://collatex.obdurodon.org/installation.xhtml).

A good example of a Collatex collation: the [Samuel Beckett manuscript project](www.beckettarchive.org/).

### BONUS material: An XPath and XSLT Primer

(TBD)

### A Meditation on Digital Editions

#### Readings

(TBD)

1. Hans Walter Gabler, "Theorising the Digital Edition."
2. [Paul Eggert on Interfaces]
