---
layout: page
permalink: /publications/
title: Publications
description: Biomedical Informatics, Artificial Intelligence, Multimodal Learning, Medical Signal Processing, Medical AI, Wearable Ultrasound
nav: true
nav_order: 4
---

{% include bib_search.liquid %}

<style>
.under-review ol {
  list-style-type: disc !important;
  padding-left: 2em !important;
}
.under-review ol li {
  display: list-item !important;
  padding-left: 0 !important;
  margin-bottom: 1.5em;
}
.under-review .col-sm-2 {
  display: none !important;
}
.under-review .col-sm-8 {
  flex: 0 0 100% !important;
  max-width: 100% !important;
}
</style>

<div class="publications">

<h2 class="bibliography">Publications</h2>

{% bibliography --query @*[category=Publications] %}

<h2 class="bibliography">Manuscripts Under Review</h2>

</div>

<div class="under-review publications">
{% bibliography --query @*[category=Under Review] %}
</div>