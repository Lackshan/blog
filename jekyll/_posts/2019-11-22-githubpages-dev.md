---
layout: post
title: "Setting up GitHub Pages with a Namecheap .dev domain"
date: 2019-11-22 12:22:34
categories: 
---
I ran into some trouble trying to get GitHub Pages to work with this domain. I was unable to enforce HTTPS (which is a requirement for a .dev domain) which resulted in the site being unaccessable due to an SSL error. Upon further investigation it appeared the problem was twofold: firstly the site referenced assets over HTTP and secondly I needed to create A records pointing to the IP addresses for GitHub Pages:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

I was able to get GitHub Pages to enforce HTTPS but actually accessing the site still gave me an SSL error. The culprit turned out to be the CNAME record that Namecheap created by default to point the domain to their parking page[http://parkingpage.namecheap.com/] because it's only available over HTTP! Deleting it got everything working.

**TL;DR**: Delete the CNAME record pointing your domain to Namecheap's parking page.