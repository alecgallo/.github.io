---
layout: default
title: "Outside the lab"
permalink: /outside_the_lab/
---

<!DOCTYPE html>
<html lang="{{ page.lang | default: site.lang | default: "en" }}">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ page.title | default: site.title | default: "Website" }}</title>
    <style>
        /* Basic styles for the page and navigation */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        .navigation {
            display: flex;
            justify-content: flex-end;
            background-color: #333;
            padding: 10px;
        }
        .navigation a {
            color: white;
            text-decoration: none;
            padding: 10px;
            font-size: 16px;
        }
        .navigation a:hover {
            background-color: #575757;
        }
        /* Styles for the curtain window */
        .curtain {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            z-index: 1000;
        }
        .curtain-content {
            text-align: center;
        }
        .curtain-content a {
            color: white;
            text-decoration: none;
            font-size: 24px;
            margin: 10px 0;
            display: block;
        }
    </style>
</head>
<body>
    <nav class="navigation">
        {% for item in site.navigation %}
            <a href="{{ item.url }}">{{ item.title }}</a>
        {% endfor %}
        <a href="javascript:void(0)" id="outside-the-lab-button">Outside the lab</a>
    </nav>

    <div class="curtain" id="curtain">
        <div class="curtain-content">
            <a href="#">2024</a>
            <a href="#">2023</a>
            <a href="#">2022</a>
            <!-- Add more years as needed -->
        </div>
    </div>

    <script>
        document.getElementById('outside-the-lab-button').addEventListener('click', function() {
            var curtain = document.getElementById('curtain');
            if (curtain.style.display === 'flex') {
                curtain.style.display = 'none';
            } else {
                curtain.style.display = 'flex';
            }
        });
    </script>
</body>
</html>
