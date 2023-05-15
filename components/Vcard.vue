<template>
  <pre v-show="false" ref="vCard">
BEGIN:VCARD
VERSION:3.0
N:{{ getSplitName }}
FN:{{ getFullname }}
ORG:{{ vCard.org }}
ADR;TYPE=WORK:{{ getAddress }}
TITLE:{{ vCard.title }}
TEL;TYPE=CELL:{{ vCard.cell }}
TEL;TYPE=WORK:{{ vCard.work }}
TEL;TYPE=HOME:{{ vCard.home }}
TEL;TYPE=MSG:{{ vCard.sms }}
EMAIL;TYPE=WORK:{{ vCard.email }}
URL;TYPE=Digital Business Card:{{ vCard.hostedURL }}
KEY;TYPE=PGP;ENCODING=b:{{ vCard.key }}
NOTE:{{ vCard.note }}
PHOTO;TYPE=JPEG;ENCODING=BASE64:{{ profilePhotoSrc }}
END:VCARD

<!-- URL:{{ vCard.website }}
{{ getURLs }} -->
<!-- UID:{{ vCard.uid }} -->
</pre>
</template>

<script>
export default {
  props: ['vCard','base64string'],

  computed: {
    // getURLs() {
    //   return this.vCard.urls
    //     .map((e) => `URL;TYPE=${e.title}:${e.url}`)
    //     .join('\n')
    // },
    getSplitName() {
      let fn=this.vCard.fn
      let ln = this.vCard.ln
      return `${ln ? ln : ''};${fn ? fn : ''};;;`
    },
    getFullname() {
      let fn = this.vCard.fn
      let ln = this.vCard.ln
      return (fn + ln).length ? `${fn ? fn : ''}${ln ? ' ' + ln : ''}` : null
    },
    getAddress() {
  let address = this.vCard.addr;
  if (address === null) {
    return ''; // Return empty string if address is null
  }
  //address = address.replace(/\s+/g, ''); // Remove spaces from address
  return address === '' ? '' : address.replace(/[\.\•]/g, ';;;');
    },
    profilePhotoSrc() {
      return this.$props.base64string;
    }

    
  },
}
</script>
