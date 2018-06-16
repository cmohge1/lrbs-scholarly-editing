---
layout: page
title: 'Digital Scholarly Editing, Day 1'
permalink: /day1/
---

# [London Rare Books School 2018](https://cmohge1.github.io/lrbs-scholarly-editing/)

## Synopsis

Today will feature an introduction to the history of scholarly editing, an overview of digital workflow strategies, and an introduction to XML.

## Aims

- General grasp of the history of scholarly editing.

- Facility with transcribing documents in Markdown, HTML, and XML.

## Schedule

### Day 1 (Monday, 2 July)

Time  | Topic                                                          | Type
:---- | :------------------------------------------------------------- | :-----------------------
12.30 | Registration                                                   |                          |
13.00 | Senate House Library Talk                                      | Presentation             |
14.00 | Seminar 1: Brief history of Scholarly Editing                  | Presentation, Discussion |
16.00 | Seminar 2: Digital Editing Workflow; Brief Introduction to XML | Digital lab              |  |

## Seminar 1: Brief History of Scholarly editing

### Readings and discussions

A. E. Housman, "The Application of Thought to Textual Criticism"; W. W. Greg, "The Rationale of Copy Text"; Fredson Bowers, "Some Principles..."; D. Greetham, "A History of Textual Scholarship" (from _Cambridge Companion to Textual Scholarship_); Philip Gaskell, Introduction to _From Writer to Reader_.

### Lecture notes

<details>
  <summary>A brief outline</summary>
  <ul>
  <li><p>Peisistratus (560–527 BCE) orders the 'official' text of Homer. The primary challenge was to build a coherent text from myriad versions spoken by the rhapsodes. This could be a viable beginning of textual criticism, i.e., being aware of variance and attending to authenticity and authority (whatever those terms mean). (Discuss!)</p></li>
  <li><p>Lycurgus (c. 390–324 BCE) arranges for single texts of Aeschylus, Sophocles, and Euripedes to be deposited into Athenian archives.</p></li>
  <li><p>The history of textual editing is a history of arguments about the meaning of terms such as authenticity and authority.</p></li>
  <li><p>What is the <em>textus receptus</em>? E.g., Falstaff "babbl'd o' green fields" (Shakespeare, <em>Henry V</em>); "soiled fish of the sea" (Melville, <em>White-Jacket</em>).</p></li>
  <li><p>Alexandrian library: manuscript copying; the birth of collation as a practice; dealing with anomalies.</p></li>
  <li><p>Descriptive Bibliography.</p></li>
  <li><p>Biblical scholarship and philology.
</p></li>
</ul>
</details>

 

<details>
  <summary>Housman's thought</summary>
  <p>
</p>
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
  <summary>Problem of the Copy-Text: Greg-Bowers method</summary>
  <p>
- ...
</p>
</details>

## Seminar 2: Digital Editing Workflow; Brief Introduction to XML

### Reading

David Birnbaum, ["An even gentler introduction to XML"](http://dh.obdurodon.org/what-is-xml.xhtml).

### Lecture notes

Digital Editing Workflow

If I am interested in creating a digital edition, there are two questions that you must ponder at length before proceeding:

1. What is my text model, and why am I making it?

2. What is my workflow?

The answer to (1) will vary quite a bit, depending on your documents, and what kind of edition you would like to produce. We will continue to investigate options to (1) as we move through the course this week.

The answer to (2) is a little more straightforward. Since we are concerned with "digital" editing, we need to think in terms of an appropriate computational pipeline.

Transcription Options

The beginning of the pipeline is the flexible text editor. By flexible I mean an editor that is amenable to Web publishing, and uses non-proprietary open source formatting. Many editors have used proprietary word processors to transcribe their editorial material. While that has many virtues (control of type-setting feature, to name one), it presents a lot of problems if you are trying to optimize your workflow. E.g., if you transcribe an edition in Microsoft Word, you would have to transform that document (and all of its attendant features) into XML or HTML in order to make it work as a digital edition on the Web.

For us, the common understanding is that XML files should be our edition files of record. Ideally, all documents would be transcribed in XML from the beginning, but for a variety of reasons that is not always practicable.

First we will look at the most basic of transcription: Markdown. This is lightweight web authoring at its best.

[Access the slides here.](insert-link)

### Brief Introduction to XML

Why encode documents in XML? [Access the slides here.](fill-in-link)
