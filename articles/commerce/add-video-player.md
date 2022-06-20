---
title: Videólejátszó-modul
description: Ez a témakör a Video Player modulokat ismerteti, és bemutatja, hogyan lehet őket a Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 20d516c58bf619065d57b27bc5a614eb7bd4cea9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873436"
---
# <a name="video-player-module"></a>Videólejátszó-modul

[!include [banner](includes/banner.md)]

Ez a témakör a Video Player modulokat ismerteti, és bemutatja, hogyan lehet őket a Microsoft Dynamics 365 Commerce.

A videólejátszó modul a videólejátszás támogatására szolgál. A tartalmat bármilyen oldalra felveheti, feltéve, hogy a videotartalom feltöltése a tartalomkezelő rendszerben (CMS) történik. A videolejátszó modul támogatja az .mp4 média típusát.

## <a name="video-player-module"></a>Videólejátszó modul

A videólejátszó modul egy e-kereskedelmi webhelyről származó videók bemutatására használható. Támogatja az összes lejátszási funkciót, például a lejátszást, szüneteltetést, teljes méretű módot, audioleírásokat és a feliratokat. A videólejátszó modul a Microsoft akadálymentesítési szabványoknak való megfelelés érdekében támogatja a feliratok testreszabását is. Testreszabhatja például a betűméretet és a háttérszínt.

A videólejátszó modul támogatja a másodlagos hangsávot is. Videó CMS-be való feltöltése esetén másodlagos hangsávot is fel lehet tölteni. A videólejátszó modul lejátszhatja a másodlagos hangsávot, ha a felhasználó kiválasztja azt.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Példák az e-kereskedelem videólejátszó moduljaira

- Tájékoztató videók a termék részletes lapjain vagy marketinglapjain
- Promóciós videók vagy irányelvekkel kapcsolatos videók bármelyik marketinglapon
- A termék jellemzőit bemutató marketingvideók a termék részletes lapjain vagy marketinglapokon

A következő kép egy kezdőoldalon használt videólejátszó modul egy példáját jeleníti meg.

![Példa a videólejátszó modulra.](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Videólejátszó modul tulajdonságai

| Tulajdonság neve         | Érték                               | Leírás |
|-----------------------|-------------------------------------|-------------|
| Fejléc               | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Alapértelmezés szerint a **H2** fejléccímke használatos a fejlécekhez, de a címke az akadálymentességi követelményeknek megfelelően módosítható. |
| Rich Text             | Bekezdés szövege | A modul támogatja a rich text formátumú bekezdésszöveget. A rendszer támogat néhány alapvető rich text képességet támogat, például a hiperhivatkozásokat, valamint a félkövér, az aláhúzott és a dőlt szövegformázást. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás                  | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** választó | A modul egy vagy több „cselekvésre való felhívás” hivatkozást támogat. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA-címkéknek az akadálymentességi követelmények kielégítése érdekében leíró jellegűnek kell lenniük. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |
| Alszöveg              | Fejléc, szöveg vagy hivatkozások | A videólejátszó modulhoz további környezet is hozzáadható, például egy szerző vagy egy tervező neve, illetve egy személyes blogra mutató hivatkozások. |
| Automatikus lejátszás             | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program automatikusan lejátssza a videót. |
| Elnémítás                  | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a hang le van némítva. Ennél a lejátszónál az alapértelmezett érték **Hamis**. A Chrome böngészőben alapértelmezés szerint az automatikusan lejátszott videók némítva vannak, és a hang lejátszása csak akkor történik meg, ha a felhasználó manuálisan játssza le a videót. |
| Ciklus                  | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program a videót ismétlődő hurokban játssza le. |
| Média                 | Videófájl elérési útja és neve | A videólejátszó által lejátszott videófájl. |
| Teljes képernyős lejátszás       | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program a videót teljes képernyős üzemmódban játssza le. |
| Lejátszás/szüneteltetés eseményindítója    | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van állítva, akkor egy lejátszás/szünet gomb jelenik meg a videón. |
| Videolejátszó vezérlői | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor az összes videolejátszó-vezérlő látható. Ezek közé a vezérlőelemek közé tartozik a lejátszás és szünet gomb, a folyamatjelző és a feliratbeállítások. |
| Plakátkép elrejtése     | **Igaz** vagy **Hamis**               | A videó poszterkerettel jelenhet meg. Ha a tulajdonság értéke **Igaz**, akkor a program elrejti a poszterkeretet. |
| Maszk szintje            | **0** és **100** közötti szám | A stílus módosításához a videóra alkalmazott maszk. |

> [!IMPORTANT]
> A **Címsor**, a **Rich Text**, a **Hivatkozás** és az **Alszöveg** tulajdonságok a Dynamics 365 Commerce 10.0.20-as verziójában érhetők el.

## <a name="add-a-video-player-module-to-a-page"></a>Videólejátszó modul hozzáadása egy laphoz

> [!NOTE] 
> A videolejátszó modul létrehozása előtt fel kell töltenie egy videót a médiatárba.

A videólejátszó modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az Új sablon **párbeszédpanel** Sablonnév listájában **adja** meg **a Video Player** sablonját, majd válassza az **OK gombra**.
1. Válassza ki a **három** pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget** a Törzsnél.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az Alapértelmezett** lap modult, majd kattintson az **OK gombra**.
1. Az Alapértelmezett **lap** modul főbejáratában **válassza** ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Video Player** modult, majd válassza az **OK gombra.**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új oldal **létrehozása párbeszédpanel** **Lap neve** csoportban adja **meg a Video Player** lapját, majd válassza **a Tovább gombra.**
1. A **Sablon kiválasztása mezőben válassza** **ki a Létrehozott Video Player-sablont**, majd válassza **a Tovább lehetőséget**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**.
1. Az új **lap főbejáratában** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Video Player** modult, majd válassza az **OK gombra.**
1. A videolejátszó modul tulajdonságlapján válassza a **Videó hozzáadása** elemet.
1. A **Médiaválasztó** párbeszédablakon válasszon egy videót, majd válassza az **Új médiaelem feltöltése** elemet.
1. A Fájlkezelő területen jelöljön ki egy vagy videófájlt, majd válassza a **Megnyitás** lehetőséget.
1. A **Mediaelem feltöltése** párbeszédpanelen írjon be egy címet és egyéb adatokat, majd kattintson az **OK** gombra.
1. A **Médiaválasztó** párbeszédpanelen válassza a **Bezárás** elemet.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A lapon a videómodulnak látszania kell. A további beállítások módosításával testreszabhatja a modul viselkedését.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Szövegterület-modul](add-content-rich-block.md)

[Tartalomblokk modul](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
