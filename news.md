---
title: news
permalink: /news/
---

### **News from the lab**

<div class="content list">
  {% assign news_posts = site.posts | where_exp: "post", "post.categories contains 'news'" | sort: "date" | reverse %}
  {% for post in news_posts %}
    <div class="list-item">
      <div class="row">
        <div class="col-sm-12">
          <p class="list-post-title">
            <span class="post-title" style="font-size: 1rem; font-weight: 600;">{{ post.title }}</span>
            &nbsp;·&nbsp;
            <span class="list-post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
          </p>
          <div class="list-detail">
            {{ post.content }}
          </div>
        </div>
      </div>
      <hr/>
    </div>
  {% endfor %}
</div>
