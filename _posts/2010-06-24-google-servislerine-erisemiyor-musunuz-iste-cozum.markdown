---
author: dbtek
comments: true
date: 2010-06-24 18:30:38+00:00
layout: post
slug: google-servislerine-erisemiyor-musunuz-iste-cozum
title: Google servislerine erişemiyor musunuz? İşte çözüm!
wordpress_id: 173
categories:
- Bilişim-Teknoloji
tags:
- blok
- dns
- engel
- erişim
- girme
- google
- ip
- picasa
- telekom
---

Bilindiği üzere Telekom'un google ip'lerine  karşı koyduğu engellemeden dolayı bazı google servislerine erişim  kısıtlanmıştı.

Sitenizde picasa'dan embed ettiğiniz fotoğrafları görememenizin ve de bu fotoğrafların bulunduğu sayfaların geç açılmasının  yegane sebebi Telekom'un google ip'lerine koyduğu yasaktan dolayı bu  sayfaya google'ın fotoğraf servisi picasa'dan veri çekilememesidir.

Bu  sayfada bu engelellemeyi aşmanın bir yolu olan google DNS ayarlarının kullanımını anlatacağım.

<!-- more -->

Öncelikle  erişip erişemediğimizi kontrol edelim. Zira bazı kullanıcılarda bu ip  engeline rastlanılmadığı da oluyor.

Örnek olarak picasa'yı  deneyebiliriz. Farklı bir google servisini de erişemeyebilirsiniz diğer  servisleri de denemekte yarar var.

[http://picasaweb.google.com](http://picasaweb.google.com/) bağlantısına tıklayınca uzunca beklemeden sonra sayfa görüntülenemiyor hatası mı alıyorsunuz? O  zaman aşağıdaki çözüm işinize yarayacak demektir. (En azından bende işe  yaradı.)

Windows Vista / 7 için:

1-Öncelikle Ağ ve  Paylaşım Merkezi'ne giriyoruz.

<pre>Image Lost</pre>

2-Bağlı  bulunduğumuz ağın üzerine tıklıyarak aşağıdaki pencerenin açılmasını  sağlıyoruz.

<pre>Image Lost</pre>

3- Internet Protocol Version 4 (TCP/IPv4)  seçeneğine çift tıklıyoruz.

<pre>Image Lost</pre>

4- Yukarıdaki resimde görüldüğü gibi DNS adresine  8.8.8.8 ve alternatif DNS'ye de 8.8.4.4 girerek tamam tuşuna basıp  işlemi tamamlıyoruz.

Geçmiş olsun umarım artık picasa vb google servislerine sorunsuz girebileceksiniz.
