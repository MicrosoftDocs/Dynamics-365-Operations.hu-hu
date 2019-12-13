---
title: Funkciómodul
description: Ez a témakör a funkciómodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785284"
---
# <a name="feature-module"></a>Funkciómodul 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a funkciómodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A funkciómodul a termékek és a promóciók képek és szövegek kombinálásával történő forgalmazására szolgál. Például egy kiskereskedő hozzáadhat egy funkciómodult a termék részletes lapjához a termék funkcióinak kiemeléséhez.

A funkció modul működése a tartalomkezelő rendszer (CMS) adatain alapul. Ez egy önálló modul, amely nem függ a lap egyéb moduljaitól. A funkciómodul a webhely bármely olyan lapján elhelyezhető, ahol egy kiskereskedő értékesíteni vagy népszerűsíteni szeretne valamit (például termékeket, akciókat vagy szolgáltatásokat).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Példák az e-Commerce funkciómoduljaira

A következő lapokon használható a funkciómodul:

- A termék részletes lapja a termék funkcióinak bemutatására
- A termékek népszerűsítésére szolgáló kezdőlap.
- Kategória lap egy termékkategória kiemeléséhez

## <a name="feature-module-properties"></a>Funkciómodul tulajdonságai

| Tulajdonság neve     | Értékek | Leírás |
|-------------------|--------|-------------|
| Kép             | Képfájl | Egy kép használható a termék vagy promóció reklámozásához. Egy képet lehet feltölteni a képtárba, vagy egy létező kép használható. |
| Címsor           | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Minden funkciómodulhoz tartozhat fejléc. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Bekezdés         | Bekezdés szövege | A funkciómodulok támogatják a multimédiás szöveg formátumú bekezdésszövegeket. A program néhány alapvető multimédiás szöveg képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg, valamint a hiperhivatkozások. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Hivatkozás              | Hivatkozás szövege, hivatkozás URL-címe, akadálymentes dinamikus webes alkalmazások (ARIA) címke és **Hivatkozás megnyitása új lapon** | A funkciómodulok egy vagy több „cselekvésre való felhívás” hivatkozást támogatnak. Hivatkozás hozzáadásakor hivatkozásszöveg, URL és ARIA címke szükséges. Az ARIA címkéknek az akadálymentességi követelmények kielégítése érdekében leírónak kell lennie. A hivatkozások beállíthatók úgy, hogy új lapon legyenek megnyitva. |
| Kép elhelyezése   | **Jobbra**, **Balra**, **Felül** vagy **Alul** | Ez a tulajdonság határozza meg a kép szöveghez viszonyított pozícióját. Ha például a **Jobbra** beállítás van kiválasztva, a kép a szövegtől jobbra jelenik meg. |
| Képoszlop mérete | Egy **1** és **12** közötti érték | Ez a tulajdonság határozza meg a kép szöveghez viszonyított méretét. A méret a lapon található oszlopok számában van kifejezve. A lapon 12 oszlop van. Alapértelmezés szerint a kép és a szöveg mérete azonos (hat oszlop mindegyik). A méret azonban igény szerint módosítható. |

## <a name="add-a-feature-module-to-a-new-page"></a>Funkciómodul felvétele egy új lapra 

A funkciómodul új lapra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lehetőséget, és hozzon létre egy **funkciósablon** nevű sablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy funkciómodult.
1. Adja be a sablont és tegye közzé.
1. A most létrehozott funkciósablon használatával hozzon létre egy **funkciólap** nevű lapot.
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen a **Modulok kiválasztása** alatt válasszon ki egy funkciómodult, majd kattintson az **OK** gombra.
1. A bal oldali fastruktúrán válassza ki a funkciómodult.
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

[Főképmodul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)
