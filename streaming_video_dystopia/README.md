"MARC records" provided by a streaming video content provider. 

I have removed the 856 fields to protect the guilty. 

Other than that: 
 - the .mrc file is the original "MARC" downloaded from their content platform. 
 - .xml generated with MarcEdit's MARC21 -> MARC21XML default
 - .mrk is easily human-readable "MarcEdit Mnemonic" format created with MarcEdit
 
From my comments sent to content provider: 

 - LDR: tells the catalog system that this is a record for a BOOK, not a VIDEO
 - 008: completely invalid. This is a crucial field for coding some of the most important info about a resource in a machine-readable way that we use heavily for format scoping, date range search, and limiting by language in the public catalog. SHOULD look like: `140725s1981    cau091        o   vleng d`
 - **NOTHING** in the record specifies the format of the material described by the record. In current cataloging, at least the following should be present in addition to properly coded LDR, 008, 006, and 007 fields: 

```
336  \\$atwo-dimensional moving image$tdi$rdacontent
337  \\$acomputer$bc$2rdamedia
338  \\$aonline resource$bcr$2rdacarrier
```

 - 130 should contain standardized, controlled form of 245 title, as listed in library authority databases. As it is, they are sending the exact same thing to 245$a and 130$a so the 130 is irrelevant
 - Inclusion of identical 260 and 264 fields. 260 was used in MARC records formulated according to AACR2 cataloging rules. 264 is formulated according to the current RDA cataloging rules. You don't use both. Since it's clear **no** standard is being followed, might as well choose the new/more specific 264 field
 - 300 duplicates the invalid 008. 300 *should* look like one of the following (from worst to best). Err on side of less info over potentially providing inaccurate info:

```
300  \\$a1 online resource
300  \\$a1 online resource (1 video file)
300  \\$a1 online resource (1 video file (91 min.))
300  \\$a1 online resource (1 video file (91 min.)) :$bsound, color
```

 - No 700 access point for director
 - Names included in 700 fields are not even in the inverted form (Lynch, David) required to make them basically useful/consistent within a library catalog. They *should* be authorized forms of names taken from library authority files: http://authorities.loc.gov/ or http://id.loc.gov/authorities/names.html or https://viaf.org/ 


