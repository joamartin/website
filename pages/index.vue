<template>
  <section class="section">
    <div id="map" />
    <div class="container is-desktop">
      <div class="columns is-desktop">
        <div class="column is-one-quarter">
          <figure class="image is-128x128 image-profile">
            <img class="is-rounded" src="~/assets/profile_b&w.png">
          </figure>
        </div>
        <div class="column">
          <div class="main-content">
            <p>
              Hi, my name is Joaquim Martin and I am a freelance web developer living in Lyon, France.
            </p>
            <p>
              My area of focus is <a href="https://en.wikipedia.org/wiki/Web_mapping" target="_blank">web mapping</a>
              so I concentrate on projects with an emphasis on <strong>geographic data</strong>.
            </p>
            <p>
              Predominantly, I am involved in the visualization / rendering side of a project, delivering <strong>intractive maps</strong>
              using Javascript libraries such as <a href="https://openlayers.org/" target="_blank">OpenLayers</a> or <a href="https://leafletjs.com/" target="_blank">Leaflet</a>
              .
            </p>
            <p>
              Besides that I appreciate developing with <strong>Vue.js</strong> framework and I also happened to work on the server / Database side or on desktop apps.
            </p>
            <p>
              I frequently work for the NGO <a href="https://www.cartong.org/" target="_blank">CartONG</a> for which I am also involved as a volunteer.
            </p>
            <p>
              If you would like to get in touch, feel free to send me an email at <a href="mailto:jmartin@jmartin.io">jmartin@jmartin.io</a>.
            </p>
            <hr>
            <div class="networks">
              <a href="mailto:jmartin@jmartin.io" title="contact">
                <b-icon icon="email" />
              </a>
              <a href="http://linkedin.com/in/joaquim-martin-336102b5" title="LinkedIn" target="_blank">
                <b-icon icon="linkedin-box" />
              </a>
              <a href="https://gitlab.com/jmart" target="_blank">
                <b-icon icon="gitlab" pack="fab" title="gitlab" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  head() {
    return {
      title: 'Joaquim Martin',
      meta: [{
        hid: 'description',
        name: 'description',
        content: 'Joaquim Martin freelance web developer. Javascript, web mapping, OpenLayers, Leaflet, Vue.js'
      }]
    }
  },

  mounted: function () {
    const L = this.$L

    const options = {
      dragging: false,
      scrollWheelZoom: false,
      zoomControl: false
    }

    const map = L.map('map', options)
      .setView([45.7578137, 4.8320114], 16)

    const layer = L.tileLayer('https://tiles.wmflabs.org/bw-mapnik/{z}/{x}/{y}.{ext}', {
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
      // subdomains: 'abc',
      minZoom: 0,
      maxZoom: 19,
      ext: 'png'
    })

    map.addLayer(layer)
  }
}
</script>
