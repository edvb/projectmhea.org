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
        <div id="world-map" style="width: 1170; height: 560px"></div>
        <script>
          $(function(){
            $('#world-map').vectorMap({
              map: 'world_mill_en',
              backgroundColor: '#FFFFFF',
              zoomOnScroll: false,
              regionStyle: {
                initial: {
                  fill: '#50CDB1',
                  "fill-opacity": 1,
                  stroke: 'none',
                  "stroke-width": 0,
                  "stroke-opacity": 1
                },
                hover: {
                  "fill-opacity": 0.8,
                  cursor: 'pointer'
                },
                selected: {
                  fill: 'yellow'
                },
                selectedHover: {
                }
              },
              markers: [
                {latLng: [47.38, -122.19], name: 'Seattle'},
                {latLng: [25.21, 55.23], name: 'Sharjah'},
                {latLng: [28.36, 77.13], name: 'Delhi'},
                {latLng: [12.74, 77.83], name: 'Hosur'},
                {latLng: [13.5, 80.16], name: 'Chennai'},
                {latLng: [22.47, 86.12], name: 'Jamshedpur'},
                {latLng: [34.5, 74.47], name: 'Srinagar'},
                {latLng: [26.7588, 83.3697], name: 'Ghorakhpur'},
                {latLng: [26.51, 80.57], name: 'Lucknow'},
              ],
              markerStyle: {
                initial: {
                  fill: '#7d63aa',
                  stroke: '#7d63aa',
                  "fill-opacity": 1,
                  "stroke-width": 1,
                  "stroke-opacity": 1,
                  r: 5
                },
                hover: {
                  stroke: 'black',
                  "stroke-width": 2,
                  cursor: 'pointer'
                },
                selected: {
                  fill: 'blue'
                },
                selectedHover: {
                }
              }
            });
          });
        </script>
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