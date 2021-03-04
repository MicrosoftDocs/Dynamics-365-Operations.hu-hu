---
title: Promóciós szalagcím modul
description: Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d9debd16b18300d090bde1862a16920d8e9185eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412777"
---
# <a name="promo-banner-module"></a>Promóciós szalagcím modul

[!include [banner](includes/banner.md)]

Ez a témakör a promóciós szalagcím modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A promóciós szalagcím modulok a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál. Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni. 

A promóciós szalagcím modulok szöveges üzenetet és egy hivatkozást támogatnak. Ha egy promóciós banner modulhoz több üzenetet ad, akkor egy olyan forgótár-szalagcím lesz, amely segítségével az ügyfelek végigpörgethetik az összes üzenetet. 

A promóciós szalagcím modulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Az e-kereskedelmi promóciós szalagcím használatára példa

A webhely fejlécében a promóciós szalagcímeket a webhely egészére kiterjedő promóciók és üzenetek megjelenítésére lehet használni, ahogy az alábbi példákban is.

„Az éves akció 10 napon belül lejár”

„Nagy megtakarítás az iskolakezdő akcióval. Vásároljon most.”

"Vásároljon Karácsonyra AKCIÓ!" 

A következő kép egy promóciós bannert mutat be.

![Példa egy promóciós banner modulra](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Promóciós szalagcím modul tulajdonságai

| Tulajdonság neve             | Érték                              | Leírás |
|---------------------------|------------------------------------|-------------|
| Szalagüzenetek           | Szöveg és hivatkozások                     | Szövegből és hivatkozásokból álló tömb. |
| Automatikus lejátszás                  | **Igaz** vagy **Hamis**              | Olyan érték, amely jelzi, hogy az üzenetek automatikusan körbemennek-e, ha több üzenet van konfigurálva. |
| Diák áttűnési időköze | Ezredmásodpercek száma (ms)      | Az üzenetek átváltására használt időtartam. |
| Elvetés engedélyezése             | **Igaz** vagy **Hamis**              | Ha az érték **Igaz**, akkor az ügyfelek elvetheti a figyelmeztetést. |
| Forgótár-váltó megjelenítése     | **Igaz** vagy **Hamis**              | Olyan érték, amely azt jelzi, hogy a körhintaváltók megjelenjenek-e, így a vevők több manuálisan váltogathatnak több szalagcímelem között. |
| Szöveg igazítása            | **Jobb**, **Bal** vagy **Közép** | A promóciós szalagcím modul szövegének igazítása. |
| Hivatkozás                      | Egy URL-cím                              | Az opcionális hivatkozás URL-címe. |

## <a name="add-a-promo-banner-module-to-a-page"></a>Promóciós szalagcím modul hozzáadása a laphoz 

A promóciós szalagcím modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **promóciós szalagcím sablon** elemet, majd válassza az **OK** gombot.
1. Az **Oldalstruktúra** területen vegyen fel egy **Alapértelmezett oldal** modult a **Szövegtörzs** helyre. 
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 
1. A most létrehozott sablon használatával hozzon létre egy **Promóciós szalagcím oldal** nevű lapot. 
1. Az új lap **Fő** helyén adjon hozzá egy tárolómodult. 
1. A jobb oldali ablaktáblában adja meg a **Tároló kitöltése** értékre a **Szélesség** beállítást.
1. A **Oldalstruktúra** területen vegyen fel egy promóciós szalagcím modult a tároló modulba.
1. A szalagcím modul beállításainál vegyen fel egy vagy több szalagcímüzenetet. Minden üzenethez hivatkozással együtt szöveg tartozhat. A további tulajdonságokat módosíthatja, ha a modult további személyre szabására van szükség.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A lap tetején egy olyan figyelmeztetés jelenik meg, amely az Ön által hozzáadott szöveget jeleníti meg.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

> [!NOTE]
> A promóciós szalagcím általában a lap fejlécének vagy egy alfejlécének helyén használatos.


## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Forgótármodul](add-carousel.md)

[Szövegterület-modul](add-content-rich-block.md)

[Tartalomblokk-modul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]