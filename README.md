doc2json
========

`doc2json` is a utility Python script that allows us you
to convert API documentation pages (as those generated by automated tools,
such as `javadoc`) into JSON document files.
`doc2json` currently handles API docs generated by the following tools:

* [javadoc](https://www.oracle.com/java/technologies/javase/javadoc-tool.html) format (Java)
* [dokka](https://kotlin.github.io/dokka/1.7.20/) (Kotlin)
* [scaladoc](https://docs.scala-lang.org/overviews/scaladoc/for-library-authors.html) (Scala)

# Installation

```bash
pip install .
```

# Usage

```
doc2json --help
usage: doc2json [-h] [--language {java,kotlin,scala}] -o OUTPUT -i INPUT [--jdk-docs]

optional arguments:
  -h, --help            show this help message and exit
  --language {java,kotlin,scala}
                        Language associated with the given API docs
  -o OUTPUT, --output OUTPUT
                        Directory to output JSON files
  -i INPUT, --input INPUT
                        Input directory of API docs
  --jdk-docs            Indicate whether the documentation is related to JDK
```

# Example

Parse documentation pages of the
[java.util](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/package-summary.html) Java package:

```bash
doc2json --language java -i examples/java/html-docs/java/util \
  -o json-docs --jdk-docs
```

The script above creates a directory named `java-docs`
that contains all generated JSON documentents.
