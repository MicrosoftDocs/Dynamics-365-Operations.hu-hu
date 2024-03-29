---
title: Tartalomblokk-modul
description: Ez a témakör a tartalomblokkmodulokat ismerteti, és bemutatja, hogyan lehet őket a webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.openlocfilehash: dc6d728f49befd0c156340379dba05f592ca7919
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277000"
---
# <a name="content-block-module"></a>Tartalomblokk-modul

[!include [banner](includes/banner.md)]

Ez a témakör a tartalomblokkmodulokat ismerteti, és bemutatja, hogyan lehet őket a webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.

A tartalomblokkmodul a termékek és a promóciók képek és szövegek kombinálásával történő reklámozására szolgál. Például egy kiskereskedő felveheti a tartalomblokkmodult egy e-kereskedelmi webhely kezdőlapjára egy új termék népszerűsítése céljából, és a vevők figyelmének felkeltéséhez.

A tartalomblokkmodul működése a tartalomkezelő rendszer (CMS) adatain alapul. Ez egy önálló modul, amely nem függ a lap egyéb moduljaitól. A tartalomblokkmodul a webhely bármely olyan lapján elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, akciókat vagy szolgáltatásokat).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Példák az e-Commerce tartalomblokkmoduljaira

- A tartalomblokkmodul az e-kereskedelmi webhely kezdőlapján a promóciók és az új termékek kiemelésére használható.
- A termék részletes lapján a tartalomblokkmodul a termék adatainak megjelenítésére használható.
- Egy forgótármodulban több tartalomblokkmodult lehet elhelyezni több termék vagy promóció kiemeléséhez.

## <a name="content-block-modules-and-themes"></a>A tartalomblokkmodulok és témák

A tartalomblokkmodulok különböző elrendezéseket és stílusokat támogatnak egy téma alapján. Például a Fabrikam téma 3 elrendezésváltozatot támogat a tartalomblokkmoduloknál: főkép, funkció és csempe. A főképelrendezés egy képet jelenít meg a háttérben a szöveg átfedésével. A funkcióelrendezés egy képet és egy szöveget jelenít meg egymás mellett. A csempeelrendezés a csempeformátumában több tartalmat is megenged.

Ezenkívül a téma különböző tulajdonságokat is felfedhet az egyes elrendezésekhez. A téma fejlesztői több stílussal készíthetnek további elrendezéseket a tartalomblokkmodul segítségével.

A következő kép egy főkép elrendezésű tartalomblokkmodul példáját jeleníti meg.

![Példa egy főkép modulra.](./media/Hero.PNG)

A következő kép egy funkció elrendezésű tartalomblokkmodul példáját jeleníti meg.

![Példák a funkciómodulokra.](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>tartalomblokkmodul tulajdonságai

| Tulajdonság neve  | Értékek | Leírás |
|----------------|--------|-------------|
| Kép          | Képfájl | Egy kép használható a termék vagy promóció bemutatásához. Egy képet lehet feltölteni a képtárba, vagy egy létező kép használható. |
| Címsor        | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Minden főképmodulhoz tartozhat fejléc. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Bekezdés      | Bekezdés szövege | A főképmodulok támogatják a rich text formátumú bekezdésszövegeket. A program néhány alapvető multimédiás szöveg képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg, valamint a hiperhivatkozások. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás           | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** | A főképmodulok egy vagy több „cselekvésre való felhívás” hivatkozást támogatnak. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA címkéknek az akadálymentességi követelmények kielégítése érdekében leírónak kell lennie. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>A tartalomblokkmodul tulajdonságok a Fabrikam téma által felfedve 

| Tulajdonság neve  | Értékek | Leírás |
|----------------|--------|-------------|
| Szöveg elhelyezése | **Bal**, **Jobb**, **Közép** | Ez a tulajdonság határozza meg a szöveg pozícióját a képen. Csak a főkép elrendezésére vonatkozik. |
| Szöveg témája     | **Világos** vagy **Sötét** | A szöveg számára a háttérkép alapján egy színséma adható meg. Ha például a kép sötét háttérrel rendelkezik, akkor egy világos téma alkalmazható a szöveg láthatóbbá tételére és a színkontraszt arányára vonatkozó akadálymentességi követelmények teljesítéséhez. Csak a főkép elrendezésére vonatkozik.|
| Kép elhelyezése       | **Bal**, **jobb** | Ez a tulajdonság azt határozza meg, hogy a képnek a szöveg bal vagy jobb oldalán kell lennie. Csak a funkció elrendezésére vonatkozik.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Tartalomblokkmodul hozzáadása új laphoz

A főképmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lehetőséget, és hozzon létre egy **Tartalomblokk-sablon** nevű sablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy főképmodult.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. A most létrehozott főképsablon használatával hozzon létre egy **Tartalomblokk oldala** nevű lapot.
1. Az alapértelmezett **oldal** főbejáratában jelölje ki az három pont gombot (**...**), majd válassza **a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki az modult, majd válassza az **OK gombra**.
1. A bal oldali fastruktúrán válassza ki a tartalomblokkmodult.
1. A jobb oldali tulajdonságok panelen válassza a **Kép hozzáadása** lehetőséget. Ezt követően válasszon ki egy meglévő képet, vagy töltsön fel egy új képet.
1. Válassza ki a **Fejléc** elemet.
1. A **Fejléc** párbeszédpanelen adja meg a fejléc szövegét, válassza ki a címsor szintjét, majd kattintson az **OK** gombra.
1. A **Rich text** alatt írja be a szükséges szöveget.
1. Válassza a **Hivatkozás hozzáadása** lehetőséget.
1. A **Hivatkozás** párbeszédpanelen adja meg a hivatkozás szövegét, a hivatkozás URL-címét és a hivatkozáshoz tartozó ARIA címkét, majd kattintson az **OK** gombra.
1. Válassza ki a **Főkép** elrendezést.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Szövegterület-modul](add-content-rich-block.md)

[Videólejátszó modul](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
