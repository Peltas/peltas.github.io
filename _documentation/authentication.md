---
title: Authentication
position: 3
parameters:
  - name:
    content:
content_markdown: |-  
  Standard Basic HTTP Authtentication.
  {: .success }

  HTTPS => Basic HTTP over SSL.
  {: .info }

  Kerberos Authentication
  {: .warning }
  
  X.509 Certificate Authentication.
  {: .error }
  
  For Alfresco Audit audit, we use the same authentication that you already have in your Alfresco autehntication chain. And for Alfresco live workspace data, we use the authentication mechanism you have in place 
  between SOLR and Alfresco.

left_code_blocks:
  - code_block:  |2-
      peltas.auth.type=basicauth|x509
    title: Authentication type
    language: javascript
right_code_blocks:
  - code_block: |2-
       peltas.auth.basic.username=YOUR_username
       peltas.auth.basic.password=YOUR_password
    title: HTTP Basic
    language: javascript
  - code_block: |2-       
       peltas.ssl.keystoreType=JCEKS
       peltas.ssl.trustStore=PATH...
       peltas.ssl.trustStorePass=xxxx
       peltas.ssl.hostVerify=false
    title: HTTPS
    language: javascript
  - code_block: |2-
       TBD
    title: Kerberos
    language: javascript
  - code_block: |2-
       peltas.auth.x509.keyStore=PATH...
       peltas.auth.x509.keyStorePass=xxxx
       peltas.auth.x509.keystoreType=JCEKS
    title: Cert
    language: javascript
---