---
layout: page
title: Day 2
permalink: /day2/
---

## Synopsis

Today will feature an introduction to documentary editing, an introduction to the Text Encoding Initiative (TEI), and a demonstration of documentary editing with Senate House Library manuscripts.

## Aims

- Understand the difference between documentary editing and other forms of editing.
- General grasp of the Text Encoding Initiative and TEI schemas.
- Understanding of modelling texts.

## Schedule

### Day 2 (Tuesday, 3 July)

Time  | Topic                                                                  | Type
:---- | :--------------------------------------------------------------------- | :-----------------------
9.30  | Seminar 3: Documentary Editing; Introduction to the Text Encoding Initiative (TEI)                                        | Presentation, Discussion |
11.30 | Seminar 4: Text modelling; TEI and ODD | Presentation, discussion |
14.00 | Seminar 5: Building ODD for Documentary Editions: letters and journals | Digital lab              |
16.00 | Library Time                                                           | Presentation             |

#### Seminar 3

#### Readings

1. G. Thomas Tanselle, ["The Editing of Historical Documents."](/readings/tanselle_editing_historical _documents.pdf)
2. Lou Burnard's [*What is the TEI?*](https://books.openedition.org/oep/426)
3. James Cummings, ["The Text Encoding Initiative and the Study of Literature"](http://www.digitalhumanities.org/companion/view?docId=blackwell/9781405148641/9781405148641.xml&chunk.id=ss1-6-6&toc.depth=1&toc.id=ss1-6-6&brand=9781405148641_brand)
4. Elena Pierazzo, *Digital Scholarly Editing* (Chapter 2).

#### Documentary Editing
To make a long article short: transcribe as much as possible.

Yet: one cannot transcribe everything. As soon as transcription happens, an element of contingency comes into the text.

[Example 1: Mark Twain's notebooks and journals. Access slides here.](/Day2/mark-twain-journals.pdf)

[Example 2: Christopher Cranch's 1834 travel journal](http://scholarlyediting.org/2014/editions/cranchjournal.html)

#### Introduction to the Text Encoding Initiative (TEI)

[Access the TEI intro slides here.](/Day2/TEI-intro-slides.html)

#### Seminar 4

#### Text Modelling

"[E]very electronic representation of text is an interpretation" (Paul Eggert, *Securing the Past*, Cambridge UP, 2009).

And an argument, many say. Are these points obvious, or absurd?

Modelling: Our notions of modelling a text are really inherent in textual editing activities, but the theorising about modeling could point back to Willard McCarty's insistence on the centrality of modelling in digital humanities projects (see his *Humanities Computing*, Palgrave, 2005).

Patrick Sahle's model (of text modelling):

![Sahle_model](/day2/patrick_sahle_modelling.jpg)

(For the full slideshow, go to <http://dixit.uni-koeln.de/wp-content/uploads/2015/04/Camp1-Patrick_Sahle_-_Digital_Modelling.pdf>. And for his essay on the subject, click go to <https://www.openbookpublishers.com/htmlreader/978-1-78374-238-7/ch2.xhtml>.)

What do you think?

Sahle also provided a useful distinction of the 'digitised' versus the 'digital' edition. A work that is 'digitised' tends to mimic the codex––it is a page by page rendering. This form of digitisation is usually a PDF or even a hypertext marked up in html. But it is not interactive. A digital edition can only fully function in the digital realm––that is, if you have to print a digital edition, the edition would lose its functionality. The digital edition is more interactive  

What really distinguishes the two?

*Textons* versus *scriptons*: one of the distinguishing features of digital editing. A *texton* is all of the data that appears in the text file, while a *scripton* is the text as it appears to the user of the edition (see Pierazzo, Digital Scholarly Editing, p. 34). Put another way, it is raw source data versus the output that users see in the interface.

For example: in a recent documentary editing project on incoming letters to Mark Twain as part of an 1884 April Fools joke, each person is tagged with a pointer to a "personography" (a TEI file listing biographical information):

```
<text type="letter">
    <body>
      <pb facs="smith01.jpg" xml:id="pb0001" n="1"/>
      <head type="metadata">
        <name corresp="#JHS">J. Hyatt Smith</name> to <addressee>
          <name corresp="#SLC">Samuel L. Clemens</name>
        </addressee>
        <date when="1884-03-28">28 March 1884</date> &#8226; <name type="place">Brooklyn, N.Y.</name>
        <sourceline>(MS: CU-MARK, UCLC 41833)</sourceline>
      </head>
```

The #JHS and #SLC attributes point to @xml:id attributes in a separate personography file:

```
<person xml:id="JHS">
<persName type="display">Rev. J. Hyatt Smith</persName>
<persName type="full"><surname>Smith</surname>, <forename type="first">John</forename> <forename type="middle">Hyatt</forename></persName>
<birth when="1824">1824</birth>
<death when="1886">1886</death>
<sex>male</sex>
<note><p>Born in Saratoga, N.Y., John Hyatt Smith was educated by his schoolmaster father, then sent to Detroit to work as a clerk. There he was a close friend of Anson Burlingame, who later befriended Clemens in Hawaii. Smith studied for the ministry when he wasn't clerking. After ordination in 1848 he served as a Baptist minister in Poughkeepsie, Cleveland, Buffalo, and Philadelphia before he accepted a position at the Lee Avenue Church in Brooklyn. Smith ran as an independent Republican for a seat in the US House of Representatives and served from 1881 to 1883. In December 1883 he was called by a congregational council presided over by Edward Beecher (brother of Henry Ward Beecher) to fill a temporary pastorship at the East Congregational Church in Brooklyn, where he remained until his death.</p></note>
</person>
```
The biographical information is also rendered as a [network graph](http://scholarlyediting.org/2017/editions/aprilfools/graph/index.html).

Clearly these kinds of data could not be printed out, and even if one attempted to print all of the biographical information and the network connections, one would lose the interactivity between texts and individuals and their various connections.

#### TEI and ODD; TEI for Documentary Editing

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

### Seminar 5 (Senate House Library): Using TEI for documentary editions: letters and journals

TEI/ODD Exercise:

* open the ODD Customization file.
* identify which modules you will need for letters and journals.
* create rules for attribute values that can be used.
* invent two new elements.

For more information on writing ODDs, consult Syd Bauman and Julia Flanders's [documentation](http://www.wwp.neu.edu/outreach/seminars/uvic_advanced_2016/presentations/basic_odd/basic_odd_simple_00.xhtml). We will also return to this topic on Day 4.
