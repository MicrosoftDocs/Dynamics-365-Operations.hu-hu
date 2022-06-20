---
title: Iframe modul
description: Ez a témakör a keretmodult tartalmazza, és bemutatja, hogyan lehet a webhely lapjaihoz hozzáadni Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e9f1804cde1010c585d53d63bc0a487bc5407552
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858937"
---
# <a name="iframe-module"></a>Iframe modul

[!include [banner](includes/banner.md)]

Ez a témakör a keretmodult tartalmazza, és bemutatja, hogyan lehet a webhely lapjaihoz hozzáadni Microsoft Dynamics 365 Commerce.

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
1. Az Új **sablon párbeszédpanel** Sablon neve területén **adja** meg a **Marketingsablont**, majd válassza az **OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új lap **létrehozása párbeszédpanel** Lap neve **területén** **adja meg a Marketing** lapot, majd válassza a Tovább **gombra.**
1. A **Sablon kiválasztása mezőben válassza** ki **a létrehozott marketingsablont**, majd válassza a Tovább **gombra**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**. 
1. Az új **lap főbejáratában** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a keretmodult**, majd válassza az **OK gombra**.
1. A modul tulajdonságai ablakban állítsa be a **Cél URL-cím** értékét egy külső URL-címre a videóhoz.
1. Szükség szerint egyéb tulajdonságokat is megadhat, például **Fejlécet** és **Magasságot**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Menjen a webhely marketing oldalára. Látnia kell, hogy a videó át lett renderelve az iFrame modulba.

> [!NOTE]
> Mivel a keretmodul külső tartalmat is lehetővé tesz, a webhely házirendnek gondoskodnia kell arról, hogy a keretmodulon belül tárolt tartalom ne sérti meg a tartalomkorlátozási házirendet az adott piacon. Ha a keretmodult használó lapon tartalom-megsértés történik, akkor a webhely szerzője eltávolíthatja a keretmodult, ha megnyitja az oldalt a webhelyszerkesztőben, **kiválasztja** a Modul eltávolítása gombra a keretmodulban, majd menti és újra közzéteszi az oldalt.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
