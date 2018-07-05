---
layout: page
title: Day 4
permalink: /day4/
---
## Synopsis

Today we will finish the exercise on encoding textual apparatus and annotation. Then we will go over recent textual scholarship relating to genetic criticism and social text theory. We will also survey two digital approaches for collating texts.

## Aims

- Encode an app crit, witness list, and annotations.
- Knowledge of schemas, ODDs, and why we use them.
- Understand the differences between eclectic and genetic text editing.
- Understand how "social text" theory changed the landscape of editing.
- A working knowledge of using TextLab to transcribe manuscripts.

### Day 4 (Thursday, 5 July)

Time | Topic | Type |
:----|:------|:-----|
9.30 | Seminar 9: Writing and encoding textual apparatus and annotation | Presentation, Discussion |
11.30 | Seminar 10: Intro to genetic criticism, genetic editing, fluid text editing | Digital lab  |
14.00 | Seminar 11: Using TEI to mark-up versions of texts with TextLab | Digital lab |
16.00 | Library Time |             |

### Seminar 9:

#### Writing and encoding annotation

Remember that the essence of the app crit in TEI is the `<app>` element, which contains at least `<rdg>` elements with `@wit` attributes. If you would like to replicate Ricks's app crit, you'll want to also nest a `<lem>` element (a lemma) so that you can represent the preferred reading (the lemma) which points to its variants. More information about app crit in TEI can be found in [Chapter 12](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/TC.html) of the *TEI Guidelines*.

Thankfully annotation is a bit simpler: for many projects a `<note>` TEI element will suffice (for more, consult the [Guidelines](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-note.html)).

The way you encode your annotations will depend on how you want the notes to be structured, and where you will want the notes to appear in your interface. Many projects will create a linking system for note-writing. As a simple example from the Cranch Journal project (which we examined on Day 2), the note system is constructed this way:

```
I must "see into the life of <lb/>things."<ptr target="#note9" xml:id="nr9"/>
```
Within the text I have created a `<ptr>` element with a `@target` attribute that points to the `<back>` element near the end of the file:

```
<back>
         <div type="notes">
         ... <!--skipping ahead to note 9-->

         <note xml:id="note9">"see into the life of things"] From Wordsworth's "Lines Written a
               Few Miles Above Tintern Abbey" ... </note>
```

The `<ptr>` element uses a # mark to indicate that we are going to move to another place in the file: in this case, it is to find the `@xml:id="note9"` which is properly encoded as a note in the back matter of the edition file. This essentially structures a system of footnotes (or endnotes) that link you away from the reading text.

OK, but why did the `<ptr>` element include its own `@xml:id`?

Another way to do this is evidenced by a Mark Twain edition file:

#### Exercise

1. Return to your TEI-encoded text of Tennyson's "Early Spring."
2. Now have a look at [Christopher Ricks's edition](../readings/tennyson_early-spring-Ricks-edition.pdf) of Tennyson and take a moment to study the app crit of "Early Spring".
3. Within the `<text>` of your xml file, create an app crit using Ricks's example.
4. Create a personography within your file. Create entries (and `@xml:id`s) for Tennyson and Ricks (does not have to be complete).
5. Create a note to reproduce Ricks's textual headnote (hint: treat like you would an explanatory note: create a `<back>` element).
6. Create a short explanatory note about some aspect of the poem.

If you would like to consult the Senate House Library's manuscript of "Early Spring," you can download it [here](../readings/early-spring-ms.pdf).

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
Suppose I want a new element that is not available in the TEI? Like, say, an `<alliteration>` element for the poem above?

```
<elementSpec ident=”alliteration” mode=”add”>
    <classes>
      <memberOf key=”att.interpLike”/>
    </classes>
  </elementSpec>
```

You will now be able to have a valid `<alliteration>` element that you have added to an "interpLike" class, which is to say interpretive class.

Other poetry projects will not use any rhyming identifiers, as they may simply want to record, say, textual features such as variant readings. Burnard also gives a [good example](https://books.openedition.org/oep/692#tocfrom1n3) of the various ways editors will encode person names.

The ODD approach allows you to communicate exactly what encoding decisions you made, how you constrained them for consistency, and how you envision what is important in your document model. This benefits other researchers doing similar projects as well as the TEI, which is community-driven.

The TEI also offers a web application called [Roma](http://www.tei-c.org/Roma/) to build ODDs.

For more information on writing ODDs, consult Syd Bauman and Julia Flanders's [documentation](http://www.wwp.neu.edu/outreach/seminars/uvic_advanced_2016/presentations/basic_odd/basic_odd_simple_00.xhtml).

### Seminar 10:
#### Genetic criticism, genetic editing, fluid text editing

### Readings

1. McGann, *Critique of Modern Textual Criticism*.
2. Bryant, *The Fluid Text*.

Some distinctions:

1. New Bibliography (Greg, Bowers, Gaskell––wait? Gaskell?).
2. Sociology of Text (McKenzie, McGann).
3. Genetic editing (Gabler, Sealts–Hayford, Bryant et al).

###Seminar 11:

#### Using TEI to mark-up versions of texts with TextLab

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
