---
layout: full
title: Résumé
permalink: /resume/
---

<div class="row mt-1 equal">
    <div class="col-xs-8">
        <h1>{{site.data.resume.basics.name}}</h1>
        <h3>{{site.data.resume.basics.label}}</h3>
        <ul class="list-unstyled mt-1">
            <li><a href="mail:{{site.data.resume.basics.email}}" class="hide-print-url"><i class="fas fa-envelope mr-1"></i>{{site.data.resume.basics.email}}</a></li>
            {% if site.data.resume.basics.phone %}<li><a href="tel:{{site.data.resume.basics.phone}}" class="hide-print-url"><i class="fas fa-phone mr-1"></i>{{site.data.resume.basics.phone}}</a></li>{% endif %}
            <li><a href="{{site.data.resume.basics.website}}" class="hide-print-url"><i class="fas fa-globe-americas mr-1"></i>{{site.data.resume.basics.website}}</a></li>
        </ul>
    </div>
    <div class="col-xs-4 profile-photo-wrapper">
        <img src="{{site.data.resume.basics.picture}}" alt="profile picture" class="profile-phot img-responsiveo"/>
    </div>
</div>
<hr>
<div class="row">
    {% for profile in site.data.resume.basics.profiles %}
    <div class="col-xs-{{12  | divided_by:site.data.resume.basics.profiles.size | round }}">
        <div>{{profile.network}}</div>
        <div><a href="{{profile.url}}" class="hide-print-url" target="_blank">{{profile.username}}</a></div>
    </div>
    {% endfor %}
</div>
<hr>
<div class="row">
    <div class="col-sm-12">{{site.data.resume.basics.summary}}</div>
</div>
<hr>
## Experience
{% for job in site.data.resume.work %}
<div class="row">
    <div class="col-lg-11 col-lg-offset-1">
        <div class="row">
            <div class="col-sm-9">
                <h3 class="d-inline-block">{{job.position}}</h3>&nbsp;@&nbsp;<a href="{{job.website}}" class="hide-print-url" target="_blank"><h3 class="d-inline-block">{{job.company}}</h3></a>
            </div>
            <div class="col-sm-3 text-right text-muted">
                <span class="mt-1 d-block">{{job.startDate | date: "%b %Y"}} - {{job.endDate | date: "%b %Y"}}</span>
            </div>
        </div>
    </div>
    <div class="col-lg-11 col-lg-offset-1 mb-1">
        <p>{{ job.summary }}</p>
        <div class="tags">
            {% for tag in job.highlights %}
            <span class="badge">{{tag}}</span>
            {% endfor %}
        </div>
    </div>
</div>
{% endfor %}
<hr>
## Education
{% for qualification in site.data.resume.education %}
<div class="row">
    <div class="col-lg-11 col-lg-offset-1">
        <div class="row">
            <div class="col-sm-9">
                <h3 class="d-inline-block">{{qualification.institution}}</h3>
            </div>
            <div class="col-sm-3 text-right text-muted">
                <span class="mt-1 d-block">{{qualification.startDate | date: "%b %Y"}} - {{qualification.endDate | date: "%b %Y"}}</span>
            </div>
        </div>
    </div>
    <div class="col-lg-11 col-lg-offset-1 mb-1">
        <p><strong>{{qualification.studyType}}&nbsp;{{qualification.area}}</strong>&nbsp;{{ qualification.gpa }}</p>
    </div>
</div>
{% endfor %}
<hr>
## Skills
<div class="row">
    <div class="col-lg-11 col-lg-offset-1">
        <div class="row">
        {% for skill in site.data.resume.skills %}
            <div class="col-md-6 mb-1">
                <div class="row">
                    <div class="col-sm-9">
                        <h3 class="d-inline-block">{{skill.name}}</h3>
                    </div>
                    {% if skill.level %}<div class="col-sm-3 text-right text-muted hidden-print">
                        <span class="mt-1 d-block">{{skill.level}}</span>
                    </div>{% endif %}
                </div>
                <div class="row">
                    <div class="col-sm-12">
                        <div class="tags">
                            {% for tag in skill.keywords %}
                            <span class="badge">{{tag}}</span>
                            {% endfor %}
                        </div>
                    </div>
                </div>
            </div>
        {% endfor %}
        </div>
    </div>
</div>
<hr class="hidden-print">
<h2 class="hidden-print">Download a Copy!</h2>
<div class="row hidden-print">
    <div class="col-lg-12 mt-1">
        <a href="/resume.json" target="_blank" class="btn btn-lg btn-success">JSON Resume</a>
        <a href="#" onclick="window.print();" class="btn btn-lg btn-success">Print Page</a>
    </div>
    <div class="col-lg-12 mt-1">
        <p class="text-muted">* If you prefer a different format, please reach out to me, I am happy to assist!</p>
    </div>
</div>