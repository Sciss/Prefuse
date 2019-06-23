# Prefuse

[![Build Status](https://travis-ci.org/Sciss/Prefuse.svg?branch=master)](https://travis-ci.org/Sciss/Prefuse)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/de.sciss/prefuse-core/badge.svg)](https://maven-badges.herokuapp.com/maven-central/de.sciss/prefuse-core)

## statement

Prefuse is a Java-based toolkit for building interactive information visualization applications. It was developed until 2007 by its original author, [Jeffrey Heer](http://homes.cs.washington.edu/~jheer/). Prefuse is licensed under the terms of a [BSD license](http://github.com/Sciss/Prefuse/blob/master/licenses/Prefuse-License.txt) and can be freely used for both commercial and non-commercial purposes. The original website was at [prefuse.org](https://web.archive.org/web/20181226190156/http://prefuse.org/).

This project at [GitHub](http://github.com/Sciss/Prefuse) is a fork by Hanns Holger Rutz which aims at providing easy maven access for several projects which depend on Prefuse. All changes are released under the same original license.

## building

This fork builds with [sbt](http://www.scala-sbt.org/) 0.13. To launch the demos, run `sbt prefuse-demos/run`.

## linking

To link to this library from Maven:

    <dependency>
      <groupId>de.sciss</groupId>
      <artifactId>prefuse-core</artifactId>
      <version>1.0.0</version>
    </dependency>

Or sbt:

    "de.sciss" % "prefuse-core" % "1.0.1"

## contributing

Please see the file [CONTRIBUTING.md](CONTRIBUTING.md)

## changes

The following changes and refactorings have been applied on the original code as published through the [beta-20071021 snapshot](http://sourceforge.net/projects/prefuse/files/prefuse/beta-20071021/):

* the project builds now with sbt 0.13 instead of ant.
* the parent project contains two sub projects `core` and `demos`, where the original plain library corresponds to `core`.
* the original `readme.txt` has been renamed to `readme_original.txt`
* all the license files have been moved into the `licenses` folder
* the ant files have been removed: `ant.jar`, `build.xml` and the shell scripts for running ant
* the eclipse files `.classpath` and `.project` have been removed
* the directory structure has been changed to reflect the default layout of sbt
* an arbitrary version number has been chosen as offset for the artifact
* the sources have been converted from latin1 to utf8 encoding
* the api docs have been removed from the source folder. the can be rebuild as scaladoc files with sbt target `doc`.
* several occurrences of `AbstractTreeMap.Entry` have been corrected in `prefuse.util.collections` so javadoc doesn't choke on them
* the `data` folder was split into `demos/src/main/resources` and `sample_data`
* a demo selector class `prefuse.demos.Demos` has been added. To run it: `sbt prefuse-demos/run`
* `TreeTest` has been modified so that it won't depend on the `TreeMap` demo anymore (it has a copy of the data set now).
* The bug fixes from the other fork at https://github.com/prefuse/Prefuse have been incorporated as far as they were relevant.

The following fixes have been incorporated

* #3048039 Iterator bug in Dynamic Aggregate removal 
