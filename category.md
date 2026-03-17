---
layout: default
title: Index
permalink: /category/
---
<main>
    <h1 class="page-heading">Index of all posts by category</h1>
    <p>Welcome! Not sure where to start reading? How about one of the posts I'm happiest with:</p>
    <ul>
        <li><a href="{% link _posts/2023-10-17-spam.md %}">spam</a></li>
        <li><a href="{% link _posts/2026-02-18-vitamin.md %}">vitamin</a></li>
        <li><a href="{% link _posts/2025-01-15-minute.md %}">minute</a></li>
        <li><a href="{% link _posts/2023-09-13-orange.md %}">orange</a></li>
        <li><a href="{% link _posts/2024-09-24-cologne.md %}">cologne</a></li>
    </ul>
    <p>Or browse <a href="{% link date.md %}">all posts by date</a>, or <a href="{% link words.md %}">all etymologies by year of origin</a> instead.</p>
    <hr/>

    <h2>On being human</h2>
    <ul>
        {%- for post in site.categories.human -%}
        <li>
            {{ post.date | date: "%Y-%m-%d" }}:
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
        {%- endfor -%}
    </ul>
    <h2>On programming</h2>
    <ul>
        {%- for post in site.categories.programming -%}
        <li>
            {{ post.date | date: "%Y-%m-%d" }}:
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
        {%- endfor -%}
    </ul>
    <h2>On histories of words</h2>
    <ul>
        {%- for post in site.categories.etym -%}
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
