---
author: dbtek
comments: true
date: 2013-08-26 11:38:10+00:00
layout: post
slug: raspberry-pi-ssh-destegi-ile-boot
title: Raspberry Pi, SSH Destegi ile Boot
wordpress_id: 478
categories:
- Bilişim-Teknoloji
- Linux
tags:
- boot
- klavye
- Linux
- monitor
- pi
- raspberry
- ssh
- ssh desteği
---
[![plogo](http://blog.ismaildemirbilek.com/wp-content/uploads/2013/08/plogo.png)](http://blog.ismaildemirbilek.com/wp-content/uploads/2013/08/plogo.png)

Bilindiği gibi Raspberry Pi için oluşturulan distrolar monitör ve klavye ile boot edilip kullanıma hazır hale geliyor. Peki HDMI destekli bir monitörünüz yoksa ne yapacaksınız?

Linux makinelere ssh protokolü ile bağlanıp bash'te komut çalıştırılabilir. Ancak makine'de ssh server bulunmalı ve bu makinede bir takım konfigürasyonlar yapılmalıdır. Bu konfigurasyonlar monitör olmadığı için yükleme yapılmış sd kartta boot öncesi yapılmak zorunda. Bir takım araştırmalar sonucu elde ettiğim bilgileri adım adım yapılacaklar biçiminde derledim.<!-- more -->


Raspbian wheezy imajı (Pi için Debian distrosu) kurulu bir sdkartın hazır olduğunu varsayarak, _Ubuntu/Linux üzerinde_, sonraki adımlara göz atabiliriz. (Raspbian kurulumu için [tıklayınız](Using_command_line_tools_.282.29).)


Raspbian kurulu sdkart üzerinde iki partition bulunur. Bunlardan birisinde bin, dev, etc.. gibi dizinler var. Bu partition üzerinde işlem yapılacaktır. Verilen dizin yapısı buna göre değerlendirilmelidir.

Pi networke bağlandığında, statik IP alması için /etc/network/interfaces dosyasında değişiklik yapılmalıdır.

    
    sudo cp etc/network/interfaces etc/network/interfaces.bak
    # dosya yedeklenir
    sudo gedit etc/network/interfaces
    # metin editörü ile interfaces dosyası açılır.


Dosyanın içeriği aşağıdaki içerik ile değiştirilir. Network gereksinimlerine göre IP adreslerinde değişiklikler yapılmalıdır.

    
    auto lo eth0
    iface default inet dhcp
    iface lo inet loopback
    iface eth0 inet static
    address 192.168.1.67 # istenen statik ip
    netmask 255.255.255.0
    gateway 192.168.1.1


Artık Pi boot edildiğinde verilen statik ip ile networke bağlanacaktır.

SSH Raspbian içerisinde aktifleştirilmiş olarak bulunuyor ancak bir takım konfigürasyonlar yapmak gerekmekte. Bunun için bash'te çalışacak komutlar yazmak mümkün. [Bu çözüme  [stackexhange](http://raspberrypi.stackexchange.com/questions/4444/enabling-ssh-on-rpi-without-screen-keystrokes-for-raspi-config#answer-8083)'de [nortally](http://raspberrypi.stackexchange.com/users/8114/nortally) tarafından yazılımış bir cevap ile ulaşmıştım.]

/etc dizininde bayrak niteliğinde bir dosya eklenir:

    
    sudo touch etc/SSHFLAG



    
    sudo gedit etc/rc.local       # metin editöründe dosya açılır.


Editörde:

    
    <code>if [ -e /etc/SSHFLAG ]; then
      /usr/sbin/update-rc.d -f ssh defaults
      /bin/rm /etc/SSHFLAG
      /sbin/shutdown -r now
    fi
    </code>


kod parçası `exit0` komutunun hemen üstüne eklenir. Bu sayede Pi boot edildiğinde /etc dizininde SSHFLAG dosyası var mı diye bakar ve varsa ssh konfigurasyonlarını yapacak olan komutu çalıştırır. Bu komut ssh public key'lerini oluşturup ssh bağlantısının sağlanabileceği zemini hazırlar. Bundan sonra da SSHFLAG dosyasını dizinden siler ve sistemi yeniden başlatır. Daha sonraki bootlarda bu kısım çalışmaz.

Artık Pi'a SSH ile erişip login olunabilir, VNC kurularak uzak masaüstü kullanılabilir.

SSH bağlantısı için:

    
    <code>ssh pi@192.168.1.67 --p</code>
    password: raspberry
