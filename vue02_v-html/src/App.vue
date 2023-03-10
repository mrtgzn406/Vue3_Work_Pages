<!-- ? Bu VueJS projesinde biz return nesnesinin değerini ekrana yazdırmak istiyoruz. Ama bu sefer ekrana yazdırmak istediğimiz nesnenin metnini bir html etiketiyle sarmaladık. Mesela metni <b> etiketiyle sarmalayarak kalın hale getirmek istedik, <u> etiketiyle sarmalayarak yazıyı altı çizili yapmak istedik. Yani string ifadesi içindeki html etiketlerinin, metin olarak değil html etiketi olarak işlenmesini istedik.  -->

<template>
  <p v-text="okul"></p>
  <p v-html="okul"></p>
  
  <div v-text="sınıf"></div>
  <div v-html="sınıf"></div>
  <!-- todo Görüldüğü üzere yukarıda anlatılan işlemi yapmak için biz html etiketine metni v-html="" metoduyla bağlıyoruz. Böylelikle string ifadesi içinde metni çevreleyen html etiketi yazı olarak değil, kod olarak algılanıyor.  -->

  <!-- * Yukarıdaki örneklerde görüldüğü gibi metni v-text="" metoduyla html etiketine bağlayınca string ifadesi içindeki html etiketleri normal metin gibi ekrana yazdırılıyor. v-html="" metoduyla metni bağlayınca ise o html etiketleri kod olarak algılanıyor. Mesela metin <u> etiketi ile sarmalanınca metin altı çizili halde ekrana yazdırılıyor.  -->

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {

  
  name: 'App', 
  data(){
    return {   
        okul: `<b>ataşehir adıgüzel myo</b>`,
        sınıf: "<u>2. Sınıf</u>"

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
