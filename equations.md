---
title: "Equations"
---


<!-- MathJax Support -->
<style TYPE="text/css">
code.has-jax {font: inherit; font-size: 100%; background: inherit; border: inherit;}
</style>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
    tex2jax: {
        inlineMath: [['$','$'], ['\\(','\\)']],
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'] // removed 'code' entry
    }
});
MathJax.Hub.Queue(function() {
    var all = MathJax.Hub.getAllJax(), i;
    for(i = 0; i < all.length; i += 1) {
        all[i].SourceElement().parentNode.className += ' has-jax';
    }
});
</script>
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

These are some of the common computer graphics equations:

- Brasenheim
- Cohensutherland Clipping
- BRDF
- BSDF
- Camera View Matrix
- Light Field
- Phong
- Goraud
- ViewFrustum
- Spline
- Bezeir Curve
- Animation


<!-- Checkbox Tutorial: https://lokesh-coder.github.io/pretty-checkbox/ -->
<!-- Include Checkbox CSS -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/pretty-checkbox@3.0/dist/pretty-checkbox.min.css">

<fieldset data-role="controlgroup" data-type="horizontal">
<legend>Select all that you would like to display:</legend>
  <div class="pretty p-default p-thick p-pulse">
        <input type="checkbox" id="Course" class="Course" checked/>
        <div class="state">
            <label>Course Related</label>
        </div>
  </div>
  <div class="pretty p-default p-thick p-pulse">
        <input type="checkbox" id="Extra" class="Extra" checked/>
        <div class="state">
            <label>Extra</label>
        </div>
  </div>
  <!-- <label for="blue">VR/AR</label>
  <input type="checkbox" name="favcolor" class='XR' id="XR" value="VR/AR" checked> -->
</fieldset>



<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script>
$(document).ready(function () {
    $('.Course').change(function () {
        if (this.checked) $(".course").fadeIn();
        else $(".course").fadeOut();

    });
    $('.Extra').change(function () {
        if (this.checked) $('.extra').fadeIn();
        else $('.extra').fadeOut();

    });
    // $('.XR').change(function () {
    //     if (this.checked) $('.xrdisplay').fadeIn();
    //     else $('.xrdisplay').fadeOut();

    // });
});
</script>

{% for element in site.data.glossary %}
<div id="{{element.id}}" class="{{element.tag}}">
  <h4 id="{{element.name}}"><strong>{{element.name}}</strong></h4>
  <p>{{element.definition}}</p>
  <hr>
</div>
{% endfor %}


### **References:**

- [Wikipedia](https://en.wikipedia.org/wiki/Glossary_of_computer_graphics) 
- [IEEE](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=159476)
- [Autodesk](https://knowledge.autodesk.com)
- [Introduction to Graphics](http://math.hws.edu/graphicsbook/glossary.html)


