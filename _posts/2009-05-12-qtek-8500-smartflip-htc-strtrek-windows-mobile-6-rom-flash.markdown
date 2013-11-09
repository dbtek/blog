---
author: dbtek
comments: true
date: 2009-05-12 19:06:00+00:00
layout: post
slug: qtek-8500-smartflip-htc-strtrek-windows-mobile-6-rom-flash
title: qTek 8500 - Smartflip - HTC Strtrek - Windows Mobile 6-Rom Flash
wordpress_id: 97
categories:
- Mobil
tags:
- '6'
- '8500'
- cid unlock
- htc
- Mobil
- qtek
- ROM
- smartflip
- strtrek
- update
---

Bugün windows mobile 5 tabanlı smartphone'uma rom attım. Gerçekten de zor bir işmiş daha önce hiç yapmayan birisi için aslında. Bir de pek fazla türkçe kaynak olmayınca da ekleyince işler baya bir zorlaşıyor. Bugün yaptığım işlemleri anlatıp bu konudan muzdarip olan arkadaşlara da yardımcı olmak istiyorum. Hadi başlayalım :)  
  
  
Öncelikle cihazımıza CID unlock dediğimiz işlemi yaparak rom'u flash'lıyoruz.  


1. [regeditstg](http://wiki.xda-developers.com/uploads/regeditSTG.zip) programını indirip telefonumuza yüklüyoruz.(kopyalamak yeterli)  


  * HKEY_LOCAL_MACHINESecurityPoliciesPolicies000 1001 = 2 --> Buradaki 2 olan değeri 1 ile değiştiriyoruz.  

  * HKEY_LOCAL_MACHINESecurityPoliciesPolicies000 1005 = 16 --> Buradaki 16 olan değeri 40 ile değiştiriyoruz.
  * HKEY_LOCAL_MACHINESecurityPoliciesPolicies000 1017 = 128 --> Buradaki 128 olan değeri 144 ile değiştiriyoruz. 
  * Telefonu yeniden başlatıyoruz.  

2- [SDA_Application Unlock](http://wiki.xda-developers.com/uploads/SDA_ApplicationUnlock.zip) programını bilgisayardan çalıştırıp unlock deyip elefonu yeniden başlatın.  
3-[Itsutils](http://www.xs4all.nl/%7Eitsme/projects/xda/tools.html)  programını bu sayfadan edinebiliriz. [050628](http://nah6.com/%7Eitsme/download/itsutl050628.zip) sürümünü indirin diğerlerinde denemedim. C:/Temp klasörüne indirdiğimiz Itsutils.zip arşivini çıkartın.  
4-Telefonu Vista veya Windows 7 kullanıyorsak W.Mobile Device Center, XP kullanıyorsak ActiveSync ile USB kablodan bağlıyoruz.  
5- Komut satırına giderek (başlat+r kombinasyonuyla cmd yazıp çalıştırabiliriz.) C:tempbuild klasörüne gidip buradaki pdocread.exe programını argümansız olarak çalıştırın. Telefonu kontrol edin, gerekli onayı verdikten sonra işlem başlayacaktır.  
6-Program bir "uniqueid" isimli  00 00 00 00 12 03 02 14 3b 07 1b b2 04 05 07 54 gibi bir hex değer üretecektir, bunu bir yere not edin ya da cmd'den kopyalayın.  


7-pdocread'ı bir daha şu şekilde çalıştırın: pdocread -n 1 0x000000 0x10000 -b 0x4000 original-bdk1.nb (komut satırına aynen kopyala) Bu işlemle build klasörüne original-bdk1.nb diye bir dosya oluşturmuş oluyoruz.  
8-Bu dosyayı [http://www.spv-developers.com/strtrkCID/ ](http://www.spv-developers.com/strtrkCID)adresine upload edin.  DOCID: yazan bölüme de cihazın unique id'sini yazın. Submit ettikten sonra gelen sayfanın en son bölümünden supercidxxxxxxx.bin tarzında bir isimli dosyayı indirin. Bu dosyayı da build klasörüne kopyalayın.  
9-Şimdi pdocwrite programını şu argümanlarla çalıştırın. pdocwrite -n 1 supercidxxxxxxx.bin 0x000000 0x10000 -b 0x4000  supercidxxxx.bin deki xxx leri kendi dosyanızdaki karakterlerle değiştirin.  
  
15 20 sn bekledikten sonra cihazı yeniden başlatın işlem tamam!  
  
  
Sıra geldi ROM yüklemeye..  
  
Ben windows mobile 6 clean diye bir ROM buldum Office, Adobe Reader falan kurulu değil haliyle 64 mb'lık yerde bunu kullanmak daha mantıklı geldi. [Şuradan](http://rapidshare.com/files/105213653/RUU_STARTREK_WM6.1_19202_Clean_0.4.rar) edinilebilir.  
  
1-SoftSPL klasöründeki dosyaları direkt olarak telefonun root klasörüne atın. (klasörle birlikte değil sadece içindekileri.)  
2-SDA_ApplicationUnlock yapılmadıysa bu programla unlock edin.  
3-spl.lnk yı telefondan çalıştırın.  
4-Rom Update Utility i çalıştırın yönergeleri izleyerek işlemi tamamlayın.  
  
CIDUnlock yaptıktan sonra yukarıdaki ROM'u kurabileceğiniz gibi istediğiniz herhangi bir Romu da kurabilirsiniz.  

