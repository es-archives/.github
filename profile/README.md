
The Empty Spaces Archive Project
================================

👁 watch this space 👁

flow
----

- a willing author downloads their twitter archive zip
- they also download the thread-extraction tool (tentatively called `unstitch`)
- loading the zip into `unstitch`, they search through their threads and pick ones to extract
- they provide metadata (CWs, tags maybe?) to go with each thread
- `unstitch` packs up this data and submits it to the archive repository on github
    - format and procedure TBD
- moderation and discussion about the submitted content happens on github
- with any adjustments made, and assuming the submission is accepted, a volunteer adds it to the
  repository
    - maybe extra tooling would be good here? `git` integration in `unstitch` could streamline this,
      making integration a case of hitting "accept PR"
- another tool/infra consumes the `git` repo and produces a queryable database from it
- this database is used by a shiny web service for readers to enjoy

rationale
---------

- why use twitter archive zips? why not just get stuff from twitter directly?
    - this is possible, but twitter's api design (apparently deliberately) frustrates this. this is
      possible as an extra tool, but that's an effort in itself
    - the api can be avoiding using scraping techniques, but those _suck_ by definition

- why build a whole thread extraction tool?
    - because i'd like this to be not just accesible but *comfortable* for authors, and all the
      existing tools are very plywood-and-duct-tape, with ergonomics to match. they'd also force the
      submission part of the process to be very manual, and "you need to know how to use `git`" is a
      non-starter

- why this whole mess with `git`? why not a nice ao3/booru-style site?
    - github gives us moderation and roles *for free* - we don't need to build lots of
      security-sensitive and auth stuff
    - who's gonna pay for and maintain a service like that? and if they drift away or uh... turn
      bad, what happens to the archive? do _they_ even know?

- why a `git` repo full of text? why not a database?
    - a `git` repository is trivial to clone, or just grab a copy of as a zip/tarball
    - if the worst comes to the worst, a tree of text files is much easier to dig through that a
      database with some mysterious schema
    - fits the `git`+github collaboration model

- why build an intermediate database to drive the reader? why not use the `git` repo directly?
    - that's not convenient for full-text search or filtering, but it may be possible if necessary.
      needs further discussion

