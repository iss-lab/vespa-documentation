<!-- Copyright 2017 Yahoo Holdings. Licensed under the terms of the Apache 2.0 license. See LICENSE in the project root. -->

# Creating Vespa documentation

All Vespa features must have user documentation - this document explains how to write documentation.

## Practical information

Vespa documentation is served using
[GitHub Project pages](https://help.github.com/categories/github-pages-basics/)
with
[Jekyll](https://help.github.com/categories/customizing-github-pages/).
To edit documentation, check out and work off the master branch in this repository.

Documentation is written in HTML or Markdown.
We use a single Jekyll template (_layouts/default.html) to add header, footer and layout.
With Jekyll installed (follow the link above), use

    bundle exec jekyll serve

to set up a local server at localhost:4000 to see the pages as they will look when served.

The layout is written in Bootstrap, documents refers directly to the Bootstrap CSS.
Refer to [Bootstrap documentation](http://getbootstrap.com/css/) to
add style effects to articles. Note that the entire documentation page content
is contained in a Bootstrap layout column with column width 12.
Please do not add custom style sheets, as it is harder to maintain.

## Writing good documentation

Learn how to [contribute](https://github.com/vespa-engine/vespa/blob/master/CONTRIBUTING.md) to documentation, 
then read the following guide before writing some.

### Guides and references

A document cannot be both comprehensive and comprehensible.
Because of this, documentation is split into *guides* and *reference* documents.

Guides should be easy to understand by only explaining the most important concepts under discussion.
Reference documents on the other hand must be complete but should skip verbiage meant to aid understanding.

Reference documents are those that are placed in reference/ subdirectories.

### Maintainability

Prioritize maintainability higher than usability:

* Don't include unnecessary details, especially ephemeral ones such as that a feature is "recently added" or how things was before, etc. The guide/reference distinction helps here: Guides are harder to maintain as they contain more verbiage, and they should not unnecessarily repeat information found in a reference doc. **Write such that the document will still be correct in a half decade.**

* Don't repeat information found in other documents. It is tempting to make life easier for users by writing use-case oriented documentation on how to accomplish specific tasks, but this backfires as it leads to a lot of repetition which we fail to maintain. In the long run it is better to explain the concepts clearly and succinctly and leave it to the users to piece together the information. **Use the same principles for documentation as for code: DRY, refactor for coherency etc.**

* Be wary of adding code in the documentation. The code will becomes incorrect over time and should in most cases be placed in git as continuously built code and referenced from the doc.

### Text quality

Documentation is not high prose, and not a podcast.
Users want to consume the information as soon as possible with as little effort as possible and get on with their lives.

Make the text as short, clear, and easy to read as possible:
* Describe things plainly "as they are". You usually shouldn't worry about explaining why, what you can do with it etc.
* Use short sentences with simple structure.
* Avoid superfluous words such as "very".
* Avoid filler sentences intended to improve the flow of the text - documents are usually browsed, not read anyway.
* Use consistent terminology even when it leads to repetition which would be bad in other kinds of writing.
* Use active form "index the documents", not passive "indexing the documents".
* Avoid making it personal - do not use "we", "you", "our".
* Do not use &amp;quot; , &amp;mdash; and the likes - makes the document harder to edit, and no need to use it.
* Less is more - &lt;em&gt; and &lt;strong&gt; is sufficient formatting in most cases.

### Links

Add an *id* attribute to each heading such that link can refer to it: Use the exact same text as the heading as id, lowercased and with spaces replaced by dashes such that references can be made without checking the source.
Don't change headings/ids unless completely necessary as that breaks links.

Example:
&lt;h2 id=&quot;my-nice-heading&quot;&gt;My nice Heading&lt;/h2&gt;
If this algorithmic transformation is followed it is possible to link to this section using &lt;a href=&quot;doc.html#my-nice-heading&quot;&gt; without having to consult the html source of the page to find the right id.

### Link to Javadoc

* Link to javadoc for an artifact: http://javadoc.io/doc/com.yahoo.vespa/container-search
* Link to javadoc for a package: http://javadoc.io/page/com.yahoo.vespa/container-search/latest/com/yahoo/search/federation/vespa/package-summary.html
* Link to javadoc for a class: http://javadoc.io/page/com.yahoo.vespa/vespa-http-client/latest/com/yahoo/vespa/http/client/config/ConnectionParams.Builder.html

*By Jon Bratseth in June 2016*
