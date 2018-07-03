---
layout: page
title: Day 4
permalink: /day4/
---
## Synopsis

Today we will go over recent textual scholarship relating to genetic criticism and social text theory. We will also survey two digital approaches for collating texts.

## Aims

- Understand the differences between eclectic and genetic text editing.
- Understand how "social text" theory changed the landscape of editing.
- A working knowledge of using TextLab to transcribe manuscripts.
- Familiarity with electronic collation options.

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

#### Customising the TEI: TEI and ODD

[Burnard](https://books.openedition.org/oep/692): "How should you go about choosing just the parts of the TEI you need? How should you communicate the particular TEI encoding choices you have made to others so that such integration remains possible?"

Schema: the document's grammar. Say you want a rule: every poem should be a collection of `<l>` tags with `@n` (numbered line attributes), and that each group of `<l>`s should be grouped under an `<lg>` tag specifying that it is a numbered stanza (`@n` again) and a `@type` attribute for indicating the length of the stanza (e.g., couplet, tercet, quatrain, &amp;c.).

Or suppose in a documentary editing project, we are encoding letters, and we want to make sure each `<date>` tag has a `@when` attribute, or that each `<p>` has an `@xml:id` (a good idea), or that each `<persName>` has a `@ref` to point to the `@xml:id` of the person.

A schema will codify all of those rules such that the xml document will not be valid unless each is followed. The ODD validates the TEI document.

How to customise?

* `tei_all`: Simple, yet not recommended, way is to use the TEI All (or, put another way, the null) schema. This says that you will use all available modules in the TEI.

* `tei_lite`: also, simple; also not recommended (by me, at least): this selects about 50 of the most common elements used in about 90 percent of existing projects.

Both tei_all and tei_lite documents can be selected when you open a new file in oXygen (to do this, select File > New > Framework Templates > TEI P5).

There are three good ways to create schema for your project:

1. Relax ng schema (built into TEI files on oXygen).
2. Schematron.
3. ODD.

The TEI has elements such as `<schemaSpec>`, `<moduleRef>`, `<elementSpec>`, `<classSpec>` (and others) combine formal XML declarations for inclusion in a DTD or Schema with detailed documentation and examples, for inclusion in a technical manual about the encoding scheme being specified. For this reason, a document using these elements is informally known as an ODD

ODD files (One Document Does it all) are TEI customisation files that serve as a source for the derivation of

* a formal TEI schema
* readable documentation of the project's TEI encoding choices

Now, going back to oXygen, open an ODD template file by choosing New > File > Framework Templates > TEI ODD > ODD Customization. What you see looks like a standard TEI file. It even has an TEI-XML namespace and a `<teiHeader>`:

```
<?xml version="1.0" encoding="UTF-8"?>
<TEI xmlns:xi="http://www.w3.org/2001/XInclude" xmlns:svg="http://www.w3.org/2000/svg"
  xmlns:math="http://www.w3.org/1998/Math/MathML" xmlns="http://www.tei-c.org/ns/1.0">
  <teiHeader>
    <fileDesc>
      <titleStmt>
        <title>Title</title>
      </titleStmt>
      <publicationStmt>
        <p>Publication Information</p>
      </publicationStmt>
      <sourceDesc>
        <p>Information about the source</p>
      </sourceDesc>
    </fileDesc>
  </teiHeader>
```
But what makes the ODD file is the `<schemaSpec>` element, which lists elements specifying which TEI modules we want as well as the elements and attribute rules.

```<text>
    <body>
      <schemaSpec ident="oddex1" start="TEI">
        <moduleRef key="header"/>
        <moduleRef key="core"/>
        <moduleRef key="tei"/>
        <moduleRef key="textstructure"/>
      </schemaSpec>
    </body>
  </text>
```
The `<moduleRef>` refers to a TEI module. There are currently 22 modules in the *TEI Guidelines* that match to a chapter. So, for example, the "header" module corresponds to [Chapter 2 of the TEI Guidelines on the "TEI Header"](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/HD.html).

What is happening above is simply a listing of four TEI modules to be included: "header", "core", "tei", and "textstructure". These are all required for TEI conformance, which is why they are in the ODD template file. Other optional modules include:

```
<moduleRef key="namesdates"/>
<moduleRef key="transcr"/>
<moduleRef key="analysis"/>
```

A module element makes available all the declarations allowed within the schema. Including the the `@include` and `@except` attributes will change this default structure.

So suppose you choose the optional module `<moduleRef key="analysis"/>` but you only want to use certain elements. You would check for the available elements in the module by going to the appropriate chapter in the Guidelines, which happens to be Chapter 17. The end of the chapter includes a helpful module analysis, which indicates:

>**Module analysis: Simple analytic mechanisms** Elements defined: c cl interp interpGrp m pc phr s span spanGrp w
Classes defined: att.global.analytic att.linguistic

This tells you what elements are available and what class these belong to. But if we only want to use phrase- and word-level elements (`<s>, <phr>, and <w>`) in our document (and none of the interpretive stuff), we could write a <moduleRef> thus:

```
<moduleRef key="analysis" include="s phr w"/>
```
Or, if you're really clear about the elements you want, exclude what you do not want:
```
<moduleRef key="analysis" exclude="c cl interp m pc span spanGrp"/>
```

Burnard notes a very good example of how the TEI can be constrained by ODD. The EpiDoc Guidelines wanted to constrain the vocabulary of `@type` attributes in `<div>` elements. So within their `<schemaSpec>` you will notice:

```
<elementSpec
  ident="div"
  mode="change"
  module="textstructure">
 <attList>
  <attDef
    ident="type"
    mode="replace"
    usage="req">
   <valList type="closed">
    <valItem ident="apparatus">
     <desc>to contain apparatus criticus or textual notes</desc>
    </valItem>
    <valItem ident="bibliography">
     <desc>to contain bibliographical information, previous publications,
           etc.</desc>
    </valItem>
    <valItem ident="commentary">
     <desc>to contain all editorial commentary, historical/prosopographical
           discussion, etc.</desc>
    </valItem>
    <valItem ident="edition">
     <desc>to contain the text of the edition itself; may include multiple
           text-parts</desc>
    </valItem>
    <valItem ident="textpart">
     <desc>used to divide a div[type=edition] into multiple parts (fragments,
           columns, faces, etc.)</desc>
    </valItem>
    <valItem ident="translation">
     <desc>to contain a translation of the text into one or more modern
           languages</desc>
    </valItem>
   </valList>
  </attDef>
 </attList>
</elementSpec>
```
One could also add a new element, which we will do today. You just add an `<elementSpec>`, but you also need to consider whether the non-TEI elements belongs in a certain class. You need to think about content models and how other elements are defined within those models.

Burnard: "one of the purposes of the TEI Guidelines is to guide encoding practice ... it tells you how to communicate what you have done to others."

Why are we doing this? Aren't we jumping ahead a bit on the TEI?

Answer: Possibly, but the TEI is very difficult to learn in a few days (in a few years, even), and with ODD you engage with the Guidelines in a more critical way. Moreover, it is inevitable that projects will decide to encode different things in different ways. For example, some projects might consider it very important to label each rhyme word within a poem's lines with `<rhyme>` and `@label`, and they will want to include `@type` and `@rhyme` attributes in their supervening `<lg>` elements:

```
<!-- from Alexander Pope's *Essay on Criticism* -->
<lg type="couplet" rhyme="ab">
  <l>Speak silent when you Doubt your <rhyme label="a">Sense,</rhyme></l>
  <l>And speak, tho' Sure, with <hi rend="italic">Seeming</hi> <rhyme label="b">Diffidence.</rhyme></l>
</lg>
```

Other poetry projects will not use any rhyming identifiers, as they may simply want to record, say, textual features such as variant readings. Burnard also gives a [good example](https://books.openedition.org/oep/692#tocfrom1n3) of the various ways editors will encode person names.

The ODD approach allows you to communicate exactly what encoding decisions you made, how you constrained them for consistency, and how you envision what is important in your document model. This benefits other researchers doing similar projects as well as the TEI, which is community-driven.

The TEI also offers a web application called [Roma](http://www.tei-c.org/Roma/) to build ODDs.

TEI/ODD Exercise:

* open the ODD Customization file.
* identify which modules you will need for letters and journals.
* create rules for attribute values that can be used.
* invent two new elements.

For more information on writing ODDs, consult Syd Bauman and Julia Flanders's [documentation](http://www.wwp.neu.edu/outreach/seminars/uvic_advanced_2016/presentations/basic_odd/basic_odd_simple_00.xhtml). We will also return to this topic on Day 4.

#### Problems with TEI; alternative markup with LMNL

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
