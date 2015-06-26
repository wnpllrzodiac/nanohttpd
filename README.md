## What is "nanohttpd"?

*NanoHttpd* is a light-weight HTTP server designed for embedding in other applications.

*NanoHttpd* has been released under a Modified BSD licence.

Build status: [![Build Status](https://api.travis-ci.org/NanoHttpd/nanohttpd.png)](https://travis-ci.org/NanoHttpd/nanohttpd)

Coverage Status: [![Coverage Status](https://coveralls.io/repos/NanoHttpd/nanohttpd/badge.svg)](https://coveralls.io/r/NanoHttpd/nanohttpd)

Current central released version: [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.nanohttpd/nanohttpd/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.nanohttpd/nanohttpd)

We are currently in the process of stabalising nanohttpd from the many pull requests and feature requests that were integrated over the last few months. The next release will come soon, and there will not be any more "intended" major changes before the next release. If you want to use the bleeding edge version of nanohttpd, you can get it from sonatype:

	<dependencies>
		<dependency>
			<artifactId>nanohttpd</artifactId>
			<groupId>org.nanohttpd</groupId>
			<version>2.2.0-SNAPSHOT</version>
		</dependency>
	</dependencies>
	...
	<repositories>
		<repository>
			<id>sonatype-snapshots</id>
			<url>https://oss.sonatype.org/content/repositories/snapshots</url>
			<snapshots>
				<enabled>true</enabled>
			</snapshots>
		</repository>
	</repositories>    

The other artifacts are also available there.

## Core Features
* Only one Java file, providing HTTP 1.1 support.
* Two "flavours" - one at "current" standards and one strictly Java 1.1 compatible.
* Released as open source, free software, under a Modified BSD licence.
* No fixed config files, logging, authorization etc. (Implement by yourself if you need them.)
* Experimental support for SSL (see the 'ssl-support' branch in git)
* Basic support for cookies
* Supports parameter parsing of GET and POST methods.
* Rudimentary PUT support (added in 1.25).
* Support for HEAD and DELETE requests.
* Supports single and multi-value parameters (w/ a helper method) if needed.
* Supports file upload (since version 1.2, 2010) with minimal memory overhead.
* Never caches anything.
* Doesn't limit bandwidth, request time or simultaneous connections.
* All header names are converted to lower case so they don't vary between browsers/clients.
* Very low memory overhead when processing even the largest of requests.
* Temp file usage and threading model are easily customized.
* Persistent connections (Connection "keep-alive") support allowing multiple requests to be served over a single socket connection.

## Websocket Support
* Tested on Firefox, Chrome and IE.

## Webserver Features
* Supports both dynamic content and file serving.
* Default code serves files and shows all HTTP parameters and headers.
* File server supports directory listing, ```index.html``` and ```index.htm```.
* File server supports partial content (streaming).
* File server supports ETags.
* File server does the 301 redirection trick for directories without ```/```.
* File server supports simple skipping for files (continue download).
* File server serves also very long files without memory overhead.
* Contains a built-in list of most common MIME types.
* Runtime extension support (extensions that serve particular MIME types) - example extension that serves Markdown formatted files. Simply including an extension JAR in the webserver classpath is enough for the extension to be loaded.

*Thank you to everyone who has reported bugs and suggested fixes.*
