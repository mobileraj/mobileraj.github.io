---
layout: post
title: "On Right Location?"
description: "Exploring challenges arund the location context"
category: 
tags: [geolocation,mobile]
---
{% include JB/setup %}

This post explores some thinking around the challenges surrounding the concept of location in a mobile scenario. For this paper, our assumption is that of a user carrying a smart phone or some wearable that has enough compute power to react to the notion of where it is at (location). This reaction can be it passively sending the location info or actively engaging the user into a newer experience.
### Micro and macro
Since the user can be in a confined manmade structure (as in visiting a mall or a store in a mall or running to an ER) or moving across a larger area (like a city block, driving cross country, climbing a mountain) we need to treat them separately, as they have unique technical and behavioural challenges. Hence we introduce the concept of micro and macro locations.
Micro-location are region/area definition for a range of centimeters to few meters. These are tagged area/region as defined by the technology used in identifying that region.

### Earth is flat
In most models of the earth, its gets a planar treatment. For small areas the curvature of the earth doesnt manifest itself and the notion of a flat earth is a great approximation for us to treat various properties of the location in question. This includes things like a few acres of land, driving in your favourite city blocks or exploring a maze in your office buildings.
There are other variation in the non-planar earth model starting with the simpler spherical and the more elaborate ellipsoidal. If you ever have seen words like Mercator projection or Robinson projection, its trying to project a geometry (point, line or polygon) as represented on real earth onto a flat surface such as a map.

### Space and time
Capturing the static image of a location or events in a given area as a map is interesting but it gets more informative when the time dimension is added. With time you can better comprehend events and processes occuring in space, which provides the rich insight so desired in making the right decisions. 

### Additional datatypes
We have already seen that location constructs introduces the notion of a geometry data type in how we capture information. Starting with a simple point (lat/lon) to line (an ordered pairs of points) to polygon (an ordered pairs of points that is closed), the data to be stored and indexed for supporting the queries is much different than typical textual or numerical data. Queries also come in several forms to answer spatial questions such as if a point is *within* a polygon or if two lines *intersect* or if a point is *beyond* a given line by some distance and so on. This needs to be accommodated in how the data is stored and indexed but also at scale. The database research has produced several clever store and indexing schemes to support effective retrieval of spatial and temporal data. 

### Battery, connectivity and such
Since the location data is typically being collected on smart devices, we need to worry about several uncertainities such as battery drain when location is collected more often. Or what happens if there is an error in GPS reading. There is also the loss of connectivity during data transmission of the collected data andif you were paying for a crappy data plan, then to accommodate effective ways to send location data without incurring undue costs.

There are many more areas that we will cover as we explore key location usecases and scenarios over the next posts, but this should get you some appreciation of why location is unique in what we need to address for a effective solution around using location data.

Until next time..keep moving.


