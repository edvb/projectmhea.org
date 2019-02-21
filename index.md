---
layout: default
---

<header class="masthead bg-primary text-white text-center">
    <div class="container">
        <img class="img-fluid mb-5 pt-5 pb-5 d-block mx-auto" src="assets/img/logo.png" width="50%">
    </div>
</header>

<section id="intro" class="container" style="margin-top: -300px">
    <div class="row">
    {% for card in site.data.cards.intro %}
        <div class="col-md col-sm-12">
            <div class="card bg-light">
                <div class="card-body text-center">
                    <h3 class="card-title text-primary"><i class="fas fa-{{ card.symbol }}"></i></h3>
                    <h4 class="card-title text-primary"><b>{{ card.title }}</b></h4>
                    <p class="card-text"><b>{{ card.desc }}</b></p>
                    {% if card.button %}
                        <p class="card-text">
                            <a href="{{ card.button.link }}" class="btn btn-primary">{{ card.button.name }}</a>
                        </p>
                    {% endif %}
                </div>
            </div>
        </div>
    {% endfor %}
    </div>
</section>

<section id="motivation">
    <div class="container">
        <h1 class="display-3 pb-5 text-primary text-center">Our Motivation</h1>
        <div class="row">
            {% for person in site.data.people.quotes %}
                <div class="col">
                    <div class="box-testimony">
                        <blockquote>
                            <p>{{ person.quote }}</p>
                        </blockquote>
                        <div class="author">
                        <figure><img src="assets/img/people/{{ person.image }}" alt="Person"></figure>
                        <p>{{ person.name }}<span class="subtext">{{ person.position }}</span></p>
                        </div>
                    </div>
                </div>
            {% endfor %}
        </div>
    </div>
</section>

<section id="solution">
    <div class="container">
    <h1 class="display-3 p-5 text-white text-center">Our Solution</h1>
    <div class="row">
        {% for card in site.data.cards.solution %}
        <div class="col-md-6 col-sm-12">
        <div class="card text-white mb-3" style="background-color: transparent; border: none">
            <div class="card-body">
            <h1 class="card-title" style="font-size: 80px"><i class="fas fa-{{ card.symbol }}"></i></h1>
            <h4 class="card-title"><b>{{ card.title }}</b></h4>
            <p class="card-text">{{ card.desc }}</p>
            </div>
        </div>
        </div>
        <br>
        {% endfor %}
    </div>
    </div>
</section>

<section id="read" class="container">
    <h1 class="display-3 p-5 text-primary text-center">Read Up</h1>
    <!-- <div style="margin: 10px" class="text-center mt-4"> -->
    <div class="row">
    <div class="col-md-6 col-sm-12 text-center align-items-stretch pb-5">
        <h1 class="display-6 p-4 mb-5">Learn More</h1>
        {% for post in site.posts %}
        {% if post.category == "learn more" %}
            <a href="{{ post.url }}">
                <button type="button" class="btn btn-lg btn-primary btn-block shadow">
                    {{ post.title }}
                </button>
            </a>
            <br/>
        {% endif %}
        {% endfor %}
    </div>
    <div class="col-md-6 col-sm-12 text-center align-items-stretch pb-5">
        <h1 class="display-6 p-4 mb-5">Personal Stories</h1>
        {% for post in site.posts %}
        {% if post.category == "your story" %}
            <a href="{{ post.url }}">
                <button type="button" class="btn btn-lg btn-primary btn-block shadow">
                    {{ post.title }}
                </button>
            </a>
            <br/>
        {% endif %}
        {% endfor %}
    </div>
    </div>
</section>

<section id="team" class="container text-center">
    <h1 class="display-3 p-5 text-primary">Our Team</h1>
        <div id="world-map" style="width: 1170; height: 560px"></div>
        <script>
            console.log("sup mate");
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

<section id="contact" class="text-center">
    <div class="container">
    <h1 class="display-3 p-5 text-white">Contact</h1>
    <div class="row-md-4">
        <form method="POST" action="https://formspree.io/contact@projectmhea.org">
        <div class="row">
            <div class="col m-2">
            <input type="text" name="name" class="form-control" placeholder="Name">
            </div>
            <div class="col m-2">
            <input type="email" name="email" class="form-control" placeholder="Email">
            </div>
        </div>
        <div class="row">
            <div class="col m-2">
            <input type="text" name="school" class="form-control" placeholder="School"/>
            </div>
            <div class="col m-2">
            <input type="text" name="city" class="form-control" placeholder="City"/>
            </div>
        </div>
        <textarea type="text" name="message" class="form-control m-2" rows="7" placeholder="Message"></textarea>
        <div style="margin: 10px" class="text-center mt-4">
            <button class="btn btn-primary" type="submit">Send<i class="fas fa-paper-plane ml-2"></i></button>
        </div>
        </form>
    </div>
    </div>
</section>

