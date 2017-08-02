---
layout: default
title: Vectors and Maps
permalink: /outline/data_structures.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge-berlin.github.io/curriculum/outline/data_structures.html

{% endcomment %}

<section>
Bunches of values
----------------------------------------
{: .slide-title .chapter}

* Values in order
* Values you look up
</section>


<section ng-controller="NarrativeController">
### Vectors
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> So far, we've dealt with single pieces of data: one value at a time,
> whether it's a number or a string of letters. Now we'll look at
> groups of values. First, sequences
{: ng-show="block11" .description}

#### Sequential collection <button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> A vector is a sequential collection of values. Each value in a
> vector is numbered starting at 0. That number is called its
> index. The index is used to refer to each value when looking them
> up.
{: ng-show="block21" .description}

> Imagine a box split into equally-sized compartments. Each of those
> compartments has a number.  You can put a piece of data inside each
> compartment and always know where to find it, as it has a
> number. That's what vectors are like.
{: ng-show="block22" .description}

> Note that the numbers start with 0. That's strange to us, but it's
> how computers do things.
{: ng-show="block22" .description}


![Vector](img/vector.png)

</section>


<section ng-controller="NarrativeController">
#### What do vectors look like? <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

>Vectors are written using square brackets with any number of pieces
>of data inside them, separated by spaces. You can use commas if you
>want--the computer ignores them. Here are some examples of vectors.
{: ng-show="block31" .description}

```clojure
[1 2 3 4 5]
["Grace Hopper" 1906 1992]
```
</section>


<section>
#### EXERCISE: Make a vector
{: .slide_title .slide}

* Go to your REPL
* Make a vector of the high temperatures for the next 7 days in the
  town where you live.
* Then use the `nth` function to get the high temperature for next
  Tuesday.
</section>


<section ng-controller="NarrativeController">
### Maps

#### key value pairs <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

>Maps hold a set of keys and values associated with them. You can
>think of it like a dictionary: you look up things using a word (a
>keyword) and see the definition (its value). If you've programmed in
>another language, you might have seen something like maps--maybe
>called dictionaries, hashes, or associative arrays.
{: ng-show="block101" .description}

![Map](img/map.png) <!-- FIXME this image uses `:first` which is doggone unacceptable; remake it -->
</section>


<section ng-controller="NarrativeController">
#### What do Clojure maps look like? <button class="link" ng-bind-html="details" ng-model="block102" ng-click="block102=!block102"></button>

> We write maps by with curly braces, using key/value pairs. It goes
> key, value, key, value, over and over inside the curly braces.
{:ng-show="block102" .description}

> Maps are useful because they can hold data in a way we normally
> think about it. Take our made up example, Sally Brown. A map can
> hold her first name and last name, her address, her favorite food,
> or anything else. It's a simple way to collect that data and make it
> easy to look up. The last example is an empty map. It is a map that
> is ready to hold some things, but doesn't have anything in it yet.
{: ng-show="block102" .description}

```clojure
{:first "Sally" :last "Brown"}
{:germany "Berlin" :france "Paris" :usa "Washington, D.C."}
{}
```
</section>


<section ng-controller="NarrativeController">
#### Creation <button class="link" ng-bind-html="details" ng-model="block104" ng-click="block104=!block104"></button>

> `assoc` and `dissoc` are paired functions: they associate and disassociate items from a map. See how we add the last name "Brown" to the map with `assoc`, and then we remove it with `dissoc`. `merge` merges two maps together to make a new map.
{: ng-show="block104" .description}

```clojure
(assoc {:first "Sally"} :last "Brown")
;=> {:first "Sally", :last "Brown"}

(dissoc {:first "Sally" :last "Brown"} :last)
;=> {:first "Sally"}

(merge {:first "Sally"} {:last "Brown"})
;=> {:first "Sally", :last "Brown"}
```
</section>


<section ng-controller="NarrativeController">
#### Extraction 1 <button class="link" ng-bind-html="details" ng-model="block105" ng-click="block105=!block105"></button>

> `count`, every collection has this function. Why do you think the
> answer is two? `count` is returning the number of associations.
{: ng-show="block105" .description}

