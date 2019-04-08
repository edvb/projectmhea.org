---
title: Read Up
layout: default
---

<header class="masthead bg-primary text-white" style="padding-top: 140px; height: 450px">
  <div class="container">
    <h1 class="display-1 text-white">{{ page.title }}</h1>
  </div>
</header>

<section id="intro" style="margin-top: -120px">
  <div class="container">
    {% for cat in site.categories %}
      <div class="row justify-content-center align-items-center">
        <div class="text-center col-md-8 col-sm-12 align-items-center pb-5">
          <h1 class="display-6 p-4 mb-5">{{ cat[0] }}</h1>
          {% for post in cat[1] %}
              <a href=" {{ post.url | relative_url }}" class="nounderline">
                <button type="button" class="btn btn-lg btn-primary btn-block shadow">
                  {{ post.title }}
                </button>
              </a>
              <br/>
          {% endfor %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

