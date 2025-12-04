<div class="col">
  <a href="{% if other.redirect %}{{ other.redirect }}{% else %}{{ other.url | relative_url }}{% endif %}">
    <div class="card h-100 hoverable">
      {% if other.img %}
        {%
          include figure.liquid
          loading="eager"
          path=other.img
          sizes = "250px"
          alt="other thumbnail"
          class="card-img-top"
        %}
      {% endif %}
      <div class="card-body">
        <h2 class="card-title">{{ other.title }}</h2>
        <p class="card-text">{{ other.description }}</p>
        <div class="row ml-1 mr-1 p-0">
          {% if other.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ other.github }}"><i class="fa-brands fa-github gh-icon"></i></a>
              </div>
              {% if other.github_stars %}
                <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                  <i class="fa-solid fa-star"></i>
                  <span id="{{ other.github_stars }}-stars"></span>
                </span>
              {% endif %}
            </div>
          {% endif %}
        </div>
      </div>
    </div>
  </a>
</div>
