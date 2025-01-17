Naming conventions in R are famously anarchic, with no clear winner and
multiple conventions in use *simultaneously* in the same package. This
has been written about before, in a lucid article in the [R
Journal](http://journal.r-project.org/archive/2012-2/RJournal_2012-2_Baaaath.pdf),
a detailed exploration of names in R source code [hosted on
CRAN](http://cran.r-project.org/web/packages/rockchalk/vignettes/Rstyle.pdf)
and general discussion on
[stackoverflow](http://stackoverflow.com/questions/1944910/what-is-your-preferred-style-for-naming-variables-in-r).

Basically, there are 5 naming conventions to choose from:

-   alllowercase: e.g. `adjustcolor`
-   period.separated: e.g. `plot.new`
-   underscore\_separated: e.g. `numeric_version`
-   lowerCamelCase: e.g. `addTaskCallback`
-   UpperCamelCase: e.g. `SignatureMethod`

There are clear advantages to choosing one naming convention and
sticking to it, regardless which one it is:

> “Use common sense and BE CONSISTENT”

The [Google Style
Guide](https://google-styleguide.googlecode.com/svn/trunk/Rguide.xml) is
ironically written in a rather inconsistent way (mixing capitals with
lowercase in a single sentence surely breaks their own rule!)

But which one to choose?

Naming convention chaos
-----------------------

I recently encountered this question when I looked at the CRAN hosted
version of the tutorial I co-authored ‘Introduction to visualising
spatial data in R’. To my dismay, this document was littered with
inconsistencies: here are just a few of the object names used, breaking
almost every naming convention:

-   `Partic_Per`: This variable is trying to be simultaneously
    UpperCamelBack and underscore\_separated: a new naming convention
    I’d like to coin Upper\_Underscore\_Separated (joke). Here’s another
    example: `Spatial_DistrictName` These styles should not be mixed
    according to [Hadley Wickham](http://adv-r.had.co.nz/Style.html) and
    [Colin
    Gillespie](http://csgillespie.wordpress.com/2010/11/23/r-style-guide/).
-   `sport.wgs84`: An example of period.separation
-   `crimeDat$MajorText`: lowerCamelBack and UpperCamelBack *in the same
    object*!
-   `ons_label`: a rare example of a consistent use of a naming
    convention, although this was in a variable name, not an object.

Does any of your code look like this? If so I suggest sorting it out.
Ironically, we had a section on typographic conventions *in the error
strewn document*. This states that:

> “it is a good idea to get into the habit of consistent and clear
> writing in any language, and R is no exception”.

It was time to follow our own advice!

A trigger to remedy chaotic code
--------------------------------

The tutorial was used as the basis for a
[workshop](http://foss4g-e.org/content/using-r-command-line-gis)
delivered at the Free and Open Source Software for Geo-spatial
([FOSS4G](http://foss4g.org/)) conference in
[Bremen](http://foss4g-e.org/). The event is affiliated with the The
Open Source Geospatial Foundation ([OSGeo](http://www.osgeo.org/)), who
are big advocates of consistency and
[standards](http://live.osgeo.org/en/standards/standards.html). With
many experienced programmers at the event, it was the perfect
opportunity to update the tutorial on the project’s [github
repository](https://github.com/Robinlovelace/Creating-maps-in-R).

Which naming convention?
------------------------

We decided to use the **underscore\_separated** naming convention. Why?
It wasn’t because we love typing underscores (which can cause problems
in some contexts), but because of more fundamental issues with the other
options:

-   alllowercase names are difficult to read, especially for non-native
    readers.
-   period.separated names are confusing for users of
    [Python](http://python4astronomers.github.io/python/objects.html)
    and other languages in which dots are meaningful.
-   UpperCamelBack is *ugly* and requires excessive use of the shift
    button.

There are also a couple of reasons why we positively like underscores:

-   Underscores are **fast** to read: 10% to 20% faster than camelBack,
    which is especially confusing to non-native English readers,
    according to [one
    article](http://whathecode.wordpress.com/2011/02/10/camelcase-vs-underscores-scientific-showdown/).
-   Underscores are recommended by some prominent R users, including
    [Hadley Wickham](http://adv-r.had.co.nz/Style.html), [Colin
    Gillespie](http://csgillespie.wordpress.com/2010/11/23/r-style-guide/)
    and [Andrew
    Gellman](http://andrewgelman.com/2012/08/28/migrating-from-dot-to-underscore/).

Implementing a consistent coding convention
-------------------------------------------

After overcoming the mental inertia to decide on a new naming
convention, actually implementing it should be the easy part. A series
of
[regex](http://robinlovelace.net/r/2014/04/14/regex-in-R-RStudio.html)
commands could help, including the following (the ‘Regex’ tickbox must
be enabled if you’re searching in RStudio):

    [a-z]\.[a-z] # will search for dots between lowercase chars (period.separation)
    [a-z][A-Z] # find camelBack code

Unfortunately, these commands will also find many R commands that use
these naming convention, so just re-reading the code may be just as
fast.

The below image shows the github diff of a typical change as part of a
renaming strategy. Note in this example that not only are we
implementing a consistent naming convention, we also added a new comment
in this commit, improving the code’s ‘understandability’. Implementing a
naming convention can be part of a wider campaign to improve your R
projects. This could include adding comments, [removing redundant
information](http://robinlovelace.net/r/2014/06/25/pruning-a-giant-gh-repo.html)
from large projects and reformatting code, perhaps using the [formatR
package](http://cran.r-project.org/web/packages/formatR/index.html).

[![commit](https://dl.dropboxusercontent.com/u/15008199/img/r_style.png)](https://github.com/Robinlovelace/Creating-maps-in-R/commit/b6729590a5c9bbf3f4e5332c46e57c732412345c)

Conclusion
----------

It *is* important to think about style in writing any languages,
especially if your code will be [read by
others](http://journal.r-project.org/archive/2012-2/RJournal_2012-2_Baaaath.pdf):

> “What could help might be to raise awareness in the R community about
> naming conventions; writers of books and tutorials on R could make a
> difference here by treating naming conventions when introducing the R
> language.”

In conclusion, it is lazy and irresponsible to write and maintain messy
code that is difficult to read. By contrast, consistent, clear and
well-commented code will help you and others use your code and ensure
its longevity. Adoption of a clearly defined [naming
convention](http://en.wikipedia.org/wiki/Naming_convention_%28programming%29)
such as the **underscore\_separation** adopted in our
[tutorial](https://github.com/Robinlovelace/Creating-maps-in-R/raw/master/intro-spatial-rl.pdf)
can be an easy step one can take *now* towards this aim.

The only question that remains is which naming convention `WiLL.U_uSe`!
