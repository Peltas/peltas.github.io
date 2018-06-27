---
title: Properties
position: 1.1
description: Property mapping
content_markdown: |-
  Any Alfresco property or aspect can be tracked and mapped. While a single valued property is easily understood, a property with a list of values would need extra configuration in order to map the data. Therefor, Peltas offers processing of data collections too.
  {: .success}

  This is how we can map/format an audit property and/or an Alfresco property. Also note, that a property could converted to another Java type, a Date for instance.
left_code_blocks:
  - code_block: |-
      peltas.documentcreated.mapper.property.path.data=/alfresco-access/transaction/path
    title: Extract single value
    language: bash
  - code_block: |-
      peltas.documentcreated.mapper.property.creator.data=/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/content/1.0}creator
    title: Extract an Alfresco property
    language: bash
  - code_block: |-
      peltas.documentcreated.mapper.property.author.data=/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/content/1.0}author
      peltas.documentcreated.mapper.property.nodeRef.format=%s://%s/%s
      peltas.documentcreated.mapper.property.nodeRef.data=/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/system/1.0}store-protocol,/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/system/1.0}store-identifier,/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/system/1.0}node-uuid
    title: Complex format
    language: bash  
  - code_block: |-
      peltas.documentcreated.mapper.property.created.data=/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/content/1.0}created
      peltas.documentcreated.mapper.property.created.type=java.util.Date
    title: Java type conversion
    language: bash
  - code_block: |-
      peltas.documentcreated.mapper.property.description.data=/alfresco-access/transaction/properties/add@{http://www.alfresco.org/model/content/1.0}description
      peltas.documentcreated.mapper.property.description.type=java.util.HashMap
    title: ML Text
    language: bash
right_code_blocks:
  - code_block: |-
      {
        "id": 77,
        "application": "alfresco-access",
        "user": "admin",
        "time": "2018-05-26T17:16:36.371+02:00",
        "values": 
        {
          "...": "...",
          "/alfresco-access/transaction/path":"/app:company_home/cm:Flow Reporting Data Spec.xlsx",
          "/alfresco-access/transaction/properties/add":"{{http://www.alfresco.org/model/content/1.0}creator=admin,{http://www.alfresco.org/model/content/1.0}created=Mon May 28 10:24:42 CEST 2018}"
        }
      }
    title: Audit entry
    language: json
  - code_block: |-
      {
        "values": 
        {
          "...": "...",
          "/alfresco-access/transaction/path":"/app:company_home/cm:Flow Reporting Data Spec.xlsx",
          "/alfresco-access/transaction/properties/add":"{{http://www.alfresco.org/model/system/1.0}node-uuid=86b50e20-9bb1-4942-bd2d-96f83c4a7843, {http://www.alfresco.org/model/system/1.0}store-protocol=workspace, {http://www.alfresco.org/model/system/1.0}store-identifier=SpacesStore"
        }
      }
    title: Complex format
    language: json
---