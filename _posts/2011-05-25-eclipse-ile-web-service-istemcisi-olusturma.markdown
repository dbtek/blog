---
author: dbtek
comments: true
date: 2011-05-25 18:48:51+00:00
layout: post
slug: eclipse-ile-web-service-istemcisi-olusturma
title: Eclipse ile Web Service İstemcisi Oluşturma
wordpress_id: 335
categories:
- Bilişim-Teknoloji
- Yazılım
tags:
- client
- eclipse
- istemci
- web service
---

Eclipse ile kolayca bir web service (wsdl) istemcisi (client) oluşturmak mümkün. Bunun için New Project -> Web Services -> Web Service Client seçtikten sonra gelen pencere içinde aşağıdaki resimde olduğu gibi Service Definition bölümüne web service wsdl adresi yazılır. Projede methodları test edebileceğiniz bir jsp sayfası olsun istiyorsanız sol alt bölümdeki scroll-bar'ı en üste çekin. Sonra server ayarlarını yaptıktan sonra finish butonuna tılayın.<!-- more -->

![](http://www.eclipse.org/webtools/jst/components/ws/1.5/tutorials/WebServiceClient/images/ClientWizard.png)

<!-- more -->

Bu adımdan sonra aşağıdaki resimdeki gibi web serviste bulunan metodları test edebileceğiniz bir jsp sayfası görülür. Bundan sonra ilgili metodlarınızı istediğiniz classta kullanabilirsiniz.

![](http://www.eclipse.org/webtools/jst/components/ws/1.5/tutorials/WebServiceClient/images/ClientJSP.png)
