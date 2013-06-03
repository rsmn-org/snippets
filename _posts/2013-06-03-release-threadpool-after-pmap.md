---
layout: post
title: Release Threadpool after pmap usage
---

#{{page.title}}
When using a parallel map function in Clojure, your programm doesn't terminate immediately after the last statement. Using pmap generates a Threadpool, waiting for work to be done. To release the Threadpool, you might manually shut it down.

     (do
       (pmap mapping-function coll)
       (shutdown-agents))