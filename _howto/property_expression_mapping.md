---
title: Expressions
position: 1.3
description: Expression property mapping
content_markdown: |-
  Peltas expressions can be seen as virtual properties. Where an expression property always references a mapped property and provides a facility to change the format or convert the data value. The property has to be prefixed with prop: in oprder to be considered as an expression and it has to reference a preivously configured property.
left_code_blocks:
  - code_block: |-
      peltas.documentcreated.mapper.property.createdFormatted.data=prop:created
      peltas.documentcreated.mapper.property.createdFormatted.format=yyyyMMdd
      peltas.documentcreated.mapper.property.createdFormatted.type=java.lang.String
    title: Expression configuration
    language: bash
right_code_blocks:
---