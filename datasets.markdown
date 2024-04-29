---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Datasets
permalink: /datasets/
---

{% for dataset in site.datasets %}
<div class="software-container">
    <h2>
        {{ dataset.name }}
    </h2>
    {%- if dataset.icon -%}
    <img src="/assets/images/datasets/{{ dataset.icon }}" class="dataset-icon" alt="{{ dataset.name }}" loading="lazy"/>
    {%- endif -%}
    {%- if dataset.datasets -%}
    <h4>Datasets</h4>
    <ul>
        {%- for dataset in dataset.datasets -%}
        <li>
            <a href="{{ dataset.url }}">{{ dataset.name }}</a>
        </li>
        {%- endfor -%}
    </ul>
    {%- endif -%}
    <p>
        <a href="{{ dataset.code }}">
            <svg class="svg-icon" width="100%"><use xlink:href="/assets/minima-social-icons.svg#code"></use></svg>
            Analysis Code
        </a>
    </p>
    {%- if dataset.papers -%}
    <h4>Publications</h4>
    <ul>
        {%- for paper in dataset.papers -%}
        <li>
            <a href="{{ paper.url }}">{{ paper.name }}</a>
        </li>
        {%- endfor -%}
    </ul>
    {%- endif -%}
</div>
{% endfor %}
