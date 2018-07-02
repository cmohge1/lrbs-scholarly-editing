---
layout: page
title: day 4
permalink: /day4/
---
## Synopsis

Today we will survey two digital approaches for collating texts.

### Day 4 (Thursday, 5 July)

Time | Topic | Type |
:----|:------|:-----|
9.30 | Seminar 9: Genetic criticism, genetic editing, fluid text editing | Presentation, Discussion |
11.30 | Seminar 10: Using TEI to mark-up versions of texts with TextLab | Digital lab  |
14.00 | Seminar 11: Customising the TEI; problems with TEI; alternative markup with LMNL; Computer-Assisted Collation Overview | Discussion; Digital lab |
16.00 | Library Time |             |

### Seminar 9: Genetic criticism, genetic editing, fluid text editing

### Readings

1. McGann, *Critique of Modern Textual Criticism*.
2. Bryant, *The Fluid Text*.

Social text/sociology of text.

### Seminar 10: Using TEI to mark-up versions of texts with TextLab

<details><summary>General Instructions</summary>

<p>1. Go to <https://app.textlab.org/users/sign_in> and click "Sign Up." Enter your details and make sure to select "University of London" under "Institutional Sponsor."</p>

<p>2. Find “Bow in the Cloud” and click "Edit."</p>

<p>3. Find your Image number on the left-hand pane and click on it.</p>

<p>4. Click on "New" on the right-hand side of the editing pane. Enter the name of your file in the following format bic_leaf[number_your initials]</p>

<p>5. Transcribe the text (all of it).</p>

<p>* setting up the leaf's structure: select the "milestone" box, and input the appropriate unit (leaf) number.</p>

<p>* link the leaf image to the transcription by clicking on the "pb" box.</p>

<p>* select the "ab" box (which will surround the text transcription).</p>

<p>* transcribe all of the metamarks first, then focus on transcribing the whole text.</p>

<p>6. Draw boxes around each of the revision or metamark sites. As you do so, highlight the transcribed text of the revision, then double-click on the box (near the number) of its corresponding revision site box. Enter the appropriate TEI encoding.</p>

<p>For an example of the first stanza of a poem, “The Grave of Wilberforce” (leaf 24), <a href="https://christopherohge.com/grave-of-wilberforce.xml">click here</a> (right click and download the file ("Save link as"), or click on the link, right click, and select "View Page Source").</p>

<p>7. When finished with the transcription, click "Submit."</p>

<p>8. After submission, the editor will review the leaf.</p>

<p>9. Once it is accepted and re-shared, one can then input revision narratives.</p>

<p>10. To create a revision narrative, double-click on the boxed revision site, and click "New sequence." The top level will show the zone number of the box and the bottom will allow to compose a revision narrative.</p>
</details>

### Seminar 11:

#### Customising the TEI; problems with TEI; alternative markup with LMNL

#### Reading

1. [Wendell Piez, "TEI in LMNL: Implications for Modeling"](https://journals.openedition.org/jtei/1337) (*jTEI*, 2014)

<details><summary>Exercise 1</summary>

<p>Return to the poem you marked up on Day 1, Edward Thomas's "The Child on the Cliffs." Either open the original text file, and paste the text into a blank xml file in oXygen, or use your file that was converted from markdown to xml.</p>

<p>Say we would like to mark up all instances of speakers with `<speaker>` tags (for more on this see the [TEI Guidelines](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/DR.html#DRSP)).</p>

<p>What happens to the XML validation?</p>
</details>
<br />
Customising TEI in your ODD file.

*An alternative markup:* **LMNL**. LMNL (the Layered Markup and Annotation Language) is a non-hierarchical markup language developed by Wendell Piez.

The document consists of text and a sequence of atoms (mostly characters) with ranges (subsequences) applied to the text. Atoms and ranges may be named and annotated just like xml elements. Text ranges may or may not correspond to each other: the text retains tag types but loses the well-formedness rules of xml. This gives you the ability to retain many of the structural features of xml but with overlapping hierarchies. Therefore, Piez designed LMNL so that it could be implemented with XML.

Alternative markups such as LMNL are best used when the the XML or TEI-XML cannot serve the project's purposes. It is also best to only use alternative markup on small- to medium-scale projects (LMNL, for example, does not provide validation rules like XML does).

<details><summary>Exercise 2</summary>

Return to the text file of ["The Child on the Cliffs," by Edward Thomas](../thomas_edward_child_on_the_cliffs.txt) and mark up the speakers (and any other features) in LMNL.

How does that compare to TEI encoding?

</details>

#### Computer-Assisted Collation

The traditional method of collation has been tedious: you literally read versions of texts side-by-side and note the differences in a collation table.

The Hinman collater.

In most cases, machine-collation can detect differences that human eyes often miss: punctuation differences, capitalization, even entire lines of text. Two very effective methods of machine-collation can be achieved with Juxta and Collatex. Juxta is easier to use, and quite effective, but it lacks flexibility, and some texts require a lot more nuanced treatment. For more bespoke text projects with a lot of textual variation, Collatex is an ideal program. It is faster and fully customizable, yet it lacks the accessible interface of Juxta. Like any other editorial project, your decision of what to use depends on your documents, and how you would like to present those documents.

### Juxta Commons

Juxta Commons is a web-based interface for comparing versions of texts and creating editions from those versions.

<details><summary>Instructions</summary>

* Go to [Juxta Commons](http://www.juxtacommons.org/) (http://www.juxtacommons.org/)
* Create a [free account](http://www.juxtacommons.org/signup)
(http://www.juxtacommons.org/signup)
* Go to the Day4 file repository and download [TBD]. If you already have some versions of a text prepared, feel free to use those.
* Click on "Add Source" (top-left of the screen) and upload the files you just downloaded.
* When you have uploaded your sources, under "Sources" click on the right arrow ("Prepare Witness"). The source will then appear in the top-middle pane, "Witnesses."
* Select the witnesses that you would like to compare by clicking on the box next to its title and then "Create set" (you will then select "Create with Witnesses").
* Add the appropriate metadata to the set, then click "Create and collate".

A good example of an edition using Juxta: The [Fluid Text edition of Herman Melville's *Moby-Dick*](https://mel.hofstra.edu/expurgating-moby-dick.html).

For a more detailed user guide, go to <http://www.juxtacommons.org/guide?nocontrols#screencast>.
</details>

### CollateX

Download Python 3, preferably the Anaconda distribution

* pip install --pre collatex
* pip install python-levenshtein (but see the note below for Windows)
* pip install graphviz (either through a package manager such as apt-get or MacPorts, or go to http://www.graphviz.org/Download.php and accept the license)
* pip install graphviz

If these instructions do not make sense, consult [David Birnbaum's site](http://collatex.obdurodon.org/installation.xhtml).

A good example of a Collatex collation: the Samuel Beckett manuscript project.
