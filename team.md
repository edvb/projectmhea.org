---
title: Our Team
layout: default
---

<header class="masthead bg-primary text-white" style="padding-top: 140px; height: 450px">
  <div class="container">
    <h1 class="display-1 text-white">{{ page.title }}</h1>
  </div>
</header>

<section id="team" class="container text-center">
  {% include map.html %}
  <div class="row">
    {% for item in site.data.people.people %}
      {% if item.title %}
        </div>
        <h1 class="display-4 p-5 mb-5">{{ item.title }}</h1>
        <div class="row">
      {% else %}
        <div class="col-md-{{ item.size | default: 3 }} col-sm-12 d-flex align-items-stretch pb-5">
            <div class="card mb-5">
            <img src="assets/img/people/{{ item.image }}">
            <div class="card-body mt-5">
                <h3 class="card-title">{{ item.name }}</h3>
                <h5 class="card-subtitle mb-2">{{ item.position }}</h5>
                <p class="card-text">{{ item.desc }}</p>
            </div>
            </div>
        </div>
      {% endif %}
    {% endfor %}
  </div>
</section>