> Since map is a key-value pair, the key is used to get a value from a
> map. One of the ways often used in Clojure is the examples below.
> We can use a keyword like using a function in order to look
> up values in a map. In the last example, we supplied the key `:MISS`.
> This works when the key we asked for is not in the map.
{: ng-show="block105" .description}

```clojure
(count {:first "Sally" :last "Brown"})
;=> 2

(get {:first "Sally" :last "Brown"} :first)
;=> "Sally"
(get {:first "Sally"} :last)
;=> nil


(get {:first "Sally"} :last :MISS)
;=> :MISS
```
</section>

<section ng-controller="NarrativeController">
#### Extraction 2 <button class="link" ng-bind-html="details" ng-model="block106" ng-click="block106=!block106"></button>

> Then we have `keys` and `vals`, which are pretty simple: they return
> the keys and values in the map. The order is not guaranteed, so we
> could have gotten `(:first :last)` or `(:last :first)`.
{: ng-show="block106" .description}

```clojure
(keys {:first "Sally" :last "Brown"})
;=> (:first :last)

(vals {:first "Sally" :last "Brown"})
;=> ("Sally" "Brown")
```
</section>

<section ng-controller="NarrativeController">
#### Update <button class="link" ng-bind-html="details" ng-model="block110" ng-click="block110=!block110"></button>

> After the creation, we want to save a new value associated to the
> key. The `assoc` function can be used by assigning a new value to
> the existing key.
> Also, there's handy function `update`. The function takes map and
> a key with a function. The value of specified key will be the first
> argument of the given function.
> The `update-in` function works like `update`, but takes a vector of keys
> to update at a path to a nested map.
{: ng-show="block110" .description}

```clojure
(def hello {:count 1 :words "hello"})

(update hello :count inc)
;=> {:count 2, :words "hello"}
(update hello :words str ", world")
;=> {:count 1, :words "hello, world"}


(def mine {:pet {:age 5 :name "able"}})

(update-in mine [:pet :age] - 3)
;=> {:pet {:age 2, :name "able"}}
```
</section>


<section>
### Collections of Collections

#### <button class="link" ng-model="block101" ng-click="block101=!block101">Intro</button>

> Simple values such as numbers, keywords, and strings are not the
> only types of things you can put into collections. You can also put
> other collections into collections, so you can have a vector of
> maps, or a list of vectors, or whatever combination fits your data.
{: ng-show="block101" .description}
</section>

<section>
#### Vector of Maps

```clojure
(def characters
  [{:name "Snoopy"
    :species "dog"}
   {:name "Woodstock"
    :species "bird"}
   {:name "Charlie Brown"
    :species "human"}])

(:name (first characters))
;;=> "Snoopy"

(map :name characters)
;;=> ("Snoopy" "Woodstock" "Charlie Brown")
```
</section>


<section>
#### EXERCISE: Modeling Yourself
{: .slide_title .slide}

* Using the Clojure REPL
    - (Option) You may create a new file and write code in the file. To
    evaluate, select the code you want and hit <kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd>x</kbd> or <kbd>cmd</kbd> <kbd>shift</kbd> + <kbd>x</kbd>, or press the "Eval" button
* Make a map representing yourself
* Make sure it contains your first name and last name
* Then, add your hometown to the map using [assoc](http://grimoire.arrdem.com/1.6.0/clojure.core/assoc/) or [merge](http://grimoire.arrdem.com/1.6.0/clojure.core/merge/).
</section>

<section>
#### EXERCISE [BONUS]: Modeling your classmates
{: .slide_title .slide}

* First, take the map you made about yourself in previous exercise.
* Then, create a vector of maps containing the first name, last name and hometown of two or three other classmates around you.
* Lastly, add your map to their information using [conj](http://clojuredocs.org/clojure.core/conj).
</section>

{% comment %}

:star2: A link below is for a slide only. Go to [README.md](../README.md)
instead. :star2:

{% endcomment %}

<section>
Return to the <a href="javascript:;" onClick="Reveal.slide(1);">first slide</a>,
or go to the [curriculum outline](/curriculum/#/1).
</section>
