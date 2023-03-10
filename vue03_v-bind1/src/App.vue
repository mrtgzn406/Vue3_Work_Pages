<!-- ? Bu projede VueJS'in v-bind="" özelliği anlatılmıştır. v-bind metodu sayesinde biz html etiketlerinin özelliklerine bağlanabiliyoruz. Bu metodu kullanırken etiketin içine ilk önce v-bind yazarız, ardından bağlanmak istediğimiz html özelliğini yazarız, mesela v-bind:disabled="" yazarsak bu bizim etiketin disabled özelliği ile işlem yapmak istediğimizi,  v-bind:class="" yazarsak , bu bizim o html etiketinin  class attribute'u ile işlem yapmak istediğimizi belirtir. -->

<!-- ? Eğer metodun çift tırnağı içine ("") bir javascript değişkeni yazılırsa ve  o değişken de data (){} fonksiyonu içindeki return {} nesnesinin özelliği olursa; işte o zaman o özelliğin karşısındaki değer ister string ister number ister boolean olsun html etiketinin class attribute'una değer olarak atanır.  -->


<template>
  <div v-bind:id="ozellik1">
    <!-- todo Burada biz v-bind:id="ozellik1" yazarak script etiketi arasındaki return komutunun "ozellik1" ismindeki property'sinin değerini bu html etiketine id olarak atadık, böyelikle bu html etiketine style etiketi arasında yazılan "#ozellik1" ismindeki css seçicisinin içindeki css kodları uygulandı. -->
    
    <div class="bolumler">
      <!-- ! Bu bolumler class'ına sahip etiketleri sırf üzerinde çalıştığımız içerikler düzgün görünsün, aralarında makul bir boşluk oluşsun diye yaptık -->
      
      <button v-bind:class="ozellik2">Buton1</button>
      <button v-bind:class="ozellik2"  v-bind:disabled="degerGecerliMi">Bu buton geçersiz kılındı</button>

      <!-- todo Yukarıdaki iki butondan birincisine sadece ozellik2 ismindeki javascript özelliğinin değerini class olarak verdik, o class'a da css olarak değerler verdik.  İkincisine ise hem javascript özelliği değerini hem de html etiketinin "disabled" özelliğini verdik -->
    </div>

    <!-- ***************************************************************************************** -->
    
    <div class="bolumler">
      <div v-bind:class=" degerGecerliMi && ozellik3  ">Burası pencere</div>
      <!-- todo Burada ise v-bind:class="" metoduna && (ve) operatörüyle bir koşul yazdık ve o koşula göre özellik3 isimli javascript property'sinin değeri etiketin class'ına verilecek.  -->

      <!-- ? && operatörü şu şekilde çalışıyor : Eğer bu operatörün (&&) sol tarafında yazılan koşul doğru ise sağ tarafındaki değişken değerini döndürür, yanlış ise hiçbir şey yapmaz. -->
      
    </div>
    
    <!-- ***************************************************************************************** -->
    <div class="bolumler">
      <div v-text="arabaYeniMi ? yeniAraba : eskiAraba"></div>
      <!-- todo Burada ise v-text="" metodunu kullanıp içine koşul yazarak,  koşuldan dönen property değerini buraya ata demiş olduk. Böylelikle bu v-text="" metodu property değerini metin olarak etikete yazdırıyor.   -->
      
    
    
    <!-- ----------------------------------------------------------------------- -->
    
      
      <div v-bind:class="degerGecerliMi ? 'gecerli' : 'gecersiz' "> Değer Geçerli Mi</div>
      <!-- todo Burda ise v-bind:class="" metoduna ternary operatörüyle bir koşul yazdık eğer "?" işaretinin sol tarafındaki koşul "true" döndürürse "?" işaretinin sağ tarafındaki değer döndürülür, yok koşul "false" ise ":" işaretinden sonraki değer döndürülür ve class olarak atanır.  -->
    </div>

    
    <!-- ***************************************************************************************** -->

    <!-- ? Eğer VueJS'de bir etikete vue js metodlarını kullanarak birden değişken değeri atamak veya birden fazla koşullu atama yapmak istiyorsak  bunu yapmanın 2 yöntemi vardır: 
      todo 1.) Dizi ile çoklu değer ataması,
      todo 2.) Nesne ile çoklu değer ataması.  -->

      <!-- * 1) Dizi İle Çoklu Değer Atama -->
    <div class="bolumler">

      <a href="" v-bind:class="[dizi[0], dizi[1], dizi[2]]">Dizi Versiyon 1</a>
      <!-- ! burada birden fazla class index operatörü içinde [] dizi elemanları olarak atanmıştır.-->

      <a href="" v-bind:class="['diziOzelligi1', 'diziOzelligi1:hover','diziOzelligi2']">Dizi Versiyon 2</a> 
      <!-- ! burada birden fazla class yine index operatörü içinde class ismi olarak atanmıştır. Class olarak atandığı için ifadeler tek tırnak içine alınmaktadır, eğer script değişkeni olarak alınsaydı değişkenin ismi sade yazılmalıydı. -->

      <p v-bind:class="[degerGecerliMi && p_etiketi, degerGecerliMi? 'gecerli' : 'gecersiz']" >Koşullu Dizi Versiyonu</p>
      <!-- ! burada ise birden fazla değer yine index operatörü içinde koşullarla yazılmıştır, böylelikle her koşul bir sonuç döndürecek ve dönen sonuçlar da class olarak atanacak. Koşullar ise birbirlerinden virgül (,) ile ayrılacaki aynı normal bir Array (dizi) gibi. -->

      
      <!-- todo Bu kısımda v-bind:class="" metoduna birden fazla değeri atamak için index operatörünü [] kullandık. Bu operatörün içine gerek class ismini tek tırnak içinde, gerek javascript değişkenini (property) sade olarak, gerekse de geriye bir değer döndüren koşullu ifade olarak yazdık. -->
     
         <!-- ----------------------------------------------------------------------- -->
      <!-- * 2.) Nesne İle Çoklu Değer Atama -->

      
    </div> 
    
    <div class="bolumler">

      <a href="" v-bind:class="{
        'diziOzelligi1' : 10 >= 4,
        'diziOzelligi1:hover' : 100 > 18,
        'diziOzelligi2' : 75 > 14
      }">Nesne Versiyon 1</a>

      <!-- ! Burada birdeb fazla class'ı nesne özelliği olarak veriyoruz. Bunu yapmak için öncelikle v-bind:class="{}" şeklinde yazıyoruz ve o kuvırcık parantez {} içine nesnenin "key-value pairs" yani anahtar-değer çiftlerini yazıyoruz. Burada key yerine yazdığımız ifade, html etiketine class olarak atanır ve onun karşısındaki "value" ise o class'ın atanıp atanmayacağını bildiren, içinde koşul yazılabilen yerdir, koşul sonucunda bir boolean (true-false) değer döndürülür. Eğer bu key-value pairs içindeki "value" "true" dönerse "key" yerine yazdığımız değer class olarak atanır, yok eğer "false" dönerse class atanmaz.   -->

      <a href="" v-bind:class="{
        'diziOzelligi1' : true,
        'diziOzelligi1:hover' : false,
        'diziOzelligi2' : true
      }">Nesne Versiyon 2</a>

      <!-- ! Burada üssteki versiyonun neredeyse aynısını yaptık , tek fark burada koşul yazmak yerine direkt  "true", "false" yazdırdık. -->


      <p v-bind:class="{
        'gecerli': degerGecerliMi == false,
        'paragraf' : degerGecerliMi == true
      }">Koşullu Nesne Version</p>

    <!-- ! Burada da üstteki versiyonların benzerini yaptık.   -->
      




    </div>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// ? Burada ise bir vuejs projesi oluşturduğumzda components klasörünün içinde gelen ve varsayılan olarak projede gelen HelloWorld.vue dosyasını 

