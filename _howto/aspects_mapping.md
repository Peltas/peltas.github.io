---
title: Aspects
position: 1.5
description: Aspects and collection values mapping

content_markdown: |-
  List of aspects can be seen as any Alfresco multi valued property and that is how Peltas access such data. A collection is configurable from within an execution.
left_code_blocks:
  - code_block: |-
      peltas.documentcreated.executions.bi_case_action.collections.aspect.key=/alfresco-access/transaction/aspects/add
      peltas.documentcreated.executions.bi_case_action.collections.aspect.insert= insert into bi_case_action_aspect (action_id, aspect) values(:bi_case_action.id, :aspect)
    title: Aspect
    language: javascript
  - code_block: |-
      peltas.documentcreated.executions.bi_case_action.collections.myMultiProperty.key=/alfresco-access/transaction/properties/add@{http://www.acme.org/model/1.0}multiValue
      peltas.documentcreated.executions.bi_case_action.collections.myMultiProperty.insert= insert into bi_case_action_aspect (action_id, aspect) values(:bi_case_action.id, :myMultiProperty)
    title: Multi value property
    language: javascript
right_code_blocks:
---