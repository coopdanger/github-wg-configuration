---
docname: draft-cooper-wugh-github-wg-configuration
title: Github Configuration for IETF Working Groups
abbrev: Github Configuration
category: info

ipr: trust200902
area: General
workgroup: wugh
keyword: Internet-Draft

stand_alone: yes
pi: [toc, sortrefs, symrefs]

author:
 -
    ins: A. Cooper
    name: Alissa Cooper
    organization: Cisco
    email: alcoop@cisco.com

author:
 -
    ins: P. Hoffman
    name: Paul Hoffman
    organization: ICANN
    email: paul.hoffman@vpnc.org

normative:

informative:


--- abstract

TODO Abstract

--- middle

# Introduction

Many IETF working groups and participants are making use of Github in different ways as part of their work on IETF documents. Some others are interested in having their working groups use Github to facilitate the development of working group documents, but they are unfamiliar with how to get started or they are unclear about which conventions to follow. 

This document proposes a set of administrative processes and conventions for IETF working groups to use if they chose as a working group to use Github to facilitate their work. The proposals in this document are not directed at working groups or individuals that are already using Github to do IETF work. Practices vary among existing working groups and some of them are not consistent with the conventions proposed here. That is fine. The goal of the proposals in this document is not to require uniformity in current practice, but to help working groups to get started using Github in a uniform way if they want to.

The document is meant to spur discussion in the IETF community. If there proves to be rough consensus in the community in support of the proposals in this document, the functional requirements would need to be discussed with the IETF tools team and the secretariat who would need to support various pieces of what is proposed here.

Discussion of this document takes place on the GitHub@ietf mailing list (ietf-and-github@ietf.org), which is archived at https://mailarchive.ietf.org/arch/search?email_list=ietf-and-github.


# Administrative Process and Conventions

This section specifies a proposal for an administrative process and conventions to support the creation and management of Github organizations for working groups in a uniform way. The steps could be done manually by the secretariat or they could be automated. See, e.g., https://github.com/richsalz/ietf-gh-scripts and https://github.com/martinthomson/i-d-template for work on automation. In this document the question of whether these processes would be manual or automated is deliberately left ambiguous since the first question is whether this is functionality the community would want to have supported at all.

Most of the conventions below are drawn from {{?I-D.thomson-github-bcp}}.

## Creation of Github organization

We propose that there be a facility in the datatracker interface to allow an area director or working group chair to request the creation of a Github organization for a particular working group. Ideally, this facility would appear both as part of the working group chartering UI as well as the working group page UI.

When an area director or working group chair makes a request to create a Github organization, the following process would be initiated:

1. Create a Github organization for the working group.

2. Name the organization as follows: ietf-\<wgname>-wg

3. Initialize the organization by designating the secretariat and the area directors in the working group's area as owners. If the responsible AD for the working group is from another area, that AD will be an owner as well. 

4. Initialize the organization with a team that has administrator access. This team will consist of the working group chairs and working group secretary, if one exists.

Once the organization is created, the URL for the organization would be added to the working group's page in the datatracker.

Steps 3 and 4 above imply that the Github identities of the organization owners and administrators are known. Recording Github identities in the datatracker (see https://trac.tools.ietf.org/tools/ietfdb/ticket/2548) would facilitate this. The person requesting the organization would need to be notified if the Github identities o any of the people meant to be owners or administrators were not available.

## Personnel changes

When there are personnel changes in the area or the working group, those changes would be reflected in the Github organization.

## Working group closing

When a working group is closed, the team with administrative access would be removed and the owner list would be returned to its initial composition. The organization summary and the repositories within the organization would be updated to indicate that they are no longer under development.

## Creation of document repository

There are many different scenarios and configurations where it might be useful to have automation and/or established administrative conventions for repositories within WG organizations:

- Creating a new repository for an individual draft
- Creating a new repository for an adopted working group draft
- Migrating an existing document repository into the WG organization
- Creating a new repository that contains multiple drafts
- etc.

As an incremental step, we propose initially that there be a facility in the datatracker interface to allow an administrator of an ietf-\<wgname>-wg organization to request the creation of a new repository within that organization for a single document. The document authors would be identified as collaborators. The repository name would be the draft name. Ideally, the repository would be configured with an empty/skeletal draft file, default CONTRIBUTING, LICENSE, and README files, and continuous integration support, in the vein of https://github.com/martinthomson/i-d-template. 

# Working group process

{{?I-D.thomson-github-bcp}} contains discussion of the different possible ways that a working group can use Github and the large number of decisions associated with doing so. This section proposes a minimal set of administrative policies for working groups to follow and the administrative support needed to carry out those policies.

## Contributions

At a minimum, every repository created in a working group organization would incorporate the [boilerplate text](https://trustee.ietf.org/license-for-open-source-repositories.html) from the IETF license file for open source repositories into its CONTRIBUTING file. The CONTRIBUTING file might contain other information as well (see https://github.com/ietf/repo-files/tree/master/contributing-samples for examples).

## Back-up and archival {#archival}

[TBD. Would like to propose a standard way of doing both of these things, but really not sure what to suggest. Best I can come up with now:

For back-up: If we could identify a server endpoint on ietf.org, would be nice if we could automatically back up all repos in orgs that get created via the datatracker using the mechanism described above.

For archival: Is the dummy-account-send-to-a-separate-mailing-list the best we have on this right now?]

  

# Security Considerations

TODO


# IANA Considerations

This document has no IANA actions.



--- back



