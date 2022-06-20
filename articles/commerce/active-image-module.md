---
title: Aktívképmodul
description: Ez a témakör az aktív képmodulokat tartalmazza, és bemutatja, hogyan lehet őket a webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3d532d21f847a80a16af814eeaf097a616605795
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853850"
---
# <a name="active-image-module"></a>Aktívképmodul

[!include [banner](includes/banner.md)]

Ez a témakör az aktív képmodulokat tartalmazza, és bemutatja, hogyan lehet őket a webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.

Az aktívképmodulok segítségével termékcímkéket lehet beágyazni egy képbe. Az e-kereskedelmi webhely felhasználói ezután az egérrel a címkékre mutatva megtekinthetik a képen megjelenő termékek előnézetét. Az előnézetek előugró ablakban jelennek meg. Ha egy előugró ablakot választ ki, akkor a felhasználók közvetlenül a megfelelő termék részletező oldalára (PDP) tudnak ugrani.

A címkék a kép X és Y koordinátái alapján vannak meghatározva. Minden felcímkézett pontot a képen megjelenő termék azonosítójával kell konfigurálni.

A következő ábra egy előnézeti előugró ablakra mutat be példát, amely egy Adventure Works kezdőlap főképénél jelenik meg.

![Példa egy előnézeti előugró ablakra egy aktívképmodulban](./media/Active_image.PNG)

> [!IMPORTANT]
> - Az aktívképmodul a Dynamics 365 Commerce 10.0.20-as kiadásában áll rendelkezésre.
> - Az aktívképmodult az Adventure Works témában mutatjuk be.

## <a name="active-image-module-properties"></a>Az aktívképmodul tulajdonságai

| Tulajdonság neve      | Értékek | Leírás |
|--------------------|--------|-------------|
| Kép              | Képfájl | Egy kép használatával egy vagy több terméket is be lehet mutatni. A kép feltölthető a Commerce webhelykészítő médiatárába, de meglévő kép is használható. |
| Szélesség              | Képpontok száma | Ez a tulajdonság határozza meg a kép szélességét. Az aktív koordináták kiszámítása a kép szélessége alapján történik.|
| Aktív koordináták | X és Y koordináták, valamint egy termékazonosító szám | Minden aktív képtömb X és Y koordinátákból, valamint egy termékazonosító számból áll.|
| Fejléc            | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Alapértelmezés szerint a **H2** fejléccímke használatos a fejlécekhez, de a címke az akadálymentességi követelményeknek megfelelően módosítható. |
| Bekezdés          | Bekezdés szövege | A modul támogatja a rich text formátumú bekezdésszöveget. A rendszer támogat néhány alapvető rich text képességet támogat, például a hiperhivatkozásokat, valamint a félkövér, az aláhúzott és a dőlt szövegformázást. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás               | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** választó | A modul egy vagy több „cselekvésre való felhívás” hivatkozást támogat. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA-címkéknek az akadálymentességi követelmények kielégítése érdekében leíró jellegűnek kell lenniük. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |
| Alszöveg           | Fejléc, szöveg és hivatkozások | A képhez további környezet is hozzáadható, például egy szerző vagy egy tervező neve, illetve egy személyes blogra mutató hivatkozások.|
| Szöveg témája         | **Világos** vagy **Sötét** | Ez a tulajdonság lehetővé teszi a felhasználó számára a világos vagy sötét szöveg beállítását a háttérkép alapján. Témabővítményként áll rendelkezésre az Adventure Works témához. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Aktívképmodul hozzáadása egy új oldalhoz

Az aktívképmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lapot, és nyissa meg a webhely kezdőlapjának marketingsablonját (vagy hozzon létre új marketingsablont).
1. Az alapértelmezett **oldal** főbejáratában válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az Aktív képmodult**, majd válassza az **OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Nyissa meg az **Oldalak** területet, majd a webhely kezdőlapját (vagy hozzon létre egy új kezdőlapot a marketingsablon használatával).
1. Az alapértelmezett **oldal** főbejáratában jelölje ki az három pont gombot (**...**), majd válassza **a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az Aktív képmodult**, majd válassza az **OK gombra**.
1. Az aktívképmodul tulajdonságpanelén adjon hozzá egy képet, és állítsa a vászon szélességét a kép méretének megfelelően.
1. Állítsa be az X és az Y koordinátát, és adja hozzá a megfelelő termékazonosító számot.
1. Szükség szerint adjon hozzá és konfiguráljon további aktívképmodulokat.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Adventure Works téma](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
