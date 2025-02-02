---
permalink: /
title: "Namaste 🙏"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a PhD student in Computer Science at the University of Maryland, College Park, advised by [Prof. Tom Goldstein](https://scholar.google.com/citations?hl=en&user=KmSuVtgAAAAJ&view_op=list_works&sortby=pubdate).

Previously, I was a research intern in the BrAIN group at the Max Planck Institute for Software Systems (MPI-SWS), working with [Prof. Mariya Toneva](https://mtoneva.com/). Prior to that, I was a research project assistant at the Indian Institute of Science with [Prof. Anirban Chakraborty](https://anirbanchakraborty.github.io/), developing methods to train adversarially robust neural networks under low-resource constraints.

## Recent News

{% assign sorted_news = site.news | sort: 'date' | reverse %}
{% for item in sorted_news limit:5 %}
<div class="news-item">
  <div class="news-date">{{ item.date | date: "%b %d, %Y" }}</div>
  <div class="news-content">{{ item.news }}</div>
</div>
{% endfor %}


## Recent Publications

{% assign sorted_pubs = site.publications | sort: 'date' | reverse %}
{% for post in sorted_pubs limit:3 %}
<div class="pub-item">
  <div class="pub-venue-short">{{ post.venue | split: "(" | last | remove: ")" }}</div>
  <div class="pub-content">
    <a href="{{ post.paperurl }}">{{ post.title }}</a>
    <div class="pub-venue">{{ post.venue }}{% if post.date %}, {{ post.date | date: "%Y" }}{% endif %}</div>
  </div>
</div>
{% endfor %}


<style>
.news-item {
  display: grid;
  grid-template-columns: 120px 1fr;
  gap: 1em;
  margin-bottom: 1.5em;
}

.news-date {
  color: #666;
}

.news-content a {
  color: rgb(3, 102, 214);
  text-decoration: none;
}

.news-content a:hover {
  text-decoration: underline;
}

.pub-item {
  display: grid;
  grid-template-columns: 120px 1fr;
  gap: 1em;
  margin-bottom: 1.5em;
}

.pub-venue-short {
  color: #333;
  font-size: 0.95em;
}

.pub-content a {
  color: rgb(3, 102, 214);
  text-decoration: none;
  display: block;
  margin-bottom: 0.3em;
}

.pub-content a:hover {
  text-decoration: underline;
}

.pub-venue {
  color: #666;
  font-size: 0.9em;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  document.querySelectorAll('.news-content').forEach(function(element) {
    element.innerHTML = element.innerHTML.replace(
      /\[(.*?)\]\((.*?)\)/g, 
      '<a href="$2">$1</a>'
    );
  });
});
</script>