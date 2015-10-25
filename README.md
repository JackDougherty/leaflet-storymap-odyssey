# leaflet-storymap-odyssey
Modified version of CartoDB Odyssey.js story map template with Leaflet

## Credit
Original source: https://github.com/CartoDB/odyssey.js/blob/master/LICENSE

## Demo
http://jackdougherty.github.io/leaflet-storymap-odyssey

## Pros:
- Convenient online sandbox and downloadable code
- Easy to learn markdown syntax to create slides
- Display multiple markers in map; links, photos in story
- Option to display one CartoDB vizjson for the entire storymap

##To Do
- add L.layerControl to toggle on/off multiple basemaps and overlays?
- Experiment with Odyssey.js Advanced Sandbox and Javascript API features (and test video, sound): http://cartodb.github.io/odyssey.js/documentation/#advanced-use-of-the-sandbox
- Can individual geojson objects be added to specific slides? See complex customized example at https://github.com/clhenrick/BushwickCommunityMap, which includes this code in intro.js to display rheingoldPoly geojson object:
  ```
  Bushwick includes this intro.js
// check the index being returned by trackCurrentSlide()
  function checkIndex(index) {
    switch(index){
      case 0 : slideZero();
      break;
      case 1 : slideOne();
      break;
      case 2 : slideTwo();
      break;
      . . .
      default: console.log('out of slide counters');
    }
  }

  function slideZero() {
    el.map.setView(el.bushwick,15);
    el.dobPermitsNB.hide();
    el.taxLotActions['regular']();
    el.taxLots.show();
    el.featureGroup.clearLayers();
  }

  function slideOne() {
    el.featureGroup.clearLayers();
    el.featureGroup.addLayer(el.rheingoldPoly);
    el.map.fitBounds(el.rheingoldPoly, {paddingTopLeft: [125, 35]});
    el.taxLotActions['landuse']();
    el.taxLots.show();
  }
  ```

- Adjust calculations in the offsetHeight formula in index.html, which originally looked like this:
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
