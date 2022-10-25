
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
- another tool/infra consumes the git repo and produces a queryable database from it
- this database is used by a shiny web service for readers to enjoy

