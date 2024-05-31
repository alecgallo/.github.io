---
layout: page
title: "Outside the lab"
---


{% if site.show_excerpts %}
  {% include home.html title="Past Projects" %}
{% else %}
  {% include archive.html title="Past Projects" %}
{% endif %}


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Outside the lab</title>
  <style>
    /* Curtain window styles */
    .curtain {
      display: none; /* Hidden by default */
      position: fixed;
      z-index: 1;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0, 0, 0, 0.8); /* Black background with opacity */
      animation-name: slideDown;
      animation-duration: 0.5s;
    }

    .curtain-content {
      background-color: #fefefe;
      margin: 15% auto;
      padding: 20px;
      border: 1px solid #888;
      width: 80%;
    }

    /* Close button styles */
    .close-button {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
    }

    .close-button:hover,
    .close-button:focus {
      color: black;
      text-decoration: none;
      cursor: pointer;
    }

    /* Slide down animation */
    @keyframes slideDown {
      from { top: -100%; opacity: 0; }
      to { top: 0; opacity: 1; }
    }
  </style>
</head>
<body>
  <!-- Add this link or button somewhere in your page layout -->
  <a id="outsideLabLink" href="#">Outside the lab</a>

  <!-- Curtain window structure -->
  <div id="curtainWindow" class="curtain">
    <div class="curtain-content">
      <span class="close-button">&times;</span>
      <h2>Past Projects</h2>
      <!-- Include the content you want to show inside the curtain window -->
      {% if site.show_excerpts %}
        {% include home.html title="Past Projects" %}
      {% else %}
        {% include archive.html title="Past Projects" %}
      {% endif %}
    </div>
  </div>

  <script>
    document.addEventListener("DOMContentLoaded", function() {
      var link = document.getElementById("outsideLabLink");
      var curtain = document.getElementById("curtainWindow");
      var closeButton = document.querySelector(".close-button");

      // Show the curtain window when the link is clicked
      link.addEventListener("click", function(event) {
        event.preventDefault();
        curtain.style.display = "block";
      });

      // Hide the curtain window when the close button is clicked
      closeButton.addEventListener("click", function() {
        curtain.style.display = "none";
      });

      // Hide the curtain window when clicking outside the content
      window.addEventListener("click", function(event) {
        if (event.target == curtain) {
          curtain.style.display = "none";
        }
      });
    });
  </script>
</body>
</html>
