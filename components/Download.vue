<template>
  <div id="downloadSection" class="mt-16">
    <h2 class="font-extrabold text-2xl">Download</h2>
    <div class="stepC mt-6">
    

       <button 
       ref="downloadPackage"
       @click="downloadPackage"
       class="mt-5 inline-block bg-emerald-700 leading-none text-2xl tracking-wide border-2 border-transparent font-extrabold p-6 rounded mt-6 select-none transition-colors duration-200 hover:bg-emerald-600  focus:bg-emerald-600
 text-white ">
      Download as ZIP
      </button>
    </div>
  </div>
</template>

<script>
// // import QRCode from '~/test/dist/qrcode'
// import QRCode from 'qrcode';
export default {
  props: ['downloadPackage'],
}
</script>