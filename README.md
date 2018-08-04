JarClassLoader
==============

What is it?
-----------

This is just a copy of [JDotSoft JarClassLoader](http://www.jdotsoft.com/JarClassLoader.php), currently there are no
functional modifications, the copyright is theirs. For more information visit their web site.

I found the tool because my usual favourite tool [One-JAR](http://one-jar.sourceforge.net/) for creating JARs with
included nested dependencies (I do not like shaded JARs) failed in a situation where I wanted to use signed third-party
JARs in connection with my unsigned own one. Specifically, this was about the BouncyCastle crypto libraries. I tried
JarClassLoader, integrated it into my Maven build and - it worked! Thank you, JDotSoft. `:-)`

Why am I re-publishing it?
--------------------------

I spoke to the creators and asked them to publish it as a little JAR on Maven Central, but they refused to do so due to
maintenance effort. They said, as it only consists of one class every user can just copy the source code into her
project instead of adding a dependency. I do disagree on that approach and think that duplication is the enemy of
maintainability. Because I saw that the licence is GPL2, I decided to take the initiative and publish it myself.

This is what OSS is all about, right? Take the source code, modify it (or not) and re-publish it under the conditions of
the original licence. This is what I did here. 

In order to do that I need to create signed JARs. I also wanted a separate Javadoc JAR, so I had to modify the Javadoc a
little bit in order to make the checker pass because it threw errors (build with JDK 8). Content-wise, there are no
changes.

Why group ID `de.scrum-master` instead of `com.jdotsoft`? Because I do not want to claim another company's domain name
and rather publish under a domain name which is really mine. I did keep their package name `com.jdotsoft.jarloader`,
though, because other users who until now have used the identical class and want to migrate to using the Maven
dependency do not need to change anything in their source code, the import stays the same.
