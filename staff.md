---
title: Staff
---
<div class="columns is-multiline">
{% for s in site.data.staff %}
<div class="column is-one-fifth">
    <div class="card" style="height: 100%;">
        <header class="card-header">
            <p class="card-header-title">
            {{ s['Tag'] }}
            </p>
        </header>
        <div class="card-image">
            <figure class="image is-square" style="margin: 0px !important">
                {% if s['Pic'] %}
                <img src="{{ s['Pic'] }}">
                {% else %}
                {% assign min = 1 %}
                {% assign max = 85 %}
                {% assign diff = max | minus: min %}
                {% assign randomNumber = "now" | date: "%N" | modulo: diff | plus: min %}
                <img src='/img/staff/staff_{{ randomNumber }}.jpg'>
                {% endif %}
            </figure>
        </div>
        <div class="card-content p-3">
            <div class="media mb-2">
                <div class="media-content">
                    {% if s['Twitter'] %}
                    <span class="icon-text">
                        <span class="icon pt-1">
                            <i class="fab fa-twitter"></i>
                        </span>
                        <span><a href="https://twitter.com/{{ s['Twitter'] }}"><p class="title is-5 mb-2">{{ s['Twitter'] }}</p></a></span>
                    </span>
                    {% endif %}
                    {% if s['Pronouns'] %}
                    <p class="subtitle is-6 is-spaced"><i>{{ s['Pronouns'] }}</i></p>
                    {% endif %}
                </div>
            </div>
            {% if s['Staff Page Blurb'] %}
            <div class="content">
                {{ s['Staff Page Blurb'] }}
            </div>
            {% endif %}
        </div>
    </div>
</div>
{% endfor %}
</div>