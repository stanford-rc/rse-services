---
title: Services Explorer
disable_editable: true
disable_search: true
tags: 
 - portal
---

<style>
#add-button {
  border-radius: 30px;
  height: 20px;
  padding-top: 0px;
  background-color: darkred;
  color: white;
}

.group-wrap {
  font-size: 0;
  width: 100%;
  min-width: 750px;
}
.group-wrap > div {
  display: inline-block;
  width: 50%;
  vertical-align: top;
}
.group-wrap > div h3 {
  font-size: 28px;
  text-align: center;
  margin: 0;
  margin-bottom: 6px;
}

.group {
  list-style: none;
  margin: 0;
  padding: 0;
  font-size: 20px;
  background-color: #5bbce4;
  border: 3px solid white;
  vertical-align: top;
  min-height: 79px;
  transition: all 200ms ease-in-out;
  padding: 8px;
}
.group.adding {
  background-color: #239ed0;
  border-style: dashed;
}
.group#group2 .remove, .group#group3 .remove {
  display: none;
}
.group__item {
  padding: 16px;
  border: 1px solid white;
  background-color: #285364;
  color: white;
  letter-spacing: 2px;
}
.group__item:not(:last-child) {
  margin-bottom: 6px;
}

.sortable-ghost {
  opacity: 0.6;
  background-color: transparent;
  border: 1px dashed white;
}

.sortable-drag {
  opacity: 1;
  border: 1px solid white;
  box-shadow: 0 0 10px black;
}

.group__item {
  cursor: move;
  /* fallback if grab cursor is unsupported */
  cursor: -moz-grab;
  cursor: -webkit-grab;
  cursor: grab;
  position: relative;
}
.group__item:active {
  cursor: -moz-grabbing;
  cursor: -webkit-grabbing;
  cursor: grabbing;
}
.group__item .remove:hover:before {
  transform: scale(0.9);
  background-color: red;
}

.group__item .remove:before {
  font-family: Helvetica, Arial, sans-serif;
  content: 'x';
  position: absolute;
  right: 6px;
  top: 6px;
  line-height: 21px;
  text-align: center;
  cursor: pointer;
  border: 1px solid white;
  width: 24px;
  height: 24px;
  padding-left: 1px;
  transition: all 150ms ease-in-out;
  font-size: 14px;
}

.finished-block {
  width: 100%;
  margin-top: 16px;
}
.finished-block h3 {
  margin: 0;
  margin-bottom: 6px;
}

#textPrompt {
  margin: 0;
  padding: 12px;
  list-style: none;
  border: 1px dashed #a6a6a6;
  width: calc(100% - 6px);
  text-align: center;
  margin-bottom: 8px;
}
#textPrompt li {
  display: inline-block;
  padding: 8px;
  background-color: #285364;
  margin: 8px;
  color: #ffffff;
}

form {
  margin-bottom: 16px;
  border: 1px solid #e6e6e6;
  padding: 32px;
}

input {
  display: inline-block;
  margin-left: 8px;
  padding: 8px;
  height: 30px;
  border: 0;
  border-bottom: 1px solid #a6a6a6;
  transition: all 150ms ease-in-out;
  width: 170px;
}
input:focus {
  outline: 0;
  border-bottom: 1px solid #595959;
}

.animated > li {
  -webkit-animation-duration: 500ms;
  animation-duration: 500ms;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
}

@-webkit-keyframes fadeInUp {
  from {
    opacity: 0;
    -webkit-transform: translate3d(0, 100%, 0);
    transform: translate3d(0, 100%, 0);
  }
  to {
    opacity: 1;
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
  }
}
@keyframes fadeInUp {
  from {
    opacity: 0;
    -webkit-transform: translate3d(0, 100%, 0);
    transform: translate3d(0, 100%, 0);
  }
  to {
    opacity: 1;
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
  }
}
.fadeInUp > li {
  -webkit-animation-name: fadeInUp;
  animation-name: fadeInUp;
}</style>

# Services Explorer

<label for="addItem">Add an Item:
<input class="add-item" id="addItem" maxlength="16" required="required" type="text" /></label>
<button class="btn btn-secondary" id="add-button">+</button>
<div class="group-wrap">
  <div class="services-wrap">
    <h3>
      Services
    </h3>
    <ul class="group" id="services">{% for category in site.data.services.categories %}{% for item in category.items %}
      <li class="group__item" style="background-color: {{ category.color }}" data-id="{{ item.title | slugify }}">
       <span class="badge badge-primary">{{ category.title }}</span><br>{{ item.title }}<span class="remove"></span>
      </li>{% endfor %}{% endfor %}
    </ul>
  </div>
  <div class="group3-wrap">
    <h3>
      Selected
    </h3>
    <ul class="group" id="group3">
    </ul>
  </div>
