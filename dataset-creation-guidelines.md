# How to Create Datasets for Different NLP Problems

## Table of contents

1. [Named Entity Recognition Dataset Guide](#named-entity-recognition)
2. [Translation Dataset Guide](#Translation)


## Named Entity Recognition

Named Entity Recognition (NER) is a classification task that identifies words in a text that refer to entities or predefined categories (such as dates, person, organization and location names). 

Example of NER: John [PERSON] is going to Kenya [LOCATION] on Monday [DATE]

<use a diagram>

For annotation, we will be following the Message Understanding Conference (MUC-6) named entity definition guideline for identifying Persons, organizations, locations, dates and times, see https://cs.nyu.edu/faculty/grishman/NEtask20.book_1.html

### Person Annotation [PER]
1) Personal names (including firstnames, middle names and last names) should be tagged excluding titles e.g Mr, Mrs, President, Professor, et.c

Examples:

> President Donald [PER] Trump [PER]

> Donald [PER] Trump [PER] Jr. [PER]

2) Family names should be tagged.

Example:
 > The Kennedy [PER] family
 > Abiy [PER] Ahmed's [PER] wife. 

Some tokenization may separate "Ahmed" and "'s", in that case, we have, For example in CoNLL format, where 'O' is no label.

> Abiy, PER
> Ahmed, PER
> 's, O
> wife, O

3) Personal names that refers to an organization, location, events, law, disease, prizes should not be tagged. Example,

St. Michael
Nobel Prize

George [PER] Washington [PER] was born in 1732.
George Washington University was established in 1821.
The White House is located in Washington.


### Organization Annotation [ORG]
1) Corporate designators such as "Co." are organizations
Example
The Bridgestone [ORG] Sports [ORG] Co. [ORG]

2) Proper names that includes sports teams, stock exchanges, multinational organizations, political parties, unions, government parastatal. Many of them comes in abbreviations e.g WHO, NCDC, NASDAQ, EU, AU

The World [ORG] Health [ORG] Organization [ORG]
AU [ORG]

3) Proper names referring to facilities e.g factories, hotels, universities, airports, hospitals, churches except (a) the name is clearly the name of the structure/place and not of an organization, or (b) the name is known to be the name of an organization but is used only in reference to the facility as a structure/place. 
Example:

The Frankfurt [ORG] Airport [ORG] Management have new rules for Aircraft.

I am traveling from the Frankfurt Airport .....will not be tagged

I will stay at the IBIS [ORG] Hotel [ORG]

The Supreme [ORG] Court [ORG] of [ORG] Nigeria [ORG]

The convict will be taken to court.

The patient will be transferred to the General [ORG] Hospital [ORG] Ikoyi [ORG].

The patient is in the hospital.


### Location Annotation [ORG]

1) All country names,region names, state names and city names 
United [LOC] States [LOC] of [LOC] America [LOC]
USA [LOC]
Cape [LOC] Town [LOC]
Niger [LOC] Delta [LOC] Region [LOC]

2) Multiword expressions in which place names are separated by a comma are to be tagged as separate instances of LOCATION.

Example:
Cairo [LOC], Egypt [LOC]
Washington [LOC] , D.C. [LOC]

3) Do not label Nationalities and street addresses as locations.
 An American is traveling to Abuja [LOC]
 A Nigerian hospital
 53140 Gatchell Road

4) Place names can sometimes be part of an organization. The annotation will follow these guidelines: (1) If there is a corporate designator, it marks the end of the organization name; (2) if there is no corporate designator, the "of <place-name>" is part of the organization name.

Example:
Hyundai [ORG] of [ORG] Korea [ORG] , [ORG] Inc. [ORG]
Hyundai [ORG], [ORG] Inc.[ORG] of Korea [LOC]
John [PER] is working in BOSCH [ORG], Germany [LOC].
University [ORG] of [ORG] California [ORG] in Los [LOC] Angeles [LOC]



### DATE Annotation [DATE]
 Tag all absolute and relative dates or periods, including days, months, years. We could combine DATE and TIME annotation as [DATETIME]

1) Absolute date expressions are to be tagged. Absolute date expression must indicate a specific segment of date i.e the particular day, season, financial quarters, years, decade or a particular century:
Example:
Monday [DATE]
10th [DATE] of [DATE] October [DATE]
April [DATE] 6[DATE],[DATE] 2020 [DATE]
Summer [DATE]
the Autumn [DATE] report
Winter [DATE] 2020 [DATE]
fourth [DATE] quarter [DATE]
third [DATE] quarter [DATE] of [DATE] 1991 [DATE]
first [DATE] half [DATE] of [DATE] the [DATE] year [DATE]
1995 [DATE]
1980s [DATE] 
19th [DATE] century [DATE]

2) Relative time expressions should also be tagged.
Example:
July [DATE] last [DATE] year [DATE]
this [DATE] June [DATE]
next [DATE] summer [DATE]
thirty [DATE] days [DATE] before [DATE] the [DATE] end [DATE] of [DATE] the [DATE] year [DATE]

3) Special days, such as holidays, that are referenced by name should be tagged
Example:
because of the observance of All [DATE] Saints' [DATE] Day [DATE]
The Christmas [DATE] day [DATE]

4) Expression indicating periods between two dates should be tagged. 
Example:
We are on vacation between [DATE] July [DATE] 1 [DATE] and [DATE] July [DATE] 8 [DATE]
Her visit is from [DATE] July [DATE] 1 [DATE] and [DATE] July [DATE] 8 [DATE]


### TIME Annotation [TIME]
This refers to times smaller than a day.

1) Absolute time expressions are to be tagged. Absolute time expression must indicate a specific segment of time i.e a particular minute and hour. 
Example:
20 [TIME] minutes [TIME] after [TIME] 10 [TIME]
midnight [TIME] 
twelve [TIME]  o'clock [TIME]  noon [TIME] 
noon [TIME] 
5 [TIME] p.m. [TIME] EST [TIME]
5:40 [TIME]

2) Time expression including the city time zone should be tagged
Example:
1:30 [TIME] p.m. [TIME] Chicago [TIME] time [TIME]

3) Expression indicating periods between two time should be tagged. 
Example:
The election is from 2 [TIME] p.m.[TIME] to 4 [TIME] p.m. [TIME]


## Translation

TODO