export default {
  name: 'App',
  data (){
    return {
      ozellik1: "kapsayici",
      ozellik2: "butonlar",
      ozellik3: "pencere",
      degerGecerliMi: true,


      arabaYeniMi: false,
      yeniAraba: "2022 model Wolkswagen Passat",
      eskiAraba: "2010 model Toyota Corolla ",


      dizi: ['diziOzelligi1', 'diziOzelligi1:hover', 'diziOzelligi2'],

      p_etiketi : 'paragraf',

      isimler : ["ekrem", "kürşat", "olga", "yunus"]






      }
    }
  }

</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  #kapsayici{
    margin: auto;
    width: 800px;
    /* min-height: 200px; */
    background-color: white;
    font-size: large;
  }
  .butonlar{
    /* color: aqua;
    background-color: black; */
    min-width: 100px;
    height: 50px;
    margin-right: 20px;
  }


  .pencere{
    width: 400px;
    height: 200px;
    font-size: 3rem;
    background-color: blue;
    color: aliceblue;
  }

  .gecerli{
    color: green;
  }
  .gecersiz{
    color:red;
  }


  .diziOzelligi1{
    /* width: 100px; */
    height: 60px;
    line-height: 60px;
    color: white;
    background-color: black;
  }
  .diziOzelligi1:hover{
    color: rgb(253, 189, 11);
    background-color: rgb(7, 109, 61);
  }
  .diziOzelligi2{
    display: block;
    text-decoration: none;
  }

  .bolumler{
    height: 200px;
    margin-bottom: 50px;
    background-color: darkgrey;
    border: 5px groove red;
  }

  .paragraf{
    border: 5px solid rgb(10, 157, 255);
    /* background-color: rgb(180, 6, 233); */
    height: 50px;
    width: 400px;
    text-transform: uppercase;
    padding: 10px;
    /* margin-left: 100px;  */
    margin: auto;
    margin-top: 20px;
    /* display: block; */
  }



</style>
