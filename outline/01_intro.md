---
layout: default
title: Introduction
permalink: /outline/intro.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge-berlin.github.io/curriculum/outline/intro.html

{% endcomment %}

<section>
Welcome to Programming! 🙌
----------------------------------------
{: .slide-title .chapter}

* What we'll learn
* How we'll learn it
* How we'll help each other
</section>

<section ng-controller="NarrativeController">
## What we'll learn
{: .slide_title .slide}

#### How to program
#### ...in Clojure

> Today we're learning to code in a language called Clojure. Clojure is good for all sorts of programming projects, and we like it quite a bit.
{: ng-show="block13" .description}
</section>


<section ng-controller="NarrativeController">
## What is programming?
{: .slide_title .slide}

* asking the computer questions
* exploring
* building stuff
</section>


<section ng-controller="NarrativeController">
## What does Clojure look like?
{: .slide_title .slide}

```clojure
(print-str "Good morning, ClojureBridgers!")
(max 8 17 2)
(-> get-data clean-data analyze display-results)
```
</section>


<section>
## How will we learn?
{: .slide_title .slide}

#### <button class="link" ng-model="block51" ng-click="block51=!block51">Intro</button>

> We want to ask the computer questions, so we need a way to talk to it.
> Programmers use code to talk to the computer--tell it to do things, ask it questions.
> To start, we'll have that conversation with the computer in something called a "REPL".
{: ng-show="block51" .description}

![Nightcode's repl](img/repl.png)

</section>


<section ng-controller="NarrativeController">
## Using a REPL
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> To interact with Clojure, we're going to be using the REPL tab in
> Nightcode. It's a nice way to play with Clojure interactively.
{: ng-show="block61" .description}


#### Using the REPL <button class="link" ng-bind-html="details" ng-model="block62" ng-click="block62=!block62"></button>

> There's a couple of ways to get to a REPL in Nightcode. One general one
> that is always running in the corner of the window, and another that is
> launched with the "Run with REPL".
{: ng-show="block62" .description}

> The easiest REPL to access and use is loaded from the beginning of
> opening Nightcode. You can find it in the bottom left hand window
> pane.
{: ng-show="block62" .description}


#### Evaluate program and line <button class="link" ng-bind-html="details" ng-model="block63" ng-click="block63=!block63"></button>

<!-- TODO project_name should probably be defined somewhere, right? -->
> Nightcode also lets us evaluate a line or an entire program at a time.
> In the big panel, navigate to the `src/`(project_name)`/main.clj` file.
> After pressing "Run with REPL", you should see some output in the bottom
> pane. The first time you run this, it'll take a little while.
{: ng-show="block63" .description}

> After this, you'll find a new REPL launch in that bottom pane. Here you
> can type commands just like the other REPL -- but now you can also type
> code in the main file, and run it with the `Eval` button
> (<kbd>ctrl</kbd>/<kbd>cmd</kbd> + <kbd>shift</kbd> + <kbd>x</kbd>, making sure the cursor is next to the code).
{: ng-show="block63" .description}
</section>


<section ng-controller="NarrativeController">
## Helping and being helped
{: .slide_title .slide}

* Programming is hard
* Programming is easy
* How your coach can help
  * We don't know all the answers
  * Focus on *how* to approach the problem

</section>


<section>
#### EXERCISE: Try the Clojure REPL

* Start Nightcode
* Focus on the REPL in the bottom right
* Type the Clojure functions below and see what happens

```clojure
(print-str "Good morning, ClojureBridgers!")
(max 8 17 2)
```
> Be careful with typos! :) Take special care with those parentheses.
</section>


<section>
#### EXERCISE 2: Evaluate file and line

* In NightCode, at the top left, click on "New Project"
* Choose a location and a name (don't call it `quil`--maybe use your name?)
* Click on "Graphics" (the button with a big "Q" on it)
* Click on "Run with REPL", a window will pop up with a grey circle
* Find the line `(fill 192)` and change it to `(fill 250 20 20)`
* Select the code from lines 7 to 10 with your cursor (make sure all of it is selected) and click on `Eval Selection` (<kbd>ctrl</kbd> + <kbd>E</kbd> or <kbd>cmd</kbd> + <kbd>E</kbd>)
* See what happens
</section>


<section>
#### EXERCISE 3: Look at Clojure docs

* In the REPL, try to look up the documentation for a function you have used
* You can use the `(clojure.repl/doc function-name)` command to do this. For instance, try typing `(clojure.repl/doc fill)` into the REPL
* You can also go to [ClojureDocs](http://clojuredocs.org) and look up docs online
</section>

{% comment %}

:star2: A link below is for a slide only. Go to [README.md](../README.md)
instead. :star2:

{% endcomment %}

<section>
Return to the <a href="javascript:;" onClick="Reveal.slide(1);">first slide</a>,
or go to the [curriculum outline](/curriculum/#/1).
</section>
