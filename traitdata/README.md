
## Introduction 

These notes are part of T3.5 in DTO-Bioflow 

We are using DUC (https://github.com/iobis/dto-bioflow-3.5/issues/30) for use case data. 


## Trait hierarchy

Trait data often categorised in following way: 

1. Biological Descriptors: Physical and reproductive characteristics

2. Distribution Descriptors: Geographic and bathymetric distribution

3. Ecological Descriptors: Ecological roles and interactions

4. Species Importance To Society: Socio-economic relevance

But not all data models use this hierarchy 

The above is referneced in this documentation (https://www.coastalwiki.org/wiki/Traits:Marine_species_traits) but this seems to be depcracated. 

WoRMS currently has different hierarchical model. 

For example, "Body size" is a 'Biological Descriptors" and "Elevation" is a "Distribution Descriptors" in the DUC datasets. 

BUT 

WoRMS hierarchy is more like Parent trait -> Child trait, however expressed within measurementID, category, measurementType (darwin core extension)  


API response: 
https://www.marinespecies.org/rest/AphiaAttributeKeysByID/15

In this case category is Null but, see id "12" below 

```
[
  {
    "measurementTypeID": 15,
    "measurementType": "Body size",
    "CategoryID": null,
    "children": [
      {
        "measurementTypeID": 17,
        "measurementType": "Unit",
        "CategoryID": 11,
        "children": []
      },
      {
        "measurementTypeID": 18,
        "measurementType": "Type",
        "CategoryID": 14,
        "children": []
      },
      {
        "measurementTypeID": 19,
        "measurementType": "Dimension",
        "CategoryID": 15,
        "children": []
      },
      {
        "measurementTypeID": 20,
        "measurementType": "Life stage",
        "CategoryID": 8,
        "children": []
      },
      {
        "measurementTypeID": 21,
        "measurementType": "Sex",
        "CategoryID": 12,
        "children": []
      },
      {
        "measurementTypeID": 22,
        "measurementType": "Locality (MRGID)",
        "CategoryID": null,
        "children": []
      },
      {
        "measurementTypeID": 42,
        "measurementType": "Corresponding width",
        "CategoryID": null,
        "children": []
      },
      {
        "measurementTypeID": 43,
        "measurementType": "Corresponding length",
        "CategoryID": null,
        "children": []
      }
    ]
  }
]
```
and 
https://www.marinespecies.org/rest/AphiaAttributeKeysByID/12

Here CategoryID 8 (https://www.marinespecies.org/rest/AphiaAttributeValuesByCategoryID/8) which deals with Life Stage. 

```
[
  {
    "measurementTypeID": 12,
    "measurementType": "Life stage",
    "CategoryID": 8,
    "children": []
  }
]
```

Even though WoRMS uses "Attribute" as a term this is tied with measurementTypeID. 

>"For body size, WoRMS makes the distinction between quantitative and qualitative body size. While quantitative body sizes are numerical values (e.g. 10 mm minimum length for the adult), qualitative body sizes refer to size classes. To document the qualitative body size, four size classes were agreed upon by the WoRMS Steering Committee: Microbiota (< 0.2 mm), Meiobiota (0.2 – 2.0 mm), Macrobiota (2.0 - 200 mm) and Megabiota (> 200 mm). We are aware that other classifications can have different size boundaries, but these size classes were chosen by the WoRMS SC to be applicable to most taxa in WoRMS."

Reference: https://www.marinespecies.org/news.php?p=show&id=9034

What this means for data model/API 
Example: WoRMS has '2.0 - 200 mm' as a body size value but The term 'Macrobiota' is used informally in documentation but is NOT in the API/data structure. 


Connection with taxon id: 

https://marinespecies.org/traits/aphia.php?p=attrdetails&id=296033&tid=276793 

here tid=276793 is the taxon id for *Abalistes filamentosus* 

