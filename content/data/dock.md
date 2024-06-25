---
date: 2024-06-14
title: Test Docker taxonomy
draft: false
dockers:
- 3dprinters
- accessproxy
- adult
- ai
- analytics
- anitvirus
- audio
- authentication
- authenticationserver
- automation
- backup
- backupandsyncserver
- books
- calendar
- cctv
- chat
- chatserver
- cloud
- cms
- codeserver
- comics
- continuousintegration
- crypto
- dashboard
- dashboardserver
- database
- databaseserver
- development
- devops
- devtools
- dns
- docker
- documentation
- documents
- downloader
- downloaders
- drawing
- ebooks
- edge
- email
- employee
- entertainment
- familyappserver
- feedreader
- filebrowsers
- filemanagement
- files
- finance
- fitness
- forum
- ftp
- ftpserver
- games
- gamingserver
- graphicdesign
- helpdesk
- homeautomation
- identitymanagement
- knowledgebase
- learning
- library
- libraryserver
- linksharing
- llm
- logmanagement
- lowcode
- mail
- maintenance
- management
- managementutilityserver
- marketing
- media
- mediaappbooks
- mediaappvideo
- mediamanagement
- mediaserver
- mediaservermusic
- mediaserverphotos
- mediaservervideo
- messaging
- messenger
- metrics
- monitor
- monitoring
- multimedia
- music
- musicserver
- network
- networking
- networkother
- networkserver
- networkweb
- news
- nocode
- NONE
- notesserver
- offline
- operatingsystem
- ops
- other
- paas
- pdf
- pdftools
- photography
- photos
- podcast
- portainer
- presentation
- productivity
- projectmanagement
- proxy
- proxyserver
- remotecontrol
- research
- search
- searchengine
- security
- serverless
- smarthome
- social
- statusstable
- storage
- streaming
- system
- taskserver
- timerelated
- timetracking
- tool
- tools
- tracking
- utilities
- utilitybackup
- video
- voice
- vpn
- vpnserver
- web
- webplatform
- webserver
- wiki
- wordpress
---

## Dock

### What works
* This page holds all the tags from the json
* When in Draft mode (hugo server -D) you will get the current list from the json & wou will need to update the front end code with this info
* the term pages work like a charm: [/data/dockers/wiki/](/data/dockers/wiki/)

### What doesn't work yet
* The overview taxonomy page is not yet on the correct page 
    * I want: [/data/dockers/](/data/dockers/) - it shows a _default/list.html and not the _default/taxonomy.html.
    * I have: [/dockers/](/dockers/) - this show the correct _default/taxonomy.html, but is in the wrong place.

{{<pt-taxonomy>}}
