---
title: Action evaluator
position: 1.0
type: new
description: An evaluator is used in order to check if an entry should be processed.

content_markdown: |-
  Once the condition is satisfied the extraction will start in Peltas and all the mapping properties will be processed. 
  {: .info }

  Evaluators could be combined with an "\|" (pipe charachter) operator, which represents an "AND".
left_code_blocks:
  - code_block: |-
      peltas.documentcreated.evaluator=/alfresco-access/transaction/action=CREATE
    title: Simple configuration
    language: javascript
  - code_block: |-
      peltas.documentcreated.evaluator=/alfresco-access/transaction/action=CREATE|/alfresco-access/transaction/type=cm:content
    title: AND configuration
    language: javascript
  - code_block: |-
      peltas.documentcreated.evaluator=/alfresco-access/transaction/aspects/add=contains<>{http://www.alfresco.org/model/content/1.0}versionable
    title: Aspect based evaluation
    language: javascript
right_code_blocks:
  - code_block: |-
      {
        "id": 77,
        "application": "alfresco-access",
        "user": "admin",
        "time": "2018-05-26T17:16:36.371+02:00",
        "values": 
        {
          "/alfresco-access/transaction/action": "CREATE",
          "/alfresco-access/transaction/type": "cm:content"
        }
      }
    title: Audit entry
    language: json
---