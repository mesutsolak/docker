# Docker

## Nedir ?

Docker , kısa tanımıyla yeni nesil bir sanallaştırma platformudur.Bir makine üzerine farklı sanal makineler kurmamızı sağlamaktadır.Open Source Community sahiptir ve Go diliyle yazılmıştır.Uygulamayı güvenli bir şekilde izole etmek , hızlı ve esnek deployment kolaylığı sağlamaktadır.İşletim maaliyetini oldukça azalttığı için mikroservis mimarilerinde kullanılabilir , detaylıca monitör edilebilebilir, taşınabilir ve ölçeklendirilebilir bir sanallaştırma teknolojisidir.

Docker ayrıyeten development ortamındaki konfigürasyon ayarıyla test ortamındaki deployment ayarını aynı tutmaktadır.Böylelikle local'de çalışıyor test'e çalışmıyor gibi söylemlerinde önüne geçmiş olmaktadır.Docker'ı çok daha kısa bir şekilde açıklamak gerekirse bir sunucuda birkaç dakika içerisinde uygulamamızı kurmaya sağlayan bir teknolojidir. 

## Sanallaştırma Nedir ?

Bir işletim sistemi üzerine , farklı işletim sistemleri kurmak için gerekli olan teknolojilerin genel adına biz sanallaştırma diyoruz.
Bir işletme örneğin crm uygulama yayınlamak , ios testi yapabilmek için macos işletim sistemi kurmak istiyor.Böyle bir durumda her 2 durumunda sanallaştırma yöntemi kullanılmazsa eğer crm uygulaması yayınlamak için 1 ve ios yani macos sistem kurabilmek içinse 1 tane makine olmak üzere toplam da 2 adet makine alacaktır.

Fakat böyle bir durumda makinenin verimlilik durumunu düşürecektir ve gereksiz maaliyet çıkaracaktır.Bunun nedenlerine inecek olursak her yapılacak işlem için farklı bir makine almak zahmetli olacaktır.
Bunun yanında farklı makineler almamız onların tamamını kullanacağımız anlamına da gelmemektedir.Bu da haliyle verimlilik açısından oldukça aşağıda kalacaktır.

Bu işleri yapmak yerine sanallaştırma yöntemi kullanarak , bir makinenin içerisinde farklı alanlar oluşturup makinen %100 kullanabiliriz.Böylelikle hem maliyet hem de verimlilik açısından oldukça yarar sağlamış oluruz. 

## Eski teknolojilerden farkı nedir ?

<ul>
  <li>Eski teknolojilere göre docker daha hızlı çalışmaktadır.</li>
  <li>Eski teknolojilerde sanallaştrıma teknolojisi olarak hypervisor kullanılırken docker teknolojisinde hypersivor yerine docker ve host operating system kullanılmaktadır.</li>
  <li>Eski teknolojilerde kurulan yerel sanal makineye misafir bir işletim sistemi ve uygulama dosyaları (kütüphaneler , publish dosyaları vs) kurulurken docker teknolojisinde sadece uygulama dosyaları kurulmaı gerekir.</li>
  <li>Eski teknolojilerin genel adı <b>Virtual Machine</b> olarak isimlendirilirken docker teknolojisiyle beraber bu isim <b>Container</b> olmuştur. </li>
  <li>Hypervisor , farklı seviyelerde donanımı paylaştırarak , bellek yönetimini izole hale getirir.Dockerın kendisi bir platformdur.Bilgisayarda kurulan Docker Engine üzerinden containerlar çalıştırarak paylaşımlarını gerçekleştirir.</li>
</ul>

<table>
  <thead>
    <tr class="alt">
      <th></th>
      <th>Virtual Machine</th>
      <th>Docker</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="font-weight: bold;text-align: left;">OS</td>
      <td>Tam işletim sistemi</td>
      <td>Küçültülmüş işletim sistemi</td>
    </tr>
    <tr class="alt">
      <td style="font-weight: bold;text-align: left;">İzalasyon</td>
      <td>İşletim sistemi seviyesinde. Yüksek</td>
      <td>Container seviyesinde. Düşük</td>
    </tr>
    <tr>
      <td style="font-weight: bold;text-align: left;">Çalışır hale gelmesi</td>
      <td>Dakikalar</td>
      <td>Saniyeler</td>
    </tr>
    <tr class="alt">
      <td style="font-weight: bold;text-align: left;">Versiyonlama</td>
      <td>Yok</td>
      <td>Var</td>
    </tr>
    <tr>
      <td style="font-weight: bold;text-align: left;">Kolay paylaşılabilirlik</td>
      <td>Düşük</td>
      <td>Yüksek</td>
    </tr>
  </tbody>
</table>

## Container Nedir ?

Container , yazılım uygulamalarını izole edilmiş ve taşınabilir bir şekilde çalıştırmak için kullanılan hafif sanallaştırma teknolojisidir.Mini işletim sistemi olarak da düşünebiliriz.

## Ürünleri Nelerdir ?
Docker'ın docker hup - docker desktop - docker enterprise olmak üzere 3 ürünü bulunmaktadır.

<b><i> Docker Hub: </i></b> Bu, Docker'in bulut tabanlı bir hizmetidir ve kullanıcıların uygulamalarını, görüntülerini ve konteynerlerini paylaşmalarını ve depolamalarını sağlar. Docker Hub ayrıca otomatik oluşturma ve test süreçleri için entegrasyon sağlar. Genellikle yazılım geliştirme ve paylaşım süreçlerini kolaylaştırmak için kullanılır.

<b><i> Docker Desktop: </i></b> Bu, Docker'in masaüstü uygulamasıdır ve kullanıcılara Docker konteynerlerini kendi bilgisayarlarında çalıştırma imkanı sunar. Geliştiriciler, Docker Desktop kullanarak uygulamalarını yerel olarak test edebilir, geliştirebilir ve çalıştırabilirler. Docker Desktop, hem Windows hem de MacOS işletim sistemlerinde kullanılabilir.

<b><i> Docker Enterprise: </i></b> Bu, Docker'in kurumsal ölçekte kullanım için tasarlanmış bir ürünüdür. Bu platform, büyük ölçekli kuruluşların konteyner tabanlı uygulamaları geliştirmesine, yönetmesine ve dağıtmasına olanak tanır. Docker Enterprise, güvenlik, ölçeklenebilirlik ve yönetilebilirlik gibi işletme düzeyindeki ihtiyaçları karşılamak için gelişmiş özellikler sunar.

Bu üç ürün, Docker'in farklı kullanım senaryoları için farklı gereksinimleri karşılamak üzere tasarlanmıştır. Docker Hub, Docker Desktop ve Docker Enterprise, geliştiricilerin, uygulama geliştirme ve dağıtım süreçlerini kolaylaştırırken aynı zamanda işletmelerin konteyner tabanlı altyapılarını etkili bir şekilde yönetmelerine olanak tanır.
