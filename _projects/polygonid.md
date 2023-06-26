---
title: "PolygonID"
last_modified_at: 2023-06-09T16:20:02-05:00
excerpt: "Big Data Polygon Gmaps at the provincial level to sub-districts throughout Indonesia based on 2004 BPS data"
share: true
header:
  image: /assets/images/polygonid.jpg
  teaser: /assets/images/polygonid.jpg
  overlay_image: /assets/images/unsplash-image-2.jpg
  og_image: /assets/images/polygonid.jpg
  caption: "Photo credit: Batax Developer"
  actions:
    - label: "DEMO"
      url: "https://polygonid.bataxdev.com"
categories:
  - API
tags:
  - ExpressJS
---

Clone repository using command <code>git clone https://github.com/bachtiarpanjaitan/polygonid.git</code>

**Initialize Install**

make sure you install all required package with ```npm install```

**Export db from mysql**

```
mysql2sqlite -f db.polygonid -d polygons -u root -t provinces districts sub_districts
```

**Run APP**

 ``` 
 PORT=5000 DEBUG=polygonid:* npm start 
 ```
 or 
 
 ```
 node app.js
 ```

**Try it**

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/3228973-2490d44e-5035-4b65-93b6-82b4d42f960a?action=collection%2Ffork&collection-url=entityId%3D3228973-2490d44e-5035-4b65-93b6-82b4d42f960a%26entityType%3Dcollection%26workspaceId%3D47673369-1803-4695-bf5a-735e67e12b14)
