---
title: iFrame modul
description: Ez a témakör az iFrame modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 570901e3afca82abd21172df4c0b6fc575b57262f2b5d1decad11cabc00db31d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767290"
---
# <a name="iframe-module"></a>iFrame modul

[!include [banner](includes/banner.md)]

Ez a témakör az iFrame modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

Az iFrame modul egy iFrame (szövegközi keretet), amely külső tartalmat tárol a webhelyen. Felhasználható például YouTube-videó vagy PDF-megjelenítő tárolására bármilyen webhelyen. 

Az iFrame modulhoz cél URL-cím szükséges. Ezt követően egy HTML **iFrame** elemen belül tárolja a céloldal tartalmát. A külső URL-címeknek a webhely tartalmi biztonsági házirendjével (CSP) kapcsolatos határozatok engedélyezett elemek listáján kell szerepelniük. Az iFrame-tartalom esetében az URL-címeket a **keret -elődelem** utasítással kell engedélyezni. További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md).

> [!NOTE]
> Az iFrame modul a Dynamics 365 Commerce 10.0.13-as verziójában érhető el.

A következő kép példákat mutat be azokról az iFrame modulokról, amelyek külső videókat mutatnak be meg a webhely oldalain.

![Példa a külső videókat bemutató iFrame modulokról.](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>iFrame modul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Címsor | Szöveg | A modul címe. |
| Célként megadott URL-cím | URL-cím | A modulban tárolt URL-cím. |
| Magasság | Szám vagy százalék | A modul magassága képpontban vagy százalékban kifejezve. Például a **100** értéket a program képpontértékként kezeli, és a **100%** értéket százalékként. |
| Akadálymentességi címke | Szöveg | Az Akadálymentes dinamikus webes alkalmazások (ARIA) címkét meg lehet határozni hozzáférhetőségi célokra. |

## <a name="add-an-iframe-module-to-a-page"></a>iFrame modul felvétele egy oldalra

Ha fel szeretne venni egy iFrame modult egy oldalra egy külső videó bemutatásához, akkor kövesse az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Marketingsablon** elemet, majd válassza az **OK** gombot.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Marketingsablon** sablonját. Az **Oldal neve** alatta adja meg a **Marketing oldalt**, majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **iFrame** modult, majd kattintson az **OK** gombra.
1. A modul tulajdonságai ablakban állítsa be a **Cél URL-cím** értékét egy külső URL-címre a videóhoz.
1. Szükség szerint egyéb tulajdonságokat is megadhat, például **Fejlécet** és **Magasságot**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Menjen a webhely marketing oldalára. Látnia kell, hogy a videó át lett renderelve az iFrame modulba.
 
## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]