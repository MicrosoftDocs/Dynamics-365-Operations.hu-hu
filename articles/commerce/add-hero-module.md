---
title: Főképmodul
description: Ez a témakör a főképmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785391"
---
# <a name="hero-module"></a>Főképmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a főképmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A főképmodul a termékek és a promóciók képek és szövegek kombinálásával történő forgalmazására szolgál. Például egy kiskereskedő felveheti a főképmodult egy e-kereskedelmi webhely kezdőlapjára egy új termék népszerűsítése céljából, és a vevők figyelmének felkeltéséhez.

A főképmodul működése a tartalomkezelő rendszer (CMS) adatain alapul. Ez egy önálló modul, amely nem függ a lap egyéb moduljaitól. A főképmodul a webhely bármely olyan lapján elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, akciókat vagy szolgáltatásokat).

## <a name="examples-of-hero-module-in-e-commerce"></a>Példák az e-Commerce főképmoduljára

- A főképmodul az e-kereskedelmi webhely kezdőlapján a promóciók és az új termékek kiemelésére használható.
- A termék részletes lapján a főképmodul a termék adatainak megjelenítésére használható.
- Egy forgótármodulban több főképmodult lehet elhelyezni több termék vagy promóció kiemeléséhez.

## <a name="hero-module-properties"></a>Főképmodul tulajdonságai

| Tulajdonság neve  | Értékek | Leírás |
|----------------|--------|-------------|
| Kép          | Képfájl | Egy kép használható a termék vagy promóció bemutatásához. Egy képet lehet feltölteni a képtárba, vagy egy létező kép használható. |
| Címsor        | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Minden főképmodulhoz tartozhat fejléc. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Bekezdés      | Bekezdés szövege | A főképmodulok támogatják a rich text formátumú bekezdésszövegeket. A program néhány alapvető multimédiás szöveg képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg, valamint a hiperhivatkozások. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás           | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** | A főképmodulok egy vagy több „cselekvésre való felhívás” hivatkozást támogatnak. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA címkéknek az akadálymentességi követelmények kielégítése érdekében leírónak kell lennie. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |
| Szöveg elhelyezése | **Bal oldalt felül**, **Jobb oldalt felül**, **Középen fent**, **Bal oldalt alul**, **Jobb oldalt alul**, **Középen alul**, **Bal oldalt középen**, **Jobb oldalt középen** vagy **Középen középen** | Ez a tulajdonság határozza meg a kép szöveghez viszonyított pozícióját. Ha például a **Jobbra** beállítás van kiválasztva, a kép a szövegtől jobbra jelenik meg. |
| Szöveg témája     | **Világos** vagy **Sötét** | A szöveg számára a háttérkép alapján egy színséma adható meg. Ha például a kép sötét háttérrel rendelkezik, akkor egy világos téma alkalmazható a szöveg láthatóbbá tételére és a színkontraszt arányára vonatkozó akadálymentességi követelmények teljesítéséhez. |
| Színátmenet       | **Igaz** vagy **Hamis** | A képhez színátmenetet lehet alkalmazni a színkontraszt arányának akadálymentességi célból történő javításához. |

## <a name="add-a-hero-module-to-a-new-page"></a>Főképmodul hozzáadása egy új oldalhoz

A főképmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lehetőséget, és hozzon létre egy **főképsablon** nevű sablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy főképmodult.
1. Adja be a sablont és tegye közzé.
1. A most létrehozott főképsablon használatával hozzon létre egy **főképlap** nevű lapot.
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen a **Modulok kiválasztása** alatt válassza ki a főképmodult, majd kattintson az **OK** gombra.
1. A bal oldali fastruktúrán válassza ki a főképmodult.
1. A jobb oldali tulajdonságok panelen válassza a **Kép hozzáadása** lehetőséget. Ezt követően válasszon ki egy meglévő képet, vagy töltsön fel egy új képet.
1. Válassza ki a **Fejléc** elemet.
1. A **Fejléc** párbeszédpanelen adja meg a fejléc szövegét, válassza ki a címsor szintjét, majd kattintson az **OK** gombra.
1. A **Rich text** alatt írja be a szükséges szöveget.
1. Válassza a **Művelethivatkozás hozzáadása** lehetőséget.
1. A **Művelethivatkozás** párbeszédpanelen adja meg a hivatkozás szövegét, a hivatkozás URL-címét és a hivatkozáshoz tartozó ARIA címkét, majd kattintson az **OK** gombra.
1. Mentse a lapot, és tekintse meg a módosítások előnézetét.
1. Adja be a lapot, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Figyelmeztetési modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Funkciómodul](add-feature-module.md)

[Videólejátszó modul](add-video-player.md)
