<template >
  <pre ref="vCard">
    <div style="width: 300px; height: 300px; align-self: center;">
      <div id="container">
        <h1>Hello World</h1>
      </div>
      <button @click="downloadPackage">Save QR Code</button>
    </div>
  </pre>
  </template>
  
  <script>
//  import QRCode from '~/test/dist/qrcode'
 
  export default {
    mounted() {
      this.generateQRCode(); // Call the method to generate QR code when component is mounted
    },
    methods: {
      generateQRCode() {
        var qrcode = new QRCode({
          content: "Raju",
          container: "svg-viewbox", // Update the container reference to "container"
          join: true // Crisp rendering and 4-5x reduced file size
        });
        var svg = qrcode.svg();
        document.getElementById("container").innerHTML = svg;

      },
     
    }
    
  };
  </script>
  