---
layout: default
title: Words
permalink: /words/
---
<main class="words">
    <p>Welcome! Not sure where to start reading? How about one of the posts I'm happiest with:</p>
    <ul>
        <li><a href="{% link _posts/2023-10-17-spam.markdown %}">spam</a></li>
        <li><a href="{% link _posts/2023-09-13-orange.markdown %}">orange</a></li>
        <li><a href="{% link _posts/2024-05-28-roshambo.markdown %}">roshambo</a></li>
        <li><a href="{% link _posts/2025-01-15-minute.markdown %}">minute</a></li>
        <li><a href="{% link _posts/2024-09-24-cologne.markdown %}">cologne</a></li>
    </ul>
    <hr/>
    <h1 class="page-heading">Index of all words</h1>
    <p>
        In this index, I'm doing a thing you should absolutely never do. I'm using significant figures with years instead of writing e.g. "1730s" or "late 14th century", so that they sort in an aesthetically pleasing way. Very, very loosely speaking:
        <ul>
            <li>dates more than 250 years old are accurate to within 10 years</li>
            <li>dates more than 500 years old are accurate to within 30 years</li>
            <li>dates more than 1000 years old are accurate to within 100 years</li>
            <li>dates more than 2000 years old are accurate to within 1000 years</li>
            <li>dates labeled "-3000" could actually be any time before 3000 BCE, we can't really narrow it down any more than that with current methods</li>
        </ul>
    </p>
    <ol>
        {% assign sortedPosts = site.categories.etym | sort: "origin" %}
        {%- for post in sortedPosts -%}
        <li>
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
            ({{ post.origin }})
        </li>
        {%- endfor -%}
    </ol>
</main>
