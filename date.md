---
layout: default
title: Index
permalink: /date/
---
<main>
    <h1 class="page-heading">Index of all posts by date</h1>
    <ul>
        {%- for post in site.posts -%}
        <li>
            {{ post.date | date: "%Y-%m-%d" }}:
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
        {%- endfor -%}
    </ul>
</main>
