---
layout: page
permalink: /blog/
title: Blog Posts
---

<div class="external-posts">
  <section >
    <ul>
    {% for post in site.posts %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>, {{ post.date | date: "%B %e, %Y" }}
      </li>
    {% endfor %}
    </ul>
  </section>

  <section class="external-posts">
    <h2>External Posts</h2>
    <ul>
      <li><a href="https://community.blockcerts.org/search?q=kim">Blockcerts Posts</a></li>
      <li><a href="https://kimdhamilton.wordpress.com/">HBase, Hadoop Posts</a></li>
      <li><a href="https://learn.microsoft.com/en-us/archive/blogs/bclteam">.NET Base Class Libraries Posts</a>: <i>Collections, Resource Manager, IO, contracts, performance, and Serial Port</i></li>
    </ul>
  </section>
</div>
