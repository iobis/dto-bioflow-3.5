
## Introduction 

These notes are part of T3.5 in DTO-Bioflow 




## Trait hierarchy

Trait data can be categorised in following way: 

1. Biological Descriptors: Physical and reproductive characteristics

2. Distribution Descriptors: Geographic and bathymetric distribution

3. Ecological Descriptors: Ecological roles and interactions

4. Species Importance To Society: Socio-economic relevance

But not all data models use this hierarchy 

https://www.coastalwiki.org/wiki/Traits:Marine_species_traits
(above is depcracated?) is this outdated? 

https://marinespecies.org/traits/aphia.php?p=attrdefinitions 

For example, "Body size" is a 'Biological Descriptors" and "Elevation" is a "Distribution Descriptors". 

in WoRMS there are identifiers 

https://marinespecies.org/traits/aphia.php?p=attrdetails&id=296033&tid=276793 

here tid=276793 is the taxon id for *Abalistes filamentosus* https://marinespecies.org/traits/aphia.php?p=taxdetails&id=276793#attributes and the attribute is 
"296033" which is 

API provides more information 
https://www.marinespecies.org/rest/AphiaIDsByAttributeKeyID/296033?offset=1 
https://www.marinespecies.org/rest/AphiaAttributeKeysByID/15

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

See also https://www.marinespecies.org/rest/AphiaAttributesByAphiaID/126436 
https://marinespecies.org/traits/aphia.php?p=attrdetails&id=296033&tid=276793