</div>
<div class="finished-block">
  <h3>
    Selection
  </h3>
  <ul id="textPrompt"></ul>
</div>
<ul id="workingList"></ul>

<form action="https://formspree.io/vsochat@stanford.edu" method="POST">
  <label for="name">Your Name:
  <input type="text" name="name"><br>
  <label for="email">Your Email:
  <input type="email" name="_replyto"><br>
  <label for="message">Message:
  <input type="textarea" name="message"><br>
  <input id="interest-list" type="hidden" name="request"><br>
  <button class="btn btn-success" type="submit" style="cursor:pointer" value="Send">Send</button>

<script src="https://cdn.jsdelivr.net/npm/sortablejs@latest/Sortable.min.js"></script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js'></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
  printList("group3", "textPrompt", sortable3);
});

var services = document.getElementById("services");
var group3 = document.getElementById("group3");
var sortableSpeed = 150;

var sortable1 = Sortable.create(services, {
  group: {
    name: "services",
    put: "group3"
  },
  animation: sortableSpeed,
  
  onMove: function(evt) {
    var dropGroup = evt.to;
    group3.classList.add("adding");
  },
  onSort: function(evt) {
    console.log("services on sort");
    evt.from.classList.remove("adding");
  },
  onEnd: function(evt) {
    group3.classList.remove("adding");
  },
  filter: ".remove",
     onFilter: function (evt) {
	var item = evt.item,
	    ctrl = evt.target;
	    if (Sortable.utils.is(ctrl, ".remove")) {  // Click on remove button
      $(item).slideUp(400, removeItem);
      function removeItem() {
       $(item).remove();
      }
    }
  }
});

var sortable3 = Sortable.create(group3, {
  group: {
    name: "group3",
    put: "services"
  },
  animation: sortableSpeed,
  onMove: function(evt) {
    var dropGroup = evt.to;
    dropGroup.classList.add("adding");
    evt.from.classList.remove("adding");
  },
  onSort: function(evt) {
    printList("group3","textPrompt", sortable3);
    evt.from.classList.remove("adding");
  },
  onEnd: function(evt) {
    document.getElementById("services").classList.remove("adding");
    printList("group3","textPrompt", sortable3);
  }
});

"use strict";

function printList(el, container, sortGroup) {
  var printBox = document.getElementById(container);
  var groupChildren = document.getElementById(el).children;
  var groupArray = Array.prototype.slice.call(groupChildren);
  
  var groupText = groupArray.map(function(el, i) {
    var numb = i + 1;
    var itemsText;
    return (itemsText =
      '<li class="list-item">' + numb + "." + el.innerText + "</li>");
  });

  var sendText = groupArray.map(function(el, i) {
    var numb = i + 1;
    var itemsText;
    return (itemsText = numb + "." + el.innerText);
  });

  var groupString = groupText.join("");
  var sendString = sendText.join("");
  
  printBox.classList.add("animated", "fadeInUp");
  sortGroup.option("disabled", true);
  setTimeout(function() {
    printBox.classList.remove("animated", "fadeInUp");
    sortGroup.option("disabled", false);
  }, 500);
  
  if (!groupString) {
    printBox.innerHTML =
      '<li class="list-item">' + "Add items to the Finished list" + "</li>";
  } else {
    printBox.innerHTML = groupString;
  }
  $("#interest-list").val(sendString);  
  var $listItems = $('#' + container + ' ' + '.list-item');
  var maxWidth = Math.max.apply(
    null,
    $listItems
      .map(function() {
        return $(this).outerWidth(true);
      })
      .get()
  );
  $listItems.css("width", maxWidth);
 
}

// found this function in codepen - sanitize the input
(function($) {
    $.sanitize = function(input) { 
      var output = input.replace(/<script[^>]*?>.*?<\/script>/gi, '').
	                 replace(/<[\/\!]*?[^<>]*?>/gi, '').
			 replace(/<style[^>]*?>.*?<\/style>/gi, '').
			 replace(/<![\s\S]*?--[ \t\n\r]*>/gi, '');
       return output;
    };

  $('#add-button').click(function(event) {
    var input = $("#addItem").val();
    if (input != "") {
       var cleanValue = $.sanitize(input);
       var groupItemHTML = '<li class="group__item">' + cleanValue + '<span class="remove"></span>' + '</li>';
       $(groupItemHTML).prependTo('#services').hide().slideDown('1000');
       $("#addItem").val('');
    }
  });
})(jQuery);
</script>
