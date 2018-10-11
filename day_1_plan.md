---
layout: page
title: Day 1
permalink: /day1.html
---

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=3 orderedList=false} -->
<!-- code_chunk_output -->

* [Aims](#aims)
* [Schedule: Day 1 (Monday, 2 July)](#schedule-day-1-monday-2-july)
	* [Seminar 1: Brief History of Scholarly Editing](#seminar-1-brief-history-of-scholarly-editing)
	* [Seminar 2: Digital Editing Workflow](#seminar-2-digital-editing-workflow)
	* [Markdown exercise](#markdown-exercise)
	* [Brief Introduction to XML](#brief-introduction-to-xml)

<!-- /code_chunk_output -->

Today will feature an introduction to the history of scholarly editing, an overview of digital workflow strategies, and an introduction to Markdown and XML.

## Aims

- General grasp of the history of scholarly editing.

- Facility with transcribing documents in Markdown, HTML, and XML.

## Schedule: Day 1 (Monday, 2 July)

Time  | Topic                                                                         | Type
:---- | :---------------------------------------------------------------------------- | :-----------------------
12.30 | Registration                                                                  |
13.00 | Senate House Library Talk                                                     | Presentation             |
14.00 | Seminar 1: Brief history of Scholarly Editing                                 | Presentation, Discussion |
16.00 | Seminar 2: Digital Editing Workflow, Transcription with Markdown, Brief Introduction to XML | Digital lab              |

### Seminar 1: Brief History of Scholarly Editing

#### Readings

1. [Greetham, "A History of Textual Scholarship"](/readings/greetham-history-textual-scholarship.pdf) (from the *Cambridge Companion to Textual Scholarship*).

2. [A. E. Housman, "The Application of Thought to Textual Criticism"](/readings/housman_application_of_thought.html) (*Art and Error*).

3. [G. Thomas Tanselle, "The Varieties of Scholarly Editing" (Greetham, 1995)](/readings/tanselle_varieties_of_editing.pdf).

#### Lecture notes

<details>
  <summary>A brief outline of textual scholarship </summary>
  <br />
  <ul>
  <li><p>Peisistratus (560–527 BCE) orders the 'official' text of Homer. The primary challenge was to build a coherent text from myriad versions spoken by the rhapsodes. This could be a viable beginning of textual criticism, i.e., being aware of variance and attending to authenticity and authority (whatever those terms mean). (Discuss!)</p></li>
  <li><p>Lycurgus (c. 390–324 BCE) arranges for single texts of Aeschylus, Sophocles, and Euripedes to be deposited into Athenian archives.</p></li>
  <li><p>The history of textual editing is a history of arguments about the meaning of terms such as authenticity and authority. It is also a record of humans grappling with the contingencies of cultural imagination, tradition, and artifacts.</p></li>
  <li><p>What is the <em>textus receptus</em>? When mistakes in a received (published) edition prevail: E.g., Falstaff "babbl'd o' green fields" (Shakespeare, <em>Henry V</em>); "soiled fish of the sea" (Melville, <em>White-Jacket</em>).</p></li>
  <li><p>Library of Alexandria: manuscript copying was a common practice, since all incoming ships had to declare any manuscripts in their possession. Any manuscripts declared would then be copied and deposited in libraries. Their copies were only labeled differently if they had differences. Sometimes the copies were returned and the originals kept in Alexandria. What's wrong with this story?</p></li>
  <li><p>The birth of collation as an editorial practice; and dealing with analogy versus anomaly: the Alexandrians sought to emend texts that had, in their judgment, corruptions. Their practice is idealistic: the best text is not based on any actual document but rather a new document that seeks to bring out the best readings from all the extant texts.</p></li>
  <li><p>Pergamum, the other civic rival to Alexandria, switched to using parchment (animal skin) after Alexandria banished papyrus exports during a trade conflict. Generally, the Pergamanian scholars accepted the necessity of corruption and sought to identify the "best text" based on a careful examination of all surviving witnesses. The "best text" would be based on an actual historical document, rather than the Alexandrian text, which was a reconstructed text. Texts from neither of these epochs survive, but citations of them exist in medieval scholias.</p></li>
  <li><p>Descriptive Bibliography. Callimachus (c. 305–240 BCE) created the first record of Greek manuscripts, <em>Pinakes</em> (Tablets).</p></li>
  <li><p>Late classical era: the birth of textual commentaries (Servius Honoratus on Virgil, for example). Why is this important? The textual commentaries include quotes of important works and other cultural and historical information that have been otherwise lost. Hugh Cayless offers a good primer on Servius, as well as some thoughts on digital editing, <a href="https://blogs.library.duke.edu/dcthree/2018/01/10/digital-servius/">on his blog</a>.</p></li>
  <li><p>Biblical scholarship: problems of vocalisation, accentuation, and word-division in consonantal Hebrew. Masoretic text (Hebrew and Aramaic copies, c. 7th–9th centuries CE) versus Greek Septuagint translation versus the Dead Sea Scrolls. The Old Testament is far less complicated (textually speaking) than the transmission of the Greek New Testament. Jerome's <em>Vulgate</em>, commissioned by Pope Damascus I in the late 4th century CE, was the first Latin Bible that was based on surviving witnesses (~8000 manuscripts!).
</p></li>
<li><p>Medieval period saw a period of conservation, copying mostly religious works and trying to reconcile them, as much as possible, with classical (pagan) works. The Caroline Reformation led to a standardised script that made various European national scripts consistent––a significant portion of surviving manuscripts of classical literature is the result of copies made in monasteries with Carolingian script. Meanwhile, Constantinople's holdings of Greek manuscripts were crucial to Italian humanists' serious return to Greek study in the late fourteenth–early fifteenth century.</p></li>
<li><p>Copying work transferred from the hands of monks to those of professional scribes, often in universities. The great poet Petrarch's partial reconstruction of Livy's histories was a rigorous editorial project based on manuscript fragments in many medieval repositories. Poggio Bracciolini (1380–1459), acting as papal secretary, found manuscripts all over Europe of prominent classical thinkers. Bracciolini even invented a new humanist script that was far more clear and readable than the prevailing <em>textura</em> (i.e., gothic) script of the day. This is a good moment to reflect on the desire for humanists over time to invent inscription technologies that are consistent, readable, and shareable––a set of values very important to so-called "digital humanities" today.</p></li>
<li><p>Another figure worth noting: Lorenzo Valla (1407–57), the great debunker of forgeries: the <em>Donation of Constantine</em> and the letters of Seneca and St. Paul, e.g. He also sought to emend Jerome's <em>Vulgate</em>. His edition, based on Greek and patristic texts, was published by Erasmus in 1505. Similarly, Politian (1454–94) searched for earliest recoverable version of a manuscript––this foreshadowed the genealogical method of plotting a linear path of textual transmission. Politian derived the method of <em>eliminatio codicum descriptorum</em>, the removal of "descriptive" or derived copies as witnesses to an authentic version. This led to the method (very much in use to this day) of <em>stemma codicum</em>, the "family tree" of textual versions.</p></li>
</ul>


<ul><li>Stemmatics: building a family tree by examining scribal errors in multiple manuscript copies. Aldine editions. Example of the Erasmus New Testament. As an example: <img src="https://christopherohge.com/stemmatics.jpg"/>(<em>Source</em>: https://chs.harvard.edu/CHS/article/display/4742.1-textual-criticism-as-applied-to-biblical-and-classical-texts)</li></ul>

<ul><li><p>Philology (<em>OED</em>):</p>

<p>1. Love of learning and literature; the branch of knowledge that deals with the historical, linguistic, interpretative, and critical aspects of literature; literary or classical scholarship. Now chiefly U.S.</p>

<p>3. The branch of knowledge that deals with the structure, historical development, and relationships of languages or language families; the historical study of the phonology and morphology of languages; historical linguistics. See also comparative philology at comparative adj. 1b.</p></li></ul>

<ul><li><p>Lachmannian method: identification and evaluation of bibliographic sources with a critical awareness. This comes out of the work of Karl Lachmann (1793–1851), whose 1850 edition of Lucretius claimed that the three extant manuscripts descended from a single archetype. Later witnesses have more errors. Interestingly, Lachmann's <em>Nibelungenlied</em> edition involved more speculation.</p></li></ul>

<ul><li><p>Johann Gottfried Eichhorn (1753–1824) and his monumental claim that there was no possibility to find or reconstruct the original or best text in biblical texts, because of all of the layers of copying and linguistic shifts (<em>Einleitung in das Alte Testament</em>, 1780–83).</p></li></ul>

<ul><li><p>Friedrich August Wolf (1759–1824) similarly argued in his <em>Prolegomena ad Homerum</em> (1795) that it would be impossible to recover Homeric texts.</p></li></ul>
</details>

<details>
  <summary>Housman's thought</summary>
  <ul>
  <li><p>Where do science and art meet? "Textual criticism is a science, and, since it comprises recension and emendation, it is also an art."</p></li>
  <li><p>A matter of reason and common sense, but also not "an exact science at all ... fluid and variable ... neither mystery nor mathematics"... It deals with human frailties---errors.</p></li>
  <li><p>Editorial problems should be treated as individuals: "must be regarded as possibly unique."</p></li>
  <li><p>Learning principles from instances:
  "P]ublic opinion is now aware that textual criticism, however repulsive, is nevertheless indispensable, and editors find that some presence of dealing with the subject is obligatory; and in these circumstances they apply, not thought, but words, to textual criticism. They get rules by rote without grasping the realities of which those rules are merely emblems, and recite them on inappropriate occasions instead of seriously thinking out each problem it arises."</p></li>
  <li><p>This is to suggest that editors should "look all facts in the face" and avoid sectarianism of thought: "This I cite as a specimen of the things which people may say if they do not think about the meaning of what they are saying, and especially as an example of the danger of dealing in generalisations. The best way to treat such pretentious inanities is to transfer them from the sphere of textual criticism, where the difference between truth and falsehood or between sense and nonsense is little regarded and seldom even perceived, into some sphere where men are obliged to use concrete and sensuous terms, which force them, however reluctantly, to think."</p></li>
  <li><p>What does he mean by sincerity of a manuscript? "When you call a MS. sincere you instantly engage on its behalf the moral sympathy of the thoughtless ... Our concern is not with the eternal destiny of the scribe, but with the temporal utility of the MS.; and a MS. is useful or the reverse in proportion to the amount of truth which it discloses or conceals, no matter what may be the causes of the disclosure or concealment."</p></li>
  <li><p>Sincerity and recension; the importance of <em>building</em>. "[E]ven the traditional rules must of course be tested by comparison with the witness of the MSS... if we build structures on our trust we are no critics."</p></li>
  <li><p>A paradox: "The MSS. are the material upon which we base our rule, and then, when we have got our rule, we turn round upon the MSS. and say that the rule, based upon them, convicts them of error. We are thus working in a circle, that is a fact which there is no denying; but, as Lachmann says, the task of the critic is just this, to tread that circle deftly and warily"</p></li>
  <li><p>"To be a textual critic requires aptitude for thinking and willingness to think; and though it also requires other things, those things are supplements and cannot be substitutes. Knowledge is good, method is good, but one thing beyond all others is necessary; and that is to have a head, not a pumpkin, on your shoulders and brains, not pudding, in your head."</p></li>
</ul>
</details>



<details>
  <summary>Editing and history</summary> <!-- fill in more here -->
  <ul>
  <li><p>An act of historical scholarship which requires an answer to this question: "What role do judgment and evaluation play in reconstructing the past?" (Tanselle, 10).</p></li>
  <li><p>Texts of <strong>documents</strong> v. text of <strong>works</strong>.</p></li>
</ul>
</details>
<br/>
### Seminar 2: Digital Editing Workflow

#### Reading

1. David Birnbaum, ["An even gentler introduction to XML"](http://dh.obdurodon.org/what-is-xml.xhtml).

#### Lecture notes
<details>
<summary>Basic components of a digital edition</summary>
<ul>
<li>
<p>Source file(s) of transcribed text and metadata encoded in XML. The best encoding practice is to use the Text Encoding Initiative (TEI) standards, but it's not necessary.</p>
</li>
<li>
<p>Files that parse (i.e., read) and transform the encoded documents for viewing. Typically these will be XSLT or XQuery or (less common) Python files.</p></li>
<li><p>The edition, as transformed by the former, in html.</p>
<p>Files for styling the edition's html interface (CSS, JavaScript)</p></li>
</ul>
</details>
<details>
  <summary>Digital Editing Workflow</summary>
<p>If I am interested in creating a digital edition, there are two questions that you must ponder at length before proceeding:</p>

<p>1. What is my text model, why am I making it, and what will it be used for?</p>

<p>2. What is my workflow?</p>

<p>The answer to (1) will vary quite a bit, depending on your documents, and what kind of edition you would like to produce. We will continue to investigate options to (1) as we move through the course this week.</p>

<p>The answer to (2) is a little more straightforward. Since we are concerned with "digital" editing, we need to think in terms of an appropriate computational pipeline.</p>
</details>



<details>
  <summary>Transcription Options</summary>
  <p>

The beginning of the pipeline is the flexible text editor. By flexible I mean an editor that is amenable to Web publishing, and uses non-proprietary open source formatting. Many editors have used proprietary word processors to transcribe their editorial material. While that has many virtues (control of type-setting features, to name one), it presents a lot of problems if you are trying to optimize your workflow. E.g., if you transcribe an edition in Microsoft Word, you would have to transform that document (and all of its attendant proprietary code) into XML or HTML in order to make it work as a digital edition on the Web. Also data scientists or digital text analysts warn against using Microsoft Excel files for analysis because that program introduces unnecessary code that can hinder output.</p>

<p><strong>Which text editor?</strong> We will be using the <a href="https://atom.io/">Atom</a> text editor. It features a very attractive Markdown previewer (with additional feature packages), and it is well-integrated with GitHub (upon which this course web site is built). Other good options are the <a href="https://www.sublimetext.com/">Sublime</a> text editor, <a href="https://www.barebones.com/products/bbedit/">BB Edit</a>, and <a href="https://notepad-plus-plus.org/">Notepad ++</a> (for Microsoft).</p>

<p>For us, the common understanding is that XML files should be our edition files of record. Ideally, all documents would be transcribed in XML from the beginning, but for a variety of reasons that is not always practicable.</p>

<p>First we will look at the most basic of transcription: Markdown. This is lightweight web authoring at its best.
</p>
</details>
<br />

### Markdown exercise

First we will go through a slideshow:
[Access the Markdown slides here.](https://christopherohge.com/MarkdownLRBS.pdf)

- Download ["The Child on the Cliffs," by Edward Thomas](../thomas_edward_child_on_the_cliffs.txt).

- Open the file in Atom text editor. Save it as thomas_markdown_exercise.md.

- Make sure your Atom text editor is updated. Click on Help and check to see you if need to update.

- Go to File > Settings > Install and type in the search box "markdown-preview-enhanced". This enhanced preview package gives you additional features such as footnotes and table of contents.

- Press `control + shift + m` to show an html preview in Atom.

- Using Markdown syntax, mark up the following ([click here for the Markdown cheatsheet](https://www.markdownguide.org/cheat-sheet/)):

  - a main header (for the title), and italicise it;
  - a secondary header (for the author);
  - a hyperlink from Edward Thomas's name to a web page (say, Poetry Foundation) with his biography;
  - create a contextual footnote for one of the lines (possibly the "Source"?).

- Once your markdown document is complete, right-click on the preview window, select HTML > HTML (offline). In a green box you will see the html url for your file. You can also right click on the markdown preview and select "Open in Broswer". Your document is now available as a web-ready html file. You can navigate to the file yourself and open it in your browser.

How do you get from markdown to xml? Two good options are [Pandoc](https://pandoc.org/) and [OxGarage](http://www.tei-c.org/oxgarage/). I prefer using Pandoc for my transformations (my favourite probably being the markdown > PDF transformation). OxGarage is also good, and a little bit simpler to use: it can convert several types of documents into TEI-XML.

The other option is to open a new TEI-XML document in oXygen or your preferred text editor and simply copy-and-paste the body of the html file into the <body> element of the xml file.

### Brief Introduction to XML

For the introduction: [Access the XML slides here.](https://christopherohge.com/XML-intro_LRBS.pdf)

#### Proceed to [Day 2](day_2_plan.md)
