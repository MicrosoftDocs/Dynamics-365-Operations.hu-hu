---
title: Kettős felhasználású áruk
description: Ez a témakör azt mutatja be, hogyan lehet nyomon követni a kettős felhasználású árukként azonosított termékeket, tárolni az összes érintett termék és célország esetében a tanúsítványok számait, valamint kinyomtatni a megfelelő számlákra, szállítólevelekre és/vagy értékesítési rendelésekre vonatkozó érvényes tanúsítványok számát.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COODualUseCerts, COORules, COODualUseCountries
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: a6cc730f8d672d906072a9b97b737dbdea9faf2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243201"
---
# <a name="dual-use-goods"></a>Kettős felhasználású áruk

[!include [banner](../includes/banner.md)]

A kettős felhasználású áruk általában olyan cikkek, amelyekben polgári és katonai alkalmazásokra egyaránt használnak. Például egy vegyszer használható műtrágyaként vagy robbanóanyagként is. Számos országban külön előírás vonatkozik a kettős felhasználású áruk exportjára, importjára és szállítására. Ezért fontos, hogy a kettős felhasználású áruk nemzetközi kereskedelmében részt vevő vállalatok nyomon kövessék a különböző irányelveket és tanúsítványokat.

A kettős felhasználás funkcióval a vállalatok könnyebben nyomon követhetik kettős felhasználású árukként azonosított termékeket, tárolhatják az összes érintett termék és célország esetében a tanúsítványok számait, valamint kinyomtathatják a megfelelő számlákra, szállítólevelekre és/vagy értékesítési rendelésekre vonatkozó érvényes tanúsítványok számát. Segít biztosítani, hogy a termékek szállítása során mindig naprakész tanúsítványok szerepeljenek.

Vegyük például a következő esetet:

1. A rendszer **kettős felhasználás országbeállítása** lapja azt jelzi, hogy a Franciaországba irányuló szállítmányoknak tanúsítvánnyal kell rendelkezniük.
2. Az X-100 termék **Kiadott termék adatai** oldala azt jelzi, hogy ez egy kettős felhasználású áru. Együttesen a kód, a kategória, a csoport és a rendszer határozza meg, hogy melyik exportellenőrzési osztályozásba a termék tartozik.
3. A **kettős felhasználású tanúsítványok** lap tartalmazza az X-100 termék tanúsítványát a Franciaországba való szállításhoz. Ez a tanúsítvány 2020. január 1-jén lejár.
4. 2020. június 17-én értékesítési rendelést hoz létre egy Franciaországban működő vevői vállalatnak, és a rendelés tartalmaz X-100-es terméket.
5. Az értékesítési rendelés mentésekor a rendszer a következő adatokat határozza meg:

    1. Tartalmaz a rendelés a kettős felhasználású termékeket?
    2. Ha a rendelés kettős felhasználású árukat tartalmaz, akkor a célországnak kettős használatú tanúsítványokra van szüksége?
    3. Ha az országban kettős használatú tanúsítványok szükségesek, akkor minden egyes kettős használatú áruhoz áll rendelkezésre érvényes tanúsítvány a célországhoz?

6. A rendelés X-100 terméket tartalmaz, és a termék szállítása Franciaországba történik, és a termékhez francia tanúsítvány van. A tanúsítvány azonban lejárt. Ennek megfelelően a következő figyelmeztető üzenet jelenik meg: „Az értékesítési rendelésben egy vagy több kettős felhasználású cikk található, amelynek kettős használatára vonatkozó tanúsítványok nem érvényesek. Folytatja a visszaigazolást?"

Ez a témakör azt mutatja be, hogyan lehet konfigurálni azokat a beállításokat, amelyek szükségesek a kettős felhasználású áruk beállításához és a helyzet támogatásához.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>A kettős használat követelményeinek meghatározása mindegyik érintett ország esetében

A különböző országoknak különböző követelményei vannak a kettős felhasználású áruk esetében. A **kettős felhasználású országbeállítás** lapon nyomon követheti azokat az országokat, amelyek nem igényelnek tanúsítványt. Az itt megadott adatok az értékesítési rendelések létrehozásakor ellenőrzésre kerülnek, és a rendszer figyelmezteti a szükséges tanúsítványok megadására.

A következő lépésekkel lehet beállítani a kettős felhasználási követelményekkel kapcsolatos információkat a különböző országokban.

1. Ugrás a **Termék adatainak kezelése \> beállítás \> termék megfelelősége \> kettős használatú termékek \> kettős használat országbeállítás**.
2. Válasszon ki egy meglévő országbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új ország-beállítást.
3. Állítsa be a következő értékeket a kiválasztott vagy az új ország beállítására.

    | Mező | Leírás |
    |---|---|
    | Ország/régió | Válassza ki azt az országot, amelynél a követelményeket nyomon szeretné követni. |
    | A tanúsítvány kötelező | Jelölje be ezt a jelölőnégyzetet olyan országok esetén, amelyben szükség van kettős felhasználású áruk tanúsítványára. Törölje azoknál az országoknál, amelyeknél nem szükséges ez a tanúsítás. |

