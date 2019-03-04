---
title: "Wykki"
date: 2014-09-09
aliases:
  - /wykki

tags:
- language-python
- tool-google-app-engine
categories:
- web

description: "Wykki uses data from Freebase to answer natural language questions, and learns how to answer new question types over time."
---

_I took Wykki offline in 2017; the rest of this page is as I originally published it in 2014._

Wykki uses data from Freebase to answer natural language questions, and learns how to answer new question types over time. In other words, Wykki answers and learns; I’ll talk about each of those separately below.

## Answering Your Questions

In short, Wykki is designed to answer questions that ask about a specific Property of a certain Subject. That means it can answer questions like these:

- What is the Structural Height of the Empire State Building?
- What is the Atomic Mass of Fe?
- What is the Number of Employees of Google?

When Wykki is asked a question, it separates the subject (“Empire State Building”) from the actual question (“What is the Structural Height of …”). Wykki knows what Freebase properties that question refers to (“Structural Height”), and then searches Freebase to return the right answer to the user.

Of course, the above questions all sound very robotic. Wykki is also robustly able to answer the same questions phrased in much more natural ways:

- How tall is the Empire State?
- How much does iron weigh?
- How many people work at Google?

Note that those questions had neither proper names for the subjects nor for the properties, but that Wykki was still able to answer them. How does this work? That’s where Wykki’s learning comes in.

## Learning to Understand Questions

What makes Wykki tick is learning from user input. If Wykki comes across a question it’s never seen before, it asks the user to guide it towards the right answer, and it’ll always keep confirming the accuracy of the questions it already knows.

### Learning New Questions

First, Wykki asks the user to specify the subject of the new question, so it can separate what part of the input is what.

{{< figure src="/images/projects/wykki/learning-1.png" >}}

Second, Wykki lists all of Freebase’s properties for that subject. The user is asked to select the property that relates to the question he or she asked.

{{< figure src="/images/projects/wykki/learning-2.png" >}}

Third and finally, Wykki answers the question–and that’s the last thing the user sees.

{{< figure src="/images/projects/wykki/learning-3.png" >}}

In the background, however, Wykki has now learned to associate the question the user asked with the property the user specified. From the screenshots above, that means that, if another user asks “How many episodes of [TV Show] are there?” Wykki will be able to answer:

{{< figure src="/images/projects/wykki/learning-4.png" >}}

This separation of questions and subjects is therefore very powerful, because it allows Wykki to learn how to answer a new type of question about every single subject that question is relevant to all at once.

### Reinforcing Old Questions

Because the relationships between questions and the properties they relate to are user-generated, there are bound to be some errors. That’s why Wykki also has a scoring system that determines the “relatedness” between a question and a property.

When a user asks a question, sometimes the scoring system jumps in and asks if the answer Wykki provided was relevant to the question the user asked. The user can then simply click “yes” or “no,” and the scoring system will either increase or decrease that question/ property combo’s relatedness score.

The more confident Wykki is in the relevance of an answer, the less the scoring system shows up; the less confident Wykki is, the more it shows up.

If the relatedness score drops below a certain threshold, the question and property are unlinked.

## Other Notes

Here are some other things that Wykki does:

- Wykki answers in full sentences, which are constructed using the names Freebase has for the subject and property that the user asked about.
- Wykki has units! If a property has a unit associated with it (like meters for the height of a person, or degrees Celsius for a boiling point), that unit will show up in the answer. Big numbers (e.g. a million) also show up nicely (1,000,000 vs. 1000000).
- With the new Freebase data, Wykki should be able to answer questions about over **46 million topics**, and reply with over **2.6 billion facts**!
- On the back end, Wykki runs on NDB and Jinja2 on top of Google App Engine, and is written completely in Python.
- The whole site is also still completely responsive, so it should look good on any device!
