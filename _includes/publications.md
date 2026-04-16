<h2 id="publications" style="margin: 2px 0px -15px;">Experiences</h2>

<div class="publications">
  <div class="experience-timeline">
    {% for link in site.data.publications.main %}
    {% assign year_text = link.year_range | default: link.conference_short %}
    {% assign logo_path = link.logo | default: link.image %}
    {% assign role_text = link.role | default: link.title %}
    {% assign org_text = link.organization | default: link.authors %}
    {% assign highlights_text = link.highlights | default: link.conference %}

    <div class="timeline-item">
      <div class="timeline-year">{{ year_text }}</div>
      <div class="timeline-center">
        <span class="timeline-dot"></span>
      </div>
      <div class="timeline-content">
        {% if logo_path %}
        <img src="{{ logo_path }}" class="timeline-logo" alt="{{ org_text }}">
        {% endif %}
        <div class="timeline-details">
          {% if role_text %}
          <div class="timeline-role">{{ role_text }}</div>
          {% endif %}
          {% if org_text %}
          <div class="timeline-org">{{ org_text }}</div>
          {% endif %}
          {% if highlights_text %}
          <div class="timeline-highlights">{{ highlights_text }}</div>
          {% endif %}
        </div>
      </div>
    </div>
    {% endfor %}
  </div>
</div>
