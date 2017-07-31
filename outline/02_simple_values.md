---
layout: default
title: Simple Values
permalink: /outline/simple_values.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge-berlin.github.io/curriculum/outline/simple_values.html

{% endcomment %}

<section>
Simple Values
----------------------------------------
{: .slide-title .chapter}

* "I am a String"
* `true`, `false`
* `:first-name`, `:last-name`
</section>


<section ng-controller="NarrativeController">
## Giving names to values

#### <button class="link" ng-model="block161" ng-click="block161=!block161">Intro</button>

> If we had to type the same values over and over, it would be very
> hard to write large programs. We need to define names for values we
> re-use, so we can refer to them in a way we can remember.
{: ng-show="block161" .description}
</section>


<section ng-controller="NarrativeController">
#### Defining names for values with `def`

#### <button class="link" ng-bind-html="details" ng-model="block171" ng-click="block171=!block171"></button>

> We can give a name to a value with `def`.
> When a value is given a name, that name is called a *symbol*.
{: ng-show="block171" .description}

> Reference: [def](http://clojurebridge-berlin.github.io/community-docs/docs/clojure/def/)
{: ng-show="block171" .description}

```clojure
(def mangoes 3)
(def oranges 5)
(+ mangoes oranges)
;=> 8
```
</section>


<section ng-controller="NarrativeController">
#### Defining names for complex values <button class="link" ng-bind-html="details" ng-model="block181" ng-click="block181=!block181"></button>

> We can define names for simple values and for more complex values too. Try the following.
> Look at the last line, and see how we can use symbols by themselves to refer to a value.
{: ng-show="block181" .description}

```clojure
(def fruit (+ mangoes oranges))
(def average-fruit-amount (/ fruit 2))
average-fruit-amount
;=> 4
```
</section>

<section>
#### EXERCISE 1: Basic arithmetic

* How many minutes have elapsed since you arrived at the workshop today?
* Convert this value from minutes to seconds.
</section>


<section>
#### EXERCISE 2 [BONUS]: Minutes and seconds

* Convert 1000 seconds to minutes and seconds.
* The minutes and the seconds will be separate numbers.
* `(quot x y)` will give you the whole number part of x divided by y.
* `(rem x y)` will give you the remainder of x divided by y.
</section>

{% comment %}

:star2: A link below is for a slide only. Go to [README.md](../README.md)
instead. :star2:

{% endcomment %}

<section>
Return to the <a href="javascript:;" onClick="Reveal.slide(1);">first slide</a>,
or go to the [curriculum outline](/curriculum/#/1).
</section>
