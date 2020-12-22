
December 2020

Notes on the latest modification to Apixio's fork of ghost4j repo/code.

There were no semantic/behavioral changes made--only the version of the com.lowagie
artifact was modified (from 2.1.7, which is from 2009, to 4.2.2, which is the latest
in the lowagie line), and the java version used to build was changed to 8 (from 7).

Building the artifact fails when building javadocs and when performing GPG signing
of it.  It's easy to skip javadoc build but the maven plugin for signing was commented
out.

To build:

  $ mvn -DskipTests -Dmaven.javadoc.skip=true clean install

As there's no jenkins job to do an official build, the process this time was to
build locally, and then manually install the resulting target/*.jar file into
artifactory.
