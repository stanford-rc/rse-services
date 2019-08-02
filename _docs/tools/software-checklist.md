---
title: Software Checklist
tags: 
 - badge
 - software
---

# Software Checklist

The following checklist is to ensure reproducible software. Check the points that apply
for your repository to generate your badge.

<div id="app">

<button class="btn btn-success" style="max-width:300px">Score: 
    <input class="form-control"
       placeholder="0"  style="background-color:transparent; width:50px; margin-left:5px; color:white; font-size:20px"
       type="text" v-model="score"><span>%</span></button>

<span style='float:right'>
<svg class="svg" xmlns="http://www.w3.org/2000/svg" width="200" height="35" viewBox="0 0 200.58699 34.999">
  <path d="M 0,0 H 146.01893 V 35 H 0 Z" fill="#333" style="color:#000" stroke-width="1.46415269" />
  <text font-size="13"
     y="22"
     x="65.093933"
     font-size="13"
     font-family="ITCGothicBold.ttf"
     text-anchor="middle"
     fill="#ffffff">software checklist</text>
  <path id="svg-color" d="m 146.01893,0 h 55.57 v 35 h -55.57 z" fill="#ccc" />
  <text id="svg-score"
     font-size="13"
     y="22"
     x="173.22897"
     font-family="ITCGothicBold.ttf"
     text-anchor="middle"
     fill="#ffffff">0</text></svg>
</span>

{% for section in site.data.software-checklist %}<h2 id="{{ section.title | slufify }}">{{ section.title }}</h2>
<ul class="task-list">{% for item in section.items %}
  <li class="task-list-item" {% if item.comment %}title="{{ item.comment }}"{% endif %}><input id="{{ item.id }}" type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>{{ item.title }}:</strong> {{ item.description }} {% if item.url %}<a href="{{ item.url }}" target="_blank">[ref]</a>{% endif %}</li>{% endfor %}
</ul>{% endfor %}
</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
new Vue({
  el: '#app',
  data: {
    // Current user score
    score: 0,
    points: 0,

    // Must be same length as number of points
    colors: ["#B43C3C","#BB473E","#BF5340","#BF6240","#BF6F40","#BF7540",
             "#BF7D40","#BF8440","#BF8E40","#BF9740","#BF9F40","#BFAA40",
             "#BFB540","#BFBB40","#AEBF40","#9FBF40","#80BF40","#59BF40"]
  },
  // The view will trigger these methods on click

  methods: {

    countPoints: function() {
      this.points = document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]:checked').length;
      this.score = (100 * (this.points / document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]').length)).toFixed(2);
      $('#svg-score').text(Math.round(this.score) + "%")
      $('#svg-color').attr("fill", this.colors[this.points - 1])
    }
  }
});
</script>
