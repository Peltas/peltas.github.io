---
title: Transactions
position: 4
parameters:
  - name:
    content:
content_markdown: |-
  Transactions are handled by batch job chunks. Peltas handles in a safe manner where the last job has left and 
  once Peltas is restarted the new job will continue its processing from the correct entry.
left_code_blocks:
  - code_block: |-
      peltas.chunksize=10
    title: Chunksize
    language: javascript
right_code_blocks:
  - code_block:
    title:
    language:
---