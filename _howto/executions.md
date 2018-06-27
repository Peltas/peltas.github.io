---
title: Executions
position: 1.4
description: Execution configuration
parameters:
  - name:
    content:
content_markdown: |-
  An execution is a command that will be used to write the data to the target storage. Peltas supports different type of targets such as databases, SOLR, Elastic Search, CSV files, flat files, etc ...
  
  Each data writer consist of its own specific configuration
  {: .warning}
  
  Executions could be chained and each previous execution data is available in the next one (i.e. for referential integrity).
  {: .error }
  
  Below you can see our database writer configuration sample.

left_code_blocks:
  - code_block: |-
      peltas.documentcreated.execution=bi_case
      peltas.documentcreated.executions.bi_case.insert=insert into bi_case (path, creator, created) values(:path, :user, :audit.time)
    title: Database
    language: javascript
  - code_block: |-
      peltas.documentcreated.execution=bi_case,bi_case_action
      peltas.documentcreated.executions.bi_case.insert=insert into bi_case (path, creator, created) values(:path, :user, :audit.time)
      peltas.documentcreated.executions.bi_case_action.insert=insert into batch_bi_case_action (case_id, type, action, "user", "time") values(:bi_case.id, :type, :action, :audit.user, :audit.time)
    title: Chain configuration
    language: javascript
right_code_blocks:
---

