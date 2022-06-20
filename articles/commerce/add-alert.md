---
title: Promóciós szalagcím modul
description: Ez a témakör a promóció modulokról és a webhelyoldalakhoz való hozzáadásukról ad le Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b85465ec0bc96e7e6f413fcae23950c3da2b99cd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862098"
---
# <a name="promo-banner-module"></a>Promóciós szalagcím modul

[!include [banner](includes/banner.md)]

Ez a témakör a promóció modulokról és a webhelyoldalakhoz való hozzáadásukról ad le Microsoft Dynamics 365 Commerce.

A promóciós szalagcím modulok a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál. Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni. 

A promóciós szalagcím modulok szöveges üzenetet és egy hivatkozást támogatnak. Ha egy promóciós banner modulhoz több üzenetet ad, akkor egy olyan forgótár-szalagcím lesz, amely segítségével az ügyfelek végigpörgethetik az összes üzenetet. 

A promóciós szalagcím modulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Példa az e-kereskedelmi promóciós szalagcím használatára

A webhely fejlécében a promóciós szalagcímeket a webhely egészére kiterjedő promóciók és üzenetek megjelenítésére lehet használni, ahogy az alábbi példákban is.

„Az éves akció 10 napon belül lejár”

„Nagy megtakarítás az iskolakezdő akcióval. Vásároljon most.”

"Vásároljon Karácsonyra AKCIÓ!" 

A következő kép egy promóciós bannert mutat be.

![Példa egy promóciósbanner-modulra.](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Promóciós szalagcím modul tulajdonságai

| Tulajdonság neve             | Érték                              | Leírás |
|---------------------------|------------------------------------|-------------|
| Szalagüzenetek           | Szöveg és hivatkozások                     | Szövegből és hivatkozásokból álló tömb. |
| Automatikus lejátszás                  | **Igaz** vagy **Hamis**              | Olyan érték, amely jelzi, hogy az üzenetek automatikusan körbemennek-e, ha több üzenet van konfigurálva. |
| Diák áttűnési időköze | Ezredmásodpercek száma (ms)      | Az üzenetek átváltására használt időtartam. |
| Elvetés engedélyezése             | **Igaz** vagy **Hamis**              | Ha az érték **Igaz**, akkor az ügyfelek elvetheti a figyelmeztetést. |
| Forgótár-váltó megjelenítése     | **Igaz** vagy **Hamis**              | Olyan érték, amely azt jelzi, hogy a körhintaváltók megjelenjenek-e, így a vevők több manuálisan váltogathatnak több szalagcímelem között. |
| Szöveg igazítása            | **Jobb**, **Bal** vagy **Közép** | A promóciós szalagcím modul szövegének igazítása. |
| Összekapcsolás                      | Egy URL-cím                              | Az opcionális hivatkozás URL-címe. |
|Szöveg igazítása             | **Jobb**, **Bal** vagy **Közép** | Ez a tulajdonság témabővítményként áll rendelkezésre az Adventure Works témához. Lehetővé teszi a felhasználó számára a szöveg igazítását a promóciós bannerben. |

> [!IMPORTANT]
> Az Adventure Works téma a Dynamics 365 Commerce 10.0.20-as kiadásában érhető el.

## <a name="add-a-promo-banner-module-to-a-page"></a>Promóciós szalagcím modul hozzáadása a laphoz 

A promóciós szalagcím modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Adja meg **a Promóciós sablon sablonját az Új sablon** párbeszédpanel Sablon **neve** **listájában**, majd **válassza az OK kódot**.
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
