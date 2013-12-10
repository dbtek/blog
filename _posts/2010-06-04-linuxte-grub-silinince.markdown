---
author: dbtek
comments: true
date: 2010-06-04 14:53:46+00:00
layout: post
slug: linuxte-grub-silinince
title: Linux'te Grub Silinince...
wordpress_id: 167
categories:
- Bilişim-Teknoloji
tags:
- boot
- grub
- loader
- mbr
- pardus
- remove
- sildi
- silindi
- ubuntu
- wipe out
- yeniden
- yükle
---

Hayli zaman oldu bu sorunla karşılaşalı fakat ancak zaman bulabildiğim için şimdi yazmak kısmet oldu hakkında. Linux kullanıyorsunuz ama ara sıra da (mesela IDM'yi kullanmak için) Windows'u açıyorsunuz. Gel zaman git zaman windows her zamanki gibi sorun çıkarmaya başlar ve ardından bir gün dersiniz ki format atma zamanı geldi! (neden böyle bir zaman geliyorsa) Tamam sıkıntı yok windows 7 ile driver sorunu nisbeten gitti. Kuruyorsunuz Window'u bilgisayar yeniden başlatınca kendisini bir de bakıyorsunuz Grub yok. "Nerde benim ubuntu'm?",  bulamıyorsunuz. İşte bunun sebebi Windows MBR'nin tüm diskleri etkilemesi.

Gelelim çözümüne. Bu noktada Ubuntu'nun ya da hangi dağıtımı kullanıyorsanız onun da bir eksiği yok değil. Böyle bir durum için yükleme diskine düzeltme seçeneği koymuş olsalardı hiç fena olmazdı. Ben bir hayli aradım taradım konu hakkında ciddi kaynaklar var.

Örneğin;

[http://www.howtogeek.com/howto/ubuntu/reinstall-ubuntu-grub-bootloader-after-windows-wipes-it-out](http://www.howtogeek.com/howto/ubuntu/reinstall-ubuntu-grub-bootloader-after-windows-wipes-it-out)


{% highlight bash %}
sudo grub
root (hd0,0)
setup (hd0)
exit
{% endhighlight %}


Fakat bu kodlarda ben grub ile ilgili bir çok hata aldım. Live CD'yi denedim terminali denedim olmadı yine olmadı. Yahu bunun kodsuz, yazısız, klavyesiz en önemlisi sorunsuz bir çözümü yok mu derken...

En sonunda aynı sayfadaki bir yorumdan yola çıkarak harika bir çözüm buldum. "Super Grub Boot Disk” diye adlandırılan bir boot disk yapmışlar. Aslında benim aklıma gelmişti böyle bir şey de yapılmışı vardır demiştim  nitekim varmış :)

Hemen bir google araması ardından[http://www.supergrubdisk.org/](http://www.supergrubdisk.org/) bir de baktım hem cdrom için hem flash diskler için yapmış adamlar, dur dur floppy bile var :) Flash diskle bios'la uğraşılmaz şimdi dedim eski usul iso'yu indirip yazdım bir diske. Sistem çok basit takıyorsunuz CD'yi bilgisayarınızdan grub silinöiş olsa hatta hiç yüklü bile olmasa sabit disklerinizdeki işletim sistemlerini tarıyor, size de oklar ve enter tuşu kalıyor. Hemen linux'ümüzü açıyoruz. Grub'da problem olduğu için "_paket_ yöneticisi"ni açıyoruz. burada arama kutusuna grub yazmak suretiyle grub'u ve diğer ilişkili paketleri buluyoruz. Muhtemelen grub işaretli olacaktır. Yüklemek istediğimiz grub sürümünü işaretliyoruz ama bunun öncesinde işaretli olan bir grub varsa onu kaldırıyoruz. Uygula dedikten sonra Super Grub Boot Disk'i  cdrom'dan çıkarıyoruz. Bilgisayarı yeniden başlatıyoruz. Tekrar özlediğiniz grub ekranı tüm bileşenleriyle, Windows dahil, karşınızda.

Tekrar özetlemek gerekirse:

1-[http://www.supergrubdisk.org/index.php?pid=5"](http://www.supergrubdisk.org/index.php?pid=5) adresinden iso dosyasını indirip bir boş cdye nero ya da Windows disk yazıcısıyla yazın.
2-Diski bilgisayara takıp yeniden başlatın. Eğer cd'den boot olmuyorsa bios ayarlarınızda cdrom birincil boot aygıtı olarak seçilmelidir.
3- Açılan menüde Linux'ü seçerek işletim sisteminizi başlatın.
4-PC açılınca paket yöneticisini açın burada arama kutusuna grub yazın.
5-Eğer çıkan sonuçlarda grub vb gibi bir paketin yanındaki kutucuk işaretli ise bu paketi kaldırın.
6-Şimdi kurmak istediğiniz grub sürümünü işaretleyin ardından uygula deyip işlem bitince pencereyi kapatın.
7- Cdromdan diski çıkarıp bilgisayarı yeniden başlatın.

Hatasız olarak kurulum gerçekleştiyse grub ekranınız sorunsuz karşınıza çıkacaktır.

Geçmiş olsun...
