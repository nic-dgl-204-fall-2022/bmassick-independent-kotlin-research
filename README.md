# Independent Kotlin overview research - part 1

## Kotlin for Data Science
Kotlin has a lot going for it in terms of data science. Since Kotlin is concise, readable, easy to learn and is a JVM language it makes it a great choice. It has access to Java libraries and has maintainable code that is easy to troubleshoot. There are so many ways you can use Kotlin to work with data.

Kotlin also has a multitude of different interactive editors that help with dealing with data such as [Jupyter Kotlin Kernal](https://github.com/Kotlin/kotlin-jupyter), Kotlin Notebooks in Datalore, and Zeppelin Kotlin interpreter. They are each able to offer a great deal of help with organizing and keeping track of any data you need, just in their own ways. Kotlin also has an ever expanding list of libraries for data related objectives. This list is vast and includes Java libraries.

## \[Key resources\]
### 1. [Multik](https://github.com/Kotlin/multik)
Multik is a multidimensional array library. It offers idiomatic, type and dimension-safe API for mathematics to be used with the multidimensional arrays. It has 4 modules: multik-core, multik-default, multik-kotlin, and multik-openblas. Multik also supports JS. 
### 2. [Lets-Plot](https://github.com/JetBrains/lets-plot)
Lets-Plot is a plotting library for statistical data. It is offered for Kotlin and Python. It is influenced by the book "The Grammar of Graphics" by Leland Wilkinson, which by the way, after reading more of what its about I may have to purchase and read.
### 3. [KotlinDL](https://github.com/Kotlin/kotlindl)
KotlinDL is a high-level deep learning API for Kotlin. it uses a few API's such as TensorFlow and ONNX for Java. KotlinDL is aiming to make deep learning easier for JVM developers. 
### 4. [Kravis](https://github.com/holgerbrandl/kravis)
Kravis implements grammar for data visualization. This allows for an easy transition from data to graph. It is used through Jupyter and is still an experimental API. This API seems to have a lot of potential as it keeps developing.
### 5. [Smile](https://github.com/haifengl/smile)
Smile is a comprehensive learning machine developed for Java and Scala, [however it can be used with Kotlin]. Smile is an amazing API for anything to do with machine learning as it covers so many different algorithms and other advanced aspects. 

## [Kravis](https://github.com/holgerbrandl/kravis)
### Kravis
### Holger Brandl, Tokuhiro Matsuno
### [Kravis](https://github.com/holgerbrandl/kravis)

Kravis is an API for visualizing tabular and relational data. Kravis is inspired from [ggplot2](https://ggplot2.tidyverse.org/) and even reuses their cheatsheet. Kravis unlike ggplot2 however does not actually require R to use. Kravis is compatable with various integration backend ranging services. When getting started with Kravis an easy way to do so is by using [Jupyter](https://github.com/Kotlin/kotlin-jupyter) which is an interactive editor for dealing with data in Kotlin.

## Reflection
For the reflection I want to talk about what I learnt and what I am still confused about. So first I leanrnt that Kotlin is actually used a lot more than I thought for data science and the like. I personally have seen people mainly using Java and some Python for this. As for what I am still confused about ... well that is essentially just anything to do with machine learning. I really enjoy the idea of AI and building my own but have nowhere near the know-how to do so. It is something I plan on looking into in the future however.

# Independent Kotlin overview research - part 2

## Overview of [Kravis/Coord.kt](https://github.com/holgerbrandl/kravis/blob/master/src/main/kotlin/kravis/Coord.kt)
The purpose of the [Coord.kt](https://github.com/holgerbrandl/kravis/blob/master/src/main/kotlin/kravis/Coord.kt) section, based off of my perception is to essentially display the data using functions to determine how to zoom/display the data. It is also able to flip coordinates so horizontal becomes vertical.

### Code snippet from [Kravis/Coord.kt](https://github.com/holgerbrandl/kravis/blob/master/src/main/kotlin/kravis/Coord.kt) lines 15-29
''''

fun GGPlot.coordCartesian(
    xlim: Limits? = null,
    ylim: Limits? = null,
    expand: Boolean = true,
    clip: Boolean = true
) = appendSpec {
    val args = arg2string(
        "xlim" to xlim?.toRVector(),
        "ylim" to ylim?.toRVector(),
        "expand" to expand,
        "clip" to if (clip) "on" else "off"
    )

    addSpec("""coord_cartesian($args)""")
}

''''
My understanding of what this snippet of code from [Kravis/Coord.kt](https://github.com/holgerbrandl/kravis/blob/master/src/main/kotlin/kravis/Coord.kt) lines 15-29, is to find where all the data is located on a table or graph and then decide how large of a table or graph is needed to display the data. It is kind of like a zoom. However, it looks like the addSpec() function is what actually handles the actions.

### Code snippet from [Kravis/Coord.kt](https://github.com/holgerbrandl/kravis/blob/master/src/main/kotlin/kravis/Coord.kt) lines 86-100
''''

fun GGPlot.coordFlip(
    xlim: Double? = null,
    ylim: Double? = null,
    expand: Boolean = true,
    clip: Boolean = true
) = appendSpec {
    val args = arg2string(
        "xlim" to xlim,
        "ylim" to ylim,
        "expand" to expand,
        "clip" to if (clip) "on" else "off"
    )

    addSpec("""coord_flip($args)""")
}

''''
My understanding of the above snippen of code from [Kravis/Coord.kt](https://github.com/holgerbrandl/kravis/blob/master/src/main/kotlin/kravis/Coord.kt) lines 86-100, is to be able to flip from horizontal to vertical. However it looks like the addSpec() function is what actually handles the actions.

# Summary of Independent Kotlin overview research - part 1 & 2
For the independent Kotlin overview research assignment, I learned about Kotlin in data science. Although my knowledge of data science is lacking it has always been something that fascinates me. So I decided to dive into it a bit and found out that Kotlin actually has lots to offer in terms of data science. I had always thought of Java, SQL, Scala, and Python for anything to do with data science. Kotlin has a multitude of different interactive editors that help with dealing with data as well and they are quite neat. So although Kotlin is still not a top data science language it has a ton of stuff to offer and will only continue growing.

I also delved into a few APIs regarding Kotlin and data science. There is a ton to choose from and explore that has a huge range of capabilities, especially since Kotlin is a JVM language and has access to the Java libraries. So Kotlin has new APIs being created specifically for it but also has access to trusted APIs that have been used in Java for years.
