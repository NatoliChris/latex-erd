# LaTeX ERD

Simple TikZ set for drawing ERDs.

The preamble will define the necessary tikz shapes to use in the diagram.

## Table of Contents

1. [TODOs](#todos)
2. [Usage](#usage)
    1. [Cardinality on Lines](#cardinality-on-lines)
        1. [Crow Foot](#crow-foot)
3. [Example](#example)


## TODOs

* [x] Crow Foot Notation
* [x] Arrow Notation
* [ ] Cardinality/Participation in the relationship
* [ ] Cardinality on the line


## Usage

**Entity**

```tex
\node[entity] (entityName) {Name Of Entity};
```

```tex
\node[weak entity] (weakEntityName) {Weak Entity};
```

**Relationship**

```tex
\node[relationship] (relationshipName) {Relationship};
```

```tex
\node[weak relationship] (weakRelationShip) {Weak Relationship};
```

**Attributes**

```tex
\node[attribute] (attributeName) {Attribute};
```

```tex
\node[multi attribute] (multiAttribute) {Multi Attribute};
```

```tex
\node[derived attribute] (derivedAttribute) {Derived};
```


### Cardinality on Lines

#### Crow Foot

**Participation(0), Cardinality(1)**

```latex
\draw[cf0one] (entity) to (relationship);
```

**Participation(1), Cardinality(1)**

```latex
\draw[cfoneone] (entity) to (relationship);
```

**Participation(0), Cardinality(many)**

```latex
\draw[cf0many] (entity) to (relationship);
```

**Participation(1), Cardinality(many)**

```latex
\draw[cfonemany] (entity) to (relationship);
```

## Example

```latex
  \begin{tikzpicture}
    % Entity 1
    \node[entity] (enone) {EntitySet};

    % Attributes
    \node[attribute] (attr1en1) [above left = of enone] {\primarykey{attr}} edge (enone);
    \node[attribute] (attr1en2) [below left = of enone] {example} edge (enone);

    % Relationship
    \node[relationship] (rel) [right = 2cm of enone] {Relationship};

    % Entity 2
    \node[entity] (entwo) [right = 2cm of rel] {EntitySet2};
    \node[attribute] (attr2en1) [above right = of entwo] {\primarykey{attrtwo}} edge (entwo);
    \node[attribute] (attr2en2) [below right = of entwo] {example} edge (entwo);



    % Draw the cardinalities
    \draw[cfoneone] (entityname) to (rel);
    \draw[cf0many] (entwo) to (rel);

  \end{tikzpicture}
```
