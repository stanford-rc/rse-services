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

<h2 id="repository-checks">Repository Checks</h2>

<ul class="task-list">
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Repository:</strong> The source code is available at a public url.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Version:</strong> The software has a method to support versioning.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Contributing:</strong> A statement is included about how to contribute to the software.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Issues:</strong> An issues board is available for a user to ask a question, or request support.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Maintainer:</strong> At least one primary maintainer is indentified.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>License:</strong> An appropriate plain-text LICENSE file is included, ideally <a href="https://opensource.org/licenses/alphabetical">OSI approved</a></li>
</ul>

<h2 id="documentation">Documentation</h2>

<ul class="task-list">
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Installation:</strong> The repository includes instructions for installation in the README, including dependencies and operating system requirements.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Purpose:</strong> A clear purpose or statement of need is defined. A reader knows what the software does.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Getting Started:</strong> After installation, there is a clear “Getting Started” tutorial or similar.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Examples:</strong> Are included (via scripts or docu</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Docstrings:</strong> If appropriate for the language, docstrings are rendered into code documents.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Functionality:</strong> All functions, client interactions, and if appropriate, API endpoints, are documented.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Living Documentation:</strong> A user can easily jump from any documentation page to ask for help, or contribute changes [<a href="https://vsoch.github.io/2018/interactive-posts/">1</a>].</li>
</ul>

<h2 id="artifacts">Artifacts</h2>

<ul class="task-list">
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Containers</strong> The repository provides one or more container recipes (Dockerfile, Singularity) or a pre-built container.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Publications:</strong> Any relevant citations for papers or external resources are linked in the README.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Data:</strong> Any required data or similar artifacts are linked.</li>
</ul>

<h2 id="continuous-integration">Continuous Integration</h2>

<ul class="task-list">
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>Automated Testing:</strong> is done with any request for change to the main (typically master) branch.</li>
  <li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)" /><strong>Operating Systems:</strong> testing is done across operating systems and environments that cover 80% of use cases.</li>
</ul>
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
    // Count points as they change
    countPoints: function() {
      this.points = document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]:checked').length;
      this.score = (100 * (this.points / document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]').length)).toFixed(2);
      $('#svg-score').text(Math.round(this.score) + "%")
      $('#svg-color').attr("fill", this.colors[this.points - 1])
    }
  }
});
</script>
