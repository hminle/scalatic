#Scalatic

[![Join the chat at https://gitter.im/padurean/scalatic](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/padurean/scalatic?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![Travis CI - Build Status](https://travis-ci.org/padurean/scalatic.svg?branch=master)](https://travis-ci.org/padurean/scalatic)

Dead simple static blog generator written in Scala with minimum dependencies.

Uses GitHub API to render as HTML posts written in GitHub-flavored Markdown
syntax.

Should be used together with the
[Github Markdown CSS](https://github.com/sindresorhus/github-markdown-css)
(a copy is included in the _**src/test/scala/scalatictest/source**_ folder)


##Usage

1. Create your blog folder structure

  **NOTE**: one can use the _**src/main/test/scala/scalatictest**_ folder
  as a starting point.

  The blog folder structure can reside anywhere on your machine
  and needs to look like this:

  ```
  blog            -> root folder of your blog; can have any name you want
    |_ new        -> any markdown source files that should be (re)rendered to HTML
    |_ source     -> contains any files that are not blog posts (e.g. html, css, js)
      |_ posts    -> all markdown source files that have already been rendered to HTML
    |_ target     -> this is where your generated blog will be saved

  ```

  Only the _**new**_ and _**source**_ folders need to be manually created -
  the _source/posts_ and _target_ folders are created automatically if they
  don't exist.

  Also, it is required that _**header.html**_ and _**footer.html**_ files exist
  in the _source_ folder.

  Any other files (folders are ignored) present in the _source_ folder are
  considered "static" files and will be copied without any transformation to
  the _target_ folder.

2. Clone the [Scalatic](https://github.com/padurean/scalatic) repo and run with

  `sbt "run /path/to/your/blog"`

  OR

  Download the latest Scalatic release as a
  [single jar](https://github.com/padurean/scalatic/releases/download/0.1.0/scalatic-0.1.0.jar)
  and run with

  `java -jar scalatic-0.1.0 /path/to/your/blog`


**NOTE**s:

  - To build Scalatic as one JAR, run `sbt one-jar`
