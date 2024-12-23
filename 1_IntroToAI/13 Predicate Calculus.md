Propositional logic is limited in a very significant way: for every individual object or idea we want to describe, we have to create a new variable. We have no way of saying all objects of some type share certain properties.

We'll introduce a few new logical constructs, and arrive at what is called first-order or predicate logic.

### <mark style="background: #69E7E4;">Constant symbols</mark>

A constant symbol is a single object, like •my cat Tony" or "President Obama.' Note that propositional logic does not have constant symbols that represent objects; instead, propositional logic only has statements like "President Obama is a Democrat."

We use upper-case for constant symbols: my cat Tony is Tony, President Obama is Obama , etc.

### <mark style="background: #69E7E4;">Predicates:</mark>

We'll also add new relations among objects that are called predicates. A predicate is true or false. So, the predicate ``IsACat()`` is true when apply to Tony: ``IsACat(Tony) = T`` . On the other hand, ``IsACat(Obama) = F``

Predicates may have more than one argument: 

``Eats(Tony, T , TastesLike(YellowCandy,Banana) = T``

``ParentsOf(Isabelle, Penelope, Rene) = F``

### <mark style="background: #69E7E4;">Variables:</mark>

Sometimes we want to find out for what values of, say, the second argument of a predicate, makes the predicate true. For example, for what values of x make this true: ``Eats(Tony,x)``

It turns out that when ``x`` equals any of ``CatFood, Bugs,CatNip, MashedPotatoes (etc.)`` then the predicate is true.

### <mark style="background: #69E7E4;">Operators:</mark>

We have the same operators as before: ^, v, ¬, ->, <-> . Thus, we can write ``Fish(Jenny) -> HasGills(Jenny)``. If this is true then Jenny is a fish, then she has gills.

### <mark style="background: #69E7E4;">Quantifiers:</mark>

We can combine variables, predicates, and relations to make statements like "all fish have gills" and "at least one cat eats mashed potatoes." Two new symbols are introduced to build these statements: ∀ (reads "for all") and ∃ (reads "there exists').

For example, ``(x∀)(Fish(x) -> HasGiIIs(x))`` is read "for all x, if x is a fish then x has gills." That statement may be true or false; it depends on whether it is true that all fish have gills (we'll see how to answer that question in the next section).

Another example: ``(∃x)(Cat(x)AEats(x,MashedPotatoes))`` , which is read "there exists an x such that x is a cat and x eats mashed potatoes." Again, we need to ask, how do we know if this is true?

### <mark style="background: #69E7E4;">Possible worlds (semantics):</mark>

How do we know if ``(x∀)(Fish(x) -> HasGiIIs(x))`` is true? It depends from what "world" we pull our x values. A 'World," or "possible world," is simply a set of objects and truth-values for predicates. 

In one possible world, the set of objects may be ``Tony, Jenny , Obama , Isabelle , Penelope , Rene, YellowCandy , Banana , etc.`` 

The truth values for the predicates are ``Cat(Tony) = T, Fish(Tony) = F, Cat(Jenny) = F, Fish(Jenny) = = Tony) = F etc.`` Every predicate must be true or false for every object or combination of objects (in other words, no predicate's truth for any inputs is "unknown").

Now if we want to know if some statement is true, we just use the following rules: 
- If the statement has a ∀ in front, we just check if every object makes the statement true.
- If the statement has a ∃ in front, we just check if there is at least one object that makes the statement true.

Notice that the negation of a ∀ statement is an ∃ statement and vice versa:
![](https://i.imgur.com/7j6zysf.png)

# <mark style="background: #FF5582A6;">Giving up:</mark>