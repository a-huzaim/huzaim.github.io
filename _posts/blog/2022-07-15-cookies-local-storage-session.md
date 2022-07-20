---
layout: posts
title: "Cookies vs Local Storage vs Session"
slug: "Cookies vs Local Storage vs Session"
permalink: /blog/:slug:output_ext
author_profile: true
---

We all have used these browser storages at different points, but sometimes we tend to wonder which is best for what. Hence a small attempt to conclude the differences and similarities.

<script src="https://gist.github.com/Huzaim/8ee6d00eb8582c93721e07958c00d2ed.js"></script>

Any of these mentioned storage mechanisms are browser independent. Chrome cannot access what's saved within Firefox.

Cookies are a small text file placed on the computer by the web site. They were used to store information about users visiting the app or website, shopping cart items, user browsing habits or any other options changed by the user.

Why do we really need cookies? HTTP is stateless, and each request that is sent to the server is perceived as a fresh request by the server. Hence cookies are helpful to identify from where the request originated from.

The cookies will be sent back and forth with every request and response between the client and the server. Hence we should be vigilant, not to over use cookies, otherwise it will increase the network response time.

Cookies does not have rich API support to interact with them. You can use the `Document.cookie` property create new cookies using javascript.

`document.cookie = 'name=Scott'`

The cookies can be utilized as either Session or Persistent cookies based on the expiration.
Session cookies are stored in temporary memory while Persistent cookies are saved in the disk.

To make things easier the Web Storage API was introduced along with HTML5, namely Local Storage and Session Storage.

If you're saving something which is specific to the particular user, perhaps a Web API storage is more ideal. If the information needs to be sent to the server, cookies are the ones to be utilized.

The Web API storage can be added, accessed and removed with the following syntax.

```
localStorage.setItem('name', 'bob')
localStorage.getItem('name')
localStorage.removeItem('name')

sessionStorage.setItem('name', 'bob')
sessionStorage.getItem('name')
sessionStorage.removeItem('name')
```

Here the data will not be sent back and forth with every HTTP request. The difference between Local Storage and Session Storage is that the session storage deletes its data, once the tab is closed. And multiple tabs of the same Url will have multiple independent session storage.

Everything has its trade offs, and we have to utilize which is best for what. Hope this gave some insight.

References

https://flaviocopes.com/cookies/#introduction

https://qubiter.medium.com/the-types-of-storage-in-browser-cd6ec9577c8e

https://medium.com/swlh/cookies-vs-localstorage-whats-the-difference-d99f0eb09b44