## <a name="create-dual-use-categories"></a>Kettős felhasználású kategóriák létrehozása

A kettős felhasználású árukat gyakran az exportellenőrzési osztályozási szám (ECCN) alapján kell kategorizálni. A ECCN egy alfanumerikus kód, amely a cikkeket olyan tényezők alapján kategorizálja, mint az árucikk és a technológia. A **Kettős felhasználás kategóriái** oldal segítségével létrehozhat egy listát a használt kategóriákról, jelentéskészítési célból.

A kettős felhasználású kategóriák beállításához kövesse az alábbi lépéseket.

1. Ugrás a **Termék adatainak kezelése \> beállítás \> termék megfelelősége \> kettős használatú termékek \> kettős használat kategóriái**.
2. Válasszon ki egy meglévő kategóriát a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új kategóriát.
3. Állítsa be a következő értékeket a kiválasztott vagy az új kategóriára.

    | Mezők | Leírás |
    |---|---|
    | Kettős felhasználású kód | Adja meg a teljes ECCN-kódot (például *3A001*).|
    | Kettős felhasználás kategóriája | A ECCN-kód Commerce Control List (CCL) kategóriájú részének megadása. A *3A001* ECCN kód esetében például ez az érték *3*. |
    | Kettős felhasználású csoport | A ECCN-kód termékazonosító részének megadása. A *3A001* ECCN kód esetében például ez az érték *A*. |
    | Kettős felhasználású rendszer | Írja be a cikk rendszerkódját. Ez a kód annak okát azonosítja, hogy a tétel miért minősíthető kettős felhasználású terméknek. A *3A001* ECCN kód esetében például ez az érték *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Kettős felhasználású kategóriák alkalmazása a termékekre

Ha egy terméket kettős felhasználású termékként szeretne megjelölni, és egy kettős felhasználási kategóriát alkalmazni, hajtsa végre az alábbi lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon ki vagy hozzon létre egy terméket, és nyissa meg a **Kapcsolódó termékadatok** oldalát.
1. A **Külkereskedelem** gyorslapon a **kettős felhasználású termékek** beállítást válassza **Igen** értékre, ha az aktuális terméket kettős használatú áruként állítja be.
1. A **Kettős felhasználás kódja** mezőt az aktuális termékre vonatkozó kódra kell megadni. (Ezt a kódot definiálta a **Kettős felhasználási kategóriák** lapon.)

Ez a beállítás az értékesítési rendelések létrehozásakor be van jelölve.

## <a name="set-up-dual-use-certificates"></a>Kettős beállítású tanúsítványok beállítása

A **kettős felhasználású tanúsítványok** lapon állíthatja be és kezelheti a szükséges kettős használatú tanúsítványokat minden termékhez és országhoz. Nyomon követheti az egyes tanúsítványok adatait, például az országot és az érvényességi dátumokat. Lehetőség van arra is, hogy megadja, hogy hol kell kinyomtatni ezeket az adatokat. Az adatok például a számlára, a szállítólevélre és/vagy az értékesítési rendelésre is kinyomtathatók. Ez a beállítás az értékesítési rendelések létrehozásakor be van jelölve.

1. Ugrás a **Termék adatainak kezelése \> beállítás \> termék megfelelősége \> kettős használatú termékek \> kettős használat tanúsítványai** pontra.
2. Válasszon ki egy meglévő tanúsítványt a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új tanúsítványt.
3. Állítsa be a következő értékeket a kiválasztott vagy az új tanúsítványra.

    | Mező | Leírás |
    |---|---|
    | Cikkszám | Válassza ki annak a kettős felhasználású árunak a cikkszámát, amelyre a tanúsítvány vonatkozik. |
    | Ország/régió | A célország vagy régió, ahol a tanúsítványt használni kell. |
    | Tanúsítványszám | A szállító vagy a vevő részére kiállított tanúsítványon megjelenő szám. |
    | Hatályos | Válassza ki az első dátumot, amikor az aktuális tanúsítvány érvényes.|
    | Lejárat | Válassza ki az utolsó dátumot, amikor az aktuális tanúsítvány érvényes. |
    | Nyomtatás számlára | Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett számlákra rá szeretné nyomtatni a tanúsítvány számát. |
    | Nyomtatás szállítólevélre | Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett szállítólevelekre rá szeretné nyomtatni a tanúsítvány számát. |
    | Nyomtatás az értékesítési rendelésre | Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett értékesítési rendelésekre rá szeretné nyomtatni a tanúsítvány számát. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]