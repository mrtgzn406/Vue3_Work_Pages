<!-- ? Bu proje bizim VueJS projelerindeki temek kısımları anlattığımız ve metni bağlama (binding text) konusunu anlattığımız projedir. VueJS projesini komut satırı üzerinden oluştururuz, detaylar için "VueJS_3_Lessons" isimli klasörün içindeki "beniOku.txt" dosyasına bakın.  Metni bağlama işlemleri mustache syntax {{}} veya v-text="" metodu kullanılarak yapılabilir, iki yöntem de anlatılmıştır. -->

<template>
  <!-- todo template kısmı VueJS projelerinde html etiketlerini yazdığımız kısımdır.  -->


  <!-- !  -->
  <div>{{ `benim adım ${ad} soyadım ise ${soyad}` }}</div>
  <div>Kişinin adı {{ ad }} {{ soyad }}</div>

  <!-- todo Vue.js'de eğer sen "default" isimli nesnenin "data" fonksiyonundaki "return" özelliklerini bir html etiketine bağlamak ve ekrana yazdırmak istiyorsan, bunun için mustache syntax (çift kıvırcık parantez)  {{  }} kullanacaksın ve değişkeni veya template literal'i bunun içine yazabilirsin. Bir elemanın içine birden fazla mustache syntax kullanabilirsin.  -->
  <!-- ! Not: Eğer html etiketinin içinde zaten bir metin varsa ve biz mustache syntax (çift kıvırcık parantez) ile sadece o var olan metne ek bir metin ekleyeceksen o zaman mustache syntax kullanmak zorundayız. Çünkü bu işlem için v-text="" metodunu kullanamayız, o metod etiketin içindeki metni tamamen silip , metot içinden dönen değeri metin olarak etikete yazdırır.  -->

  <!-- ----------------------------------------------------------------------------- -->

  <div v-text="`benim türkçe sınavından ${notlari.türkçe} alırken matematik sınavından ${notlari.matematik} aldım  `"></div>
  <!-- todo Yine VueJS'de değişkenleri aynı yukarıdaki gibi html etiketine bağlayıp ekrana yazdırmanın diğer bir yolu da direktifleri kullanmaktır, mesela v-text="" metodu metinleri html öğelerine bağlamak için kullanılır, ilk önce o metodun hangi html öğesinde çalışacağını belirtmek için o metodu bir html etiketinin özelliği olarak yazarız v-text="" olarak ve metodun içine de o html etiketine yazdıracağımız javascript ifadesini, template literal'ı yazarız. -->
  <!-- ! Bir VueJS kuralı olarak bütün direktiflerin başında v- öneki (prefix)  yer alır. Bu o metodun bir VueJS metodu olduğunu gösterir. -->
  <!--  -->
</template>


<script>

// todo script kısmı VueJS projelerimizde Javascript kodlarını yazdığımız yerdir 


// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data () {

    return{
      ad : "murat",
      soyad : "gözen",
      notlari : {
        matematik: 100,
        türkçe: 94,
        fizik : 85,
        kimya: 91
      }

    }
  }
}
</script>

<style>
/* todo style kısmı ise projelerimizde css kodlarını yazdığımız yerdir. */
  body{
    background-color: #06088f;
    font-size: 30px;
    color: white;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    /* color: #2c3e50; */
    margin-top: 60px;

  }
</style>
