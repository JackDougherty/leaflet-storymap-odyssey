##To-Do

Experiment with Odyssey.js Advanced Sandbox and Javascript API http://cartodb.github.io/odyssey.js/documentation/#advanced-use-of-the-sandbox

Center the Prev/Next arrows < > and the Dots div (••••)

Redo the offsetHeight formula in index.html, which originally looked like this:
```
function adjustSlides() {
      var container = document.getElementById("slides_container"),
          slide = document.querySelectorAll('.selected_slide')[0];

      if (slide) {
        if (slide.offsetHeight+169+40+80 >= window.innerHeight) {
          container.style.bottom = "80px";

          var h = container.offsetHeight;

          slide.style.height = h-169+"px";
          slide.classList.add("scrolled");
        } else {
          container.style.bottom = "auto";
          container.style.minHeight = "0";

          slide.style.height = "auto";
          slide.classList.remove("scrolled");
        }
      }
```
