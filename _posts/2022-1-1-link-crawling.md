---
title: Wikipedia link crawling
layout: single
classes: wide
last_modified_at: 2022-1-7
excerpt: ""
---

Weekend project that started from the thought that what kind of a graph would Wikipedia pages form if **each node is a wiki page** and **each edge denotes that one page is linked to another**. Or if randomly starting from different pages, would the networks converge toward one or multiple pages? That is, is there a Wikipedia page that is linked to all (or most) other wikipedia pages?

## Problems
As mentioned this was a quick weekend project and traversing the wikipedia pages using HTML requests isn't really the most efficient approach. Taking into account wikipedia has over billion pages ```GET``` become infeasible very fast also causing unnecessary load on the Wikipedia servers. 

Another way of approaching this would be downloading the Wikipedia pagelinks SQL dump. Only problem with this is this would require a decently beefy dedicated computer. With suggested [improvements](https://stackoverflow.com/questions/43954631/issues-with-wikipedia-dump-table-pagelinks) I was able to read approximately ~7000 rows/s which would mean importing the well over billion rows of data would have taken 2-3 days. 

## Example output 

The following Plotly plot shows a very rudimentary test of link crawling (using `GET` requests) starting from Finland's wikipedia pages. On each page max 5 links are taken and the crawling is stopped to link depth 4. The graph contains 82 nodes, 101 edges and creating it took `61` seconds.

**NOTE!** it is an interactive plot that can be panned / zoomed etc.

<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" 
src="/assets/link_grapher_example_finland.html" height="1000" width="100%"></iframe>

## Future improvement ideas?

* Instead of `HTTP` requests import the wikipedia pagelinks dump to a local database (problems with size...?)
* Visualization improvements:
   * Graph node size determined by some parameter, e.g. node out degree (number of links on page) or some other metric?
   * Similarly edge coloring / size determined by some metric
* Graph mining:
   * Do all Wikipedia pages come back to some central article?
   * Algorithms e.g. PageRank 
