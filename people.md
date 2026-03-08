---
title: People
permalink: /people/
---

### Lab Members

Our research group is full of great people.

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|postdoc|postgrad|visitor|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif role == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif role == 'postgrad' %}
<h3>Postgraduate Students</h3>
 {% elsif role == 'visitor' %}
<h3>Visitors</h3>
 {% elsif role == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

{% if role == 'alumni' %}
{% assign display_people = site.people | where: 'position', 'alumni' | sort: 'completed' | reverse %}
{% else %}
{% assign display_people = people_sorted %}
{% endif %}

<div class="content list people">
  {% for profile in display_people %}
    {% if profile.position contains role %}
      <div class="list-item-people{% if role == 'alumni' %} list-item-alumni{% endif %}">

        {% if role == 'alumni' %}
          {% if profile.avatar %}
            <div class="alumni-photo">
              <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail profile-thumbnail-alumni" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            </div>
          {% endif %}
          <div class="alumni-info">
            <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
            {% if profile.project %}<span class="project-title">{{ profile.project }}</span>{% endif %}
            {% if profile.completed %}<span class="alumni-completed">Completed: {{ profile.completed }}</span>{% endif %}
            {% if profile.now %}<span class="alumni-now">Now: {{ profile.now }}</span>{% endif %}
          </div>

        {% else %}
          <p class="list-post-title">
            {% if profile.avatar %}
              <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            {% else %}
              <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/default_avatar.svg"></a>
            {% endif %}
            <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
            {% if profile.joined %}<br><small>Joined: {{ profile.joined }}</small>{% endif %}
            {% if profile.project %}<br><small class="project-title">{{ profile.project }}</small>{% endif %}
            {% if profile.now %}<br><small>Now: {{ profile.now }}</small>{% endif %}
          </p>
        {% endif %}

      </div>
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}
