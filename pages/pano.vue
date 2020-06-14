<template>
  <div id="pano">
    <!-- <noscript>
      <table style="width:100%;height:100%;">
          <tr style="vertical-align:middle;">
            <td>
              <div style="text-align:center;">
                ERROR:
                <br />
                <br />Javascript not activated
                <br />
                <br />
              </div>
            </td>
          </tr>
        </table>
    </noscript> -->
  </div>
</template>
<script>
var krpano = null;

function krpano_onready_callback(krpano_interface) {
  krpano = krpano_interface
}

export default {

  mounted() {
    embedpano({
      swf: "../VR_Web/tour.swf",
      xml: "../VR_Web/tour.xml",
      target: "pano",
      html5: "auto",
      mobilescale: 1.0,
      passQueryParameters: true,
      onready: krpano_onready_callback
    })
    // this.getHotspots(1, 3)
  },
  methods: {
    // async getHotspots(currentPage, pageSize) {
    //   const dataTest = await getHotspots({
    //     pageNum: currentPage,
    //     pageSize: pageSize
    //   })
    //   // 实现 js 和 xml 交互
    //   krpano.call('set(hotspot[spot_0_2].title,'+dataTest.data.message+')')
    // }
  }
}
</script>

<style>

#pano {
  width: 100%;
  height: 100%;
}
</style>
