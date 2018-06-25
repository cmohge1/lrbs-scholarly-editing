---
layout: page
title: Day 4
permalink: /day4/
---

### Day 4 (Thursday, 5 July)

Time | Topic | Type |
:----|:------|:-----|
9.30 | Seminar 9: Genetic editing, genetic criticism | Presentation, Discussion |
11.30 | Seminar 10: Using TEI to mark-up versions of texts | Digital lab  |
14.00 | Seminar 11: Customising the TEI; problems with TEI; alternative markup with LMNL; Computer-Assisted Collation Overview | Discussion; Digital lab |
16.00 | Library Time |             |

# Afternoon: Computer-Assisted Collation

## Summary

This session will survey two digital approaches for collating texts.

## Collation

The traditional method of collation has been tedious: you literally read versions of texts side-by-side and note the differences in a collation table.

[Something on the Hinman collater.]

In most cases, machine-collation can detect differences that human eyes often miss: punctuation differences, capitalization, even entire lines of text. Two very effective methods of machine-collation can be achieved with Juxta and Collatex. Juxta is easier to use, and quite effective, but it lacks flexibility, and some texts require a lot more nuanced treatment. For more bespoke text projects with a lot of textual variation, Collatex is an ideal program. It is faster and fully customizable, yet it lacks the accessible interface of Juxta. Like any other editorial project, your decision of what to use depends on your documents, and how you would like to present those documents.

### Juxta Commons

Juxta Commons is a web-based interface for comparing versions of texts and creating editions from those versions.

Instructions

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

### CollateX

Download Python 3, preferably the Anaconda distribution

* pip install --pre collatex
* pip install python-levenshtein (but see the note below for Windows)
* pip install graphviz (either through a package manager such as apt-get or MacPorts, or go to http://www.graphviz.org/Download.php and accept the license)
* pip install graphviz

If these instructions do not make sense, consult [David Birnbaum's site](http://collatex.obdurodon.org/installation.xhtml).

A good example of a Collatex collation: the Samuel Beckett manuscript project.
