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

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
	  {% else %}
  		<a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/default_avatar.svg"></a>
	{% endif %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
          {% if profile.joined %}<br><small>Joined: {{ profile.joined }}</small>{% endif %}
          {% if profile.project %}<br><small>Project: {{ profile.project }}</small>{% endif %}
	  {% if profile.completed %}<br><small>Completed: {{ profile.completed }}</small>{% endif %}
          {% if profile.now %}<br><small>Now: {{ profile.now }}</small>{% endif %}
        </p>
      </div>
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}


