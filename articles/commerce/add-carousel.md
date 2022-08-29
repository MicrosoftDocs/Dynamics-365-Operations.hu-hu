---
title: Forgótármodul
description: Ez a témakör a carousel modulokat tartalmazza, és bemutatja, hogyan lehet őket a laphoz adni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 8bf9f7294dfbb4e16814dbdfb27bf646fcb5f4b1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275827"
---
# <a name="carousel-module"></a>Forgótármodul

[!include [banner](includes/banner.md)]

Ez a témakör a carousel modulokat tartalmazza, és bemutatja, hogyan lehet őket a laphoz adni Microsoft Dynamics 365 Commerce.

A forgótármodul több, a felhasználók által böngészhető promóciós elem (például multimédiás képek) forgótár-szalagcímben való elhelyezésére használható. Például egy kiskereskedő a kezdőlapon a forgótármodul segítségével több új terméket vagy promóciót mutathat be.

A forgótármodulon belül tartalomblokk-modulokat adhat hozzá. A forgótármodul tulajdonságai határozzák meg a modulok megjelenítésének módját.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Példák az e-Commerce forgótármoduljaira

- A több promóciós modult tartalmazó forgótár használható a kezdőlapon.
- A több promóciós modult tartalmazó forgótár használható a termék részletes lapján.
- A körhinta bármilyen marketinglapon több promóció vagy termék népszerűsítésére.

A következő kép egy kezdőoldalon használt forgótár modul egy példáját jeleníti meg. Ez a forgótár modul több tartalomblokk elemet tartalmaz.

![Példa egy forgótármodulra.](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Forgótármodul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Automatikus lejátszás                  | **Igaz** vagy **Hamis** | Ha az érték **Igaz**, akkor a forgótár elemei közötti váltás automatikus. Ha az érték **Hamis**, csak akkor történik váltás, ha a vevő a billentyűzet vagy az egér segítségével az egyik elemről a másikra vált. |
| Áttűnési időköz | Egy érték másodpercben    | Az elemek közötti váltások intervalluma. |
| Áttűnés típusa           | **Csúszás** vagy **Elhalványulás** | A cikkek közötti áttűnési effektus. |
| Forgótárlapozó elrejtése     | **Igaz** vagy **Hamis** | Ha az érték beállítása **Igaz**, a forgótár-kapcsoló és a sorozatjelző el van rejtve. |
| Forgótár-elutasítás engedélyezése    | **Igaz** vagy **Hamis** | Ha az érték **Igaz**, akkor a felhasználó elvetheti a forgótárat. |

## <a name="add-a-carousel-module-to-a-page"></a>Forgótármodul felvétele egy oldalra

A forgótármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Forgótársablon** elemet, majd válassza az **OK** gombot.
1. Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.  
1. A most létrehozott forgótársablon használatával hozzon létre egy **Forgótárlap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy tárolómodult. 
1. A jobb oldali ablaktáblában adja meg a **Kitöltési képernyő** **Szélesség** értékét.
1. A **Lap körvonala** területen vegyen fel egy forgótár modult a tároló modulba.
1. Vegyen fel egy tartalomblokkmodult a forgótármodulba. Állítsa be a tartalomblokkmodul tulajdonságait a **Címsor**, a **Hivatkozás**, az **Elrendezés** és más tulajdonságok megadásával.
1. Adjon hozzá és konfiguráljon egy másik tartalomblokkmodult.
1. Szükség szerint beállíthat további tulajdonságokat a forgótármodulhoz.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A lapnak egy olyan forgótárat kell megjelenítenie, amely két modult tartalmaz (egy főképmodul és egy funkciómodul). A kívánt hatás elérése érdekében módosíthatja a forgótár-, a főkép- és a funkciómodulok további tulajdonságait.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Szövegterület-modul](add-content-rich-block.md)

[Tartalomblokk-modul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
