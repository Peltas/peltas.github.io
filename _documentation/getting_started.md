---
title: Getting Started
position: 2
description: Peltas for Alfresco can be configured to process Alfresco Audit data or Alfresco live workspace data sources.
parameters:
  - name:
    content:
content_markdown: |-

  Alfresco Audit nodes extraction
  {: .success }

  Alfresco live workspace data processing and extraction
  {: .info }

  Custom Alfresco audit applications processing
  {: .warning }
  
  Write results to any JDBC database or any other custom target such as Elastic Search, flat files or REST APIs.
  {: .error }
  Peltas entry points are "evaluators", which triggers the processing of an entry. After the trigger has been recognized we process the mapped properties and store them to the target storage with different executions.
  
left_code_blocks:
  - code_block: |2-
       peltas
         documentcreated
           evaluator: /alfresco-access/transaction/action=CREATE
           mapper
             property
             action.data: /alfresco-access/transaction/action
             user.data: /alfresco-access/transaction/user
           execution: batch_bi_case
           executions
             batch_bi_case
               insert: insert into batch_bi_case (creator, created, ...) values(:user, :audit.time, ...)
    title: Yaml config
    language: yaml
  - code_block: |2-
       peltas.documentcreated.evaluator=/alfresco-access/transaction/action=CREATE
       peltas.documentcreated.mapper.property.action.data=/alfresco-access/transaction/action
       peltas.documentcreated.mapper.property.user.data=/alfresco-access/transaction/user	   
       peltas.documentcreated.execution=batch_bi_case
       peltas.documentcreated.executions.batch_bi_case.insert=insert into batch_bi_case (creator, created, ...) values(:user, :audit.time, ...)
    title: Properties config
    language: bash
right_code_blocks:
  - code_block: |2-
      peltas.datasource.url= jdbc:...
      peltas.datasource.driverClassName= ..
      peltas.datasource.username= ...
      peltas.datasource.password= ...
    title: JDBC connection
    language: javascript
---