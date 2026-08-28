---
layout: default
title: The Source
number: 002
---

# The Source

This section provides the main presentation of your source, as you have prepared it for readers (i.e., a facsimile, transcription, video, audio clip, etc.). This section is where we satisfy the first of the ADE’s three criteria for an electronic edition by providing a rigorous, accurate presentation of historical material.

{% assign media = site.mindoc_media | sort: "order" | where_exp: "item", "item.page == 'source'" %}
{% include media.html pages=media %}

This may also be a space where editorial annotations are provided, such as notes on provenance, archival location, transcription, and more. If possible, a link to the source’s permanent digital location should be included here as well as a citation for that location. This should be done in consultation with the instructors, editorial board, and peer reviewers.
