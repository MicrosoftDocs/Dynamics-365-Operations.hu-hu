---
title: Csempelista modul
description: Ez a témakör ismerteti a csempelista modulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.
author: anupamar-ms
ms.date: 07/08/2021
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
ms.openlocfilehash: 513775afe325008ebd6cd18d2d9485a972984090da3803d255a1584b16b1e014
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767851"
---
# <a name="tile-list-module"></a>Csempelista modul

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti a csempelista modulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.

A csempelista modul egy forgótárban található csempék gyűjteménye. A termékkategóriák vagy termékmárka-kategóriák képekkel és szövegekkel való piaci népszerűsítésére használatos. Egy kiskereskedő például egy csempelista modult felvehet egy e-commerce webhely kezdőlapjára, hogy elősegítse a legfelső eladási kategóriákat.

A csempelista modul működése a tartalomkezelő rendszer (CMS) adatain alapul. Ez nem függ a Commerce központ más moduljaitól és adataitól. Az csempelista modul minden olyan webhelylapon elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, kategóriákat vagy márkákat).

Az alábbi ábra egy csempelista modul és csempemodulok példáját mutatja be egy Adventure Works webhely kezdőoldalán.

![Egy csempelista modul és csempemodulok példája egy Adventure Works webhely kezdőoldalán](./media/Tile_list.PNG)

> [!IMPORTANT]
> A csempelista modul a Dynamics 365 Commerce 10.0.20-es verziójának kiadásaként érhető el.
> A csempelista modult az Adventure Works téma mutatja be.

## <a name="tile-list-modules-and-themes"></a>Csempelista moduljai és témái

A csempelista modul különböző elrendezéseket és stílusokat támogathat egy téma alapján. Például az Adventure Works témában a csempék animációs effektet mutatnak, amikor az oldal felhasználója föléjük viszi az egérmutatót. Minden téma további tulajdonságokat tartalmazhat a csempelista és a csempemodulok számára. A témafejlesztők további oldalterveket építhetnek a csempelista és a csempemodulok számára.

## <a name="tile-list-module-properties"></a>Csempelista modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc       | Fejlécszöveg és fejléccímke | A csempelista modul szöveges fejléce. |

## <a name="tile-module-properties"></a>Csempelista modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Kép         | Képfájl | Egy kép használható a termék vagy kategória bemutatásához. A kép feltölthető a Commerce webhelykészítő médiatárába, de meglévő kép is használható. |
| Fejléc       | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Alapértelmezés szerint a **H2** fejléccímke használatos a fejlécekhez, de a címke az akadálymentességi követelményeknek megfelelően módosítható. |
| Bekezdés     | Bekezdés szövege | A modul támogatja a rich text formátumú bekezdésszöveget. A rendszer támogat néhány alapvető rich text képességet támogat, például a hiperhivatkozásokat, valamint a félkövér, az aláhúzott és a dőlt szövegformázást. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás          | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** | A modulok egy vagy több „cselekvésre való felhívás” hivatkozást támogatnak. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA-címkéknek az akadálymentességi követelmények kielégítése érdekében leíró jellegűnek kell lenniük. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |
| Csempehivatkozás     | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** kiválasztó | Ez a tulajdonság a „hívás művelethez” hivatkozás meghatározására használható. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA-címkéknek az akadálymentességi követelmények kielégítése érdekében leíró jellegűnek kell lenniük. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva.|
| Ikon          | Kép | A termék vagy kategória képén kívül egy ikonszimbólum is hozzáadható. Az ikon szimbólum képe jelenik meg a termék vagy a kategória képe felett. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Csempelista modul hozzáadása egy új oldalhoz

A csempelista modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lapot, és nyissa meg a webhely kezdőlapjának marketingsablonját (vagy hozzon létre új marketingsablont).
1. Az Alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Csempelista** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Nyissa meg az **Oldalak** területet, majd a webhely kezdőlapját (vagy hozzon létre egy új kezdőlapot a marketingsablon használatával).
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Csempelista** modult, majd kattintson az **OK** gombra.
1. A csempelista modul tulajdonságlapján adjon hozzá egy fejlécet.
1. A **Csempelista** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Csempelista modul** modult, majd kattintson az **OK** gombra.
1. A csempemodul tulajdonságablakában adjon hozzá egy képet, egy fejlécet és egy ikonszimbólum-képet.
1. Szükség szerint adja hozzá és konfigurálja a további csempemodulokat.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Adventure Works téma](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
