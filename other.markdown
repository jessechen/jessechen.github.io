---
layout: default
title: Index
permalink: /other/
---
<main>
    <h1 class="page-heading">Index of other posts</h1>
    <h2>Humanism</h2>
    <ul>
        {%- for post in site.categories.human -%}
        <li>
            {{ post.date | date: "%Y-%m-%d" }}:
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
        {%- endfor -%}
    </ul>
    <h2>Programming</h2>
    <ul>
        {%- for post in site.categories.programming -%}
        <li>
            {{ post.date | date: "%Y-%m-%d" }}:
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
        {%- endfor -%}
    </ul>
    <h2><a href="https://en.wikipedia.org/wiki/Celestial_Emporium_of_Benevolent_Knowledge">Et cetera</a></h2>
    <ul>
        {%- for post in site.categories.misc -%}
        <li>
            {{ post.date | date: "%Y-%m-%d" }}:
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
        {%- endfor -%}
    </ul>
</main>
