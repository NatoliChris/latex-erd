# LaTeX ERD

Simple TikZ set for drawing ERDs.

The preamble will define the necessary tikz shapes to use in the diagram.

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