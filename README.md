# xml-internet-draft-sample
A template for a repo for an internet draft in xml source format.  The included example includes a YANG module.

# IETF Note Well
This repository relates to activities in the Internet Engineering Task
Force(IETF). All material in this repository is considered Contributions
to the IETF Standards Process, as defined in the intellectual property
policies of IETF currently designated as BCP 78
(https://www.rfc-editor.org/info/bcp78), BCP 79
(https://www.rfc-editor.org/info/bcp79) and the IETF Trust Legal
Provisions (TLP) Relating to IETF Documents
(http://trustee.ietf.org/trust-legal-provisions.html).

Any edit, commit, pull request, issue, comment or other change made to this
repository constitutes Contributions to the IETF Standards Process
(https://www.ietf.org/).

You agree to comply with all applicable IETF policies and procedures,
including, BCP 78, 79, the TLP, and the TLP rules regarding code
components (e.g. being subject to a Simplified BSD License) in
Contributions.

# Internet-Draft-Sample Repo

The template does the following things:

1. provides a makefile that supports make targets:
   - all	- Update trees mentioned in draft, <DRAFT>.{xml,txt,html,raw}
     Note that as part of generating the formatted versions from xml, it
     automatically updates the local xml file based on included YANG
     models (see below.)
   - idnits - Update <DRAFT>.txt, check it with idnits
   - id	- create the -<rev> version of I-D in "IDs" subdirectory,
     also add to git. The version in the docName within
     the xml file is used for the version number; it should be updated
     after the ID version is uploaded to the IETF.
   - rmid	- undo 'make id' (including git add)
   - trees	- update .tree versions of modules mentioned in draft
   - "DRAFT".{xml,txt,html,raw} - update version of draft indicated by extension
   - checkyang	- check draft YANG models using pyang
   - yangbase	- put or update standard yang models in ~/.yang
   - vars 	- for testing, shows some internal variables

2. adds support for travis validation of pushes/PRs -- it does a make
   idnits and reports xml or idnits errors -- see
   https://travis-ci.org/louberger/xml-internet-draft-sample for an
   example run

3. Adds a project README.md (this file) with IETF note well and links to
   - online generation of text and html versions of
     draft xml available in repo master branch using xml2rfc
   - online generation of idnits from master
   - travis results

This is an example repo for internet-drafts.  It assumes a single file named "draft<whatever>.xml".  If you want to use this for your draft, fork/copy the repo, remove *.xml and *.yang and drop in your own draft<XXX>.xml, and .yang files if you have them.

Caution: if you are using YANG, the makefile will automatically update the xml based on yang module file changes, but you MUST use the following format for noting the yang in your xml file:
```
    <CODE BEGIN> file MODULE_NAME@DATE,yang
```
and
```
    <CODE ENDS>
```
where MODULE_NAME matches a file named MODULE_NAME.yang

If you configure travis, it will automatically run 'make targets' and provie reslts as shown below.  

## Current xml2rfc and idnits results: ![alt text](https://api.travis-ci.org/louberger/xml-internet-draft-sample.svg?branch=master)
* For details see: https://travis-ci.org/louberger/xml-internet-draft-sample
* For results on past commits see: https://travis-ci.org/louberger/xml-internet-draft-sample/builds

## Fomatted versions: [text](https://xml2rfc.tools.ietf.org/cgi-bin/xml2rfc.cgi?url=https://raw.githubusercontent.com/louberger/xml-internet-draft-sample/master/draft-berger-xml-sample-repo.xml) or  [html](https://xml2rfc.tools.ietf.org/cgi-bin/xml2rfc.cgi?url=https://raw.githubusercontent.com/louberger/xml-internet-draft-sample/master/draft-berger-xml-sample-repo.xml&modeAsFormat=html%2Fascii)

## idnits: [results](https://tools.ietf.org/idnits?url=https://xml2rfc.tools.ietf.org/cgi-bin/xml2rfc.cgi?url=https://raw.githubusercontent.com/louberger/xml-internet-draft-sample/master/draft-berger-xml-sample-repo.xml&modeAsFormat=html%2Fascii)
