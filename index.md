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
                <div class="col-md-4 col-sm-12">
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

<section id="team" class="container text-center">
    <h1 class="display-3 p-5 text-primary">Our Team</h1>
    {% include map.html %}
    <br/>
    <div class="row justify-content-center align-items-center">
      <a href="{{ "team.html" | relative_url }}" style="font-size: 32px;" class="col-md-6 btn btn-lg btn-success btn-block shadow nounderline">
          Meet the team
      </a>
    </div>
</section>

<section id="read" class="container">
  <h1 class="display-3 p-5 text-primary text-center">Read Up</h1>
  <!-- <div style="margin: 10px" class="text-center mt-4"> -->
    <div class="row">
      {% for cat in site.categories %}
        <div class="col-md-4 col-sm-12 text-center align-items-stretch pb-5">
          <h1 style="font-size: 37px" class="display-6 p-4 mb-5">{{ cat[0] }}</h1>
          {% for post in cat[1] limit: 3 %}
            <a href=" {{ post.url | relative_url }}" class="btn btn-lg btn-primary btn-block shadow nounderline">
                {{ post.title }}
            </a>
            <br/>
          {% endfor %}
        </div>
      {% endfor %}
    </div>
    <div class="row justify-content-center align-items-center">
      <a href="{{ "posts.html" | relative_url }}" style="font-size: 32px;" class="col-md-4 btn btn-lg btn-success btn-block shadow nounderline">
          See more articles
      </a>
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

