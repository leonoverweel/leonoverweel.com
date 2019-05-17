---
title: "Modeling Train Commuter Stress for Dutch Cities"
date: 2018-11-15

tags:
- language-Python
- ml-NumPy
- ml-Matplotlib
- tool-Git
- tool-GitHub
categories:
- web

description: "Scraped data about the Dutch rail network to visualize which cities provide the least stressful commute to Amsterdam central station."
---

This is the project I did for the [Social and Technological Networks](http://www.inf.ed.ac.uk/teaching/courses/stn/) course I took as part of my MSc Artificial Intelligence at the University of Edinbrugh. Using data from the Nederlandse Spoorwegen, I modeled which cities are best to commute from if you work near Amsterdam Central Station (ASD) but don't want to pay Amsterdam rent, based on the following factors:

* **Crowdedness** \\( c \\): How busy the train is
* **Duration** \\( d \\): How much time it takes to get to ASD
* **Flexibility** \\( f \\): How many ways there are to get to ASD
* **Punctuality** \\( p \\): Whether the train(s) will arrive on time
* **Switches** \\( l \\): How many times the commuter has to switch trains

I combined these factors into a single stress measure \\( S \\) as follows, where \\( \alpha \\)s are weights for each factor and \\( O \\) is the set of possible options:

$$ S = \min\_{\forall o \in O} \left( \alpha\_c c\_o + \alpha\_d d\_o + \alpha\_p (1 - p\_o) + \alpha\_s s\_o \right) + \alpha\_f (1 - f) $$

By scraping data from the Dutch national railway operator Nationale Spoorwegen (NS), I could then make the following plots of how "stressful" a commute to Amsterdam would be for each train station in the Netherlands, for different \\( \alpha \\) settings.

{{< figure src="/images/projects/2018/stn-train-commuter-stress/maps.png" caption="Stress maps with different settings for \\( \alpha \\)s; green indicates low stress and red indicates high stress. Amsterdam Central Station (ASD) is marked in black. The mixed model uses my preferences as \\( \alpha \\) settings." >}}

Using settings from the bottom-right mixed model, the best cities to commute from are mostly in the Randstad and the area north-west of Amsterdam. See Appendix A of the report for a list of the top-thirty stations according to this metric.

<embed class="pdf" src="/pdfs/uoe-stn.pdf" alt="pdf" pluginspage="http://www.adobe.com/products/acrobat/readstep2.html">

More info:

* [Download the full report (PDF)](/pdfs/uoe-stn.pdf)
* [Get the code on GitHub](https://github.com/leonoverweel/infr-11124-stn/tree/master/project)
