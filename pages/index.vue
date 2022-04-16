<template>
  <div>
    <div class="text-center">
      <h1 class="text-lg m-10 font-bold text-xl">Managing Image Device Pixel Ratio</h1>
    </div>
    <div
      v-for="(option,index) in dprOptions"
      :key="index"
      class="grid grid-cols-2 bg-gray-100 m-10 overflow-hidden rounded-lg shadow-sm ring-1 ring-black ring-opacity-5"
    >
      <cld-image
        :publicId="imagePublicId"

      >
      <cld-transformation height="300" width="300" crop="thumb" />
        <cld-transformation :dpr="option" />
      </cld-image>
      <div class="text-right p-10 grid grid-rows-4 text-lg">
        <p>DPR: {{option}}</p>
        <p>Width: 300</p>
        <p>Height: 300</p>
        <p>Crop: Thumb</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      imagePublicId:"nuxtjs-image-device-pixel-ratio/pexels-kelson-downes-1149137",
      dprOptions:["1.0","2.0","3.0","auto"]
    }
  }
}
</script>
