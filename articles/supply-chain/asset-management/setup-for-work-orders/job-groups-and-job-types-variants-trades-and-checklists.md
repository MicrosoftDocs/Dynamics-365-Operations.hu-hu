---
title: Karbantartási feladatok típusai, kategóriái és változatai, karbantartási szakmák és ellenőrzőlisták
description: Ez a témakör leírja a karbantartásifeladat-típusok kategóriái és karbantartásifeladat-típusok, karbantartásifeladat-típusok változatai, karbantartási szakmák és karbantartási ellenőrző listák használatát az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 54bd489a3c9be5be298ef75893b7acad38104a1379d20f853dd700635a3e058e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742800"
---
# <a name="maintenance-job-types-categories-variants-trades-and-checklists"></a>Karbantartási feladatok típusai, kategóriái és változatai, karbantartási szakmák és ellenőrzőlisták

[!include [banner](../../includes/banner.md)]

Egy eszköztípus minden eszközhöz csatolva van. Az eszköztípusok határozzák meg, hogy a karbantartási feladattípusok (és így a karbantartási feladatok) milyen típusú eszközökkel végezhetők el. Munkarendelés létrehozásakor ki kell választania egy karbantartásifeladat-típust. Csak olyan karbantartásifeladat-típusok közül lehet választani, amely kapcsolódik az eszköztípus beállításához, amely az eszközhöz van használva.

Az eszközök és a karbantartási feladattípusok grafikus áttekintését, valamint a munkarendelésekhez való kapcsolódásukat lásd: [Munkavégzési helyszínek és eszközök](../overview/functional-locations-and-objects.md).

A karbantartási feladat típusváltozatok beállítható karbantartási feladat típusánál állíthatók be. A karbantartási feladattípus variánsai határozzák meg a feladattípus eltéréseit, például a méreteket (kis, közepes vagy nagy), az időszakokat (heti, kétheti, egy hónapos vagy három hónapos) és a konfigurációkat (alacsony színvonalú, rugalmas vagy nagy teljesítmény).

A karbantartásfeladat-típusok szakterületekről adnak információt, például mechanikus, elektromos és hidraulikus szakterületek. A szakértelemmel kapcsolatos követelményeket a karbantartási feladatok típusánál lehet beállítani. A karbantartásifeladat-típusok mindegyike használható az összes karbantartásifeladattípussal kapcsolatosan. Egy munkarendeléshez tartozó karbantartási feladattípus változat és/vagy karbantartási feladat szakma kiválasztása nem kötelező.

Minden karbantartásifeladat-típushoz az karbantartásifeladat-típus beállítások különböző változatait lehet létrehozni. Ha például egy karbantartásifeladat-típus neves **Szerviz**, akkor a következő eltérések változatok hozhatók létre a karbantartásifeladat-típushoz: **Teherautók 30 000 km**, **Autók 30 000 km** és **Furgonok 30 000 km**.

A karbantartási feladattípus-kategóriák a karbantartási feladattípusok egy csoportját gyűjtik összes áttekintés céljából. A karbantartási feladattípus-kategóriákra példák lehetnek a **Kalibráció**, **Vizsgálat**, **Nagyjavítás** és **Műszerezés**.

A karbantartási ellenőrzőlista sablonokat és karbantartási ellenőrzőlista változókat a karbantartási ellenőrzőlisták beállításához lehet használni. A karbantartási ellenőrzőlisták a karbantartási feladattípusokon állíthatók be, és a munkarendelésekben használatosak.

Először beállítja a szükséges karbantartásifeladat-típusok kategóriáit és karbantartásifeladat-típusok változatait és a karbantartásifeladat szakmákat. Ezután létrehozhatja a karbantartásifeladat-típusokat. Végül a **Karbantartási feladat alapértelmezései** lapon a berendezéshez szükséges karbantartásifeladat-típusok valamennyi változatát létre kell hozni. Ezen a lapon megadhatja az előrejelzéseket, a karbantartási ellenőrzőlistákat és a szerszámokat is a karbantartási feladattípusok kombinációihoz.

> [!NOTE]
> A karbantartási feladattípus csak egy karbantartási feladattípus-kategóriához kapcsolható.

## <a name="create-a-maintenance-job-type-category"></a>Karbantartási feladattípus kategória létrehozása

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Karbantartási feladattípusok kategóriái** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A **Karbantartási feladat típuskategóriája** mezőben adja meg a karbantartási feladattípus kategóriájának azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.

    A karbantartási feladattípus-kategóriák karbantartási feladattípusokhoz történő kapcsolása után **Feladattípusok** mező a karbantartási feladattípus kategóriához kapcsolódó karbantartási feladattípusok számát jeleníti meg.

![Karbantartási feladattípus kategóriaoldala.](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Karbantartási feladattípus változat létrehozása

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Karbantartási feladattípusok változatai** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A **Karbantartási feladat típusváltozata** mezőben adja meg a karbantartási feladattípus változatának azonosítóját.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A **Karbantartási feladattípusok** gyorslapon válassza a **Hozzáadás** lehetőséget egy karbantartási feladattípus hozzáadásához.
6. A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát.
7. További karbantartási feladattípusok hozzáadásához ismételje meg az 5–6. lépéseket a karbantartási feladattípus változathoz.

    A **Részletek** gyorslapon a **Feladattípusok** mező mutatja, hogy a karbantartási feladattípus változathoz milyen típusú karbantartási feladattípusok vannak hozzáadva.

![Karbantartási feladattípus változatok oldala.](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Karbantartási feladat szakterület létrehozása

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Karbantartási feladattípus szakterülete** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A **Szakterület** mezőben adjon meg egy azonosítót a karbantartási feladat szakterületéhez.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A **Szakértelmek** gyorslapon válassza a **Hozzáadás** lehetőséget, ha új szakértelmet szeretne hozzáadni a karbantartással kapcsolatos szakterülethez.
6. A **Szakértelem** mezőben válassza ki a szakértelmet.
7. A **szint** mezőben válassza ki a szakértelem szintjét.
8. További szakértelem hozzáadásához a karbantartásifeladat szakterülethez ismételje meg az 5–7. lépéseket.

    A **Részletek** gyorslapon a **Szakértelmek** mező mutatja, hogy a karbantartási feladattípus szakterülethez milyen típusú karbantartási feladat szakértelmek vannak hozzáadva.

9. A **Tanúsítványok** gyorslapon válassza a **Hozzáadás** lehetőséget egy tanúsítványt hozzáadásához a karbantartási feladat szakterületéhez.
10. A **Tanúsítvány típusa** mezőben válassza ki tanúsítványt.
11. További tanúsítványok hozzáadásához a karbantartásifeladat szakterülethez ismételje meg az 9–10. lépéseket.

    A **Részletek** gyorslapon a **Tanúsítványok** mező mutatja, hogy a karbantartási feladattípus tanúsítványhoz milyen típusú karbantartási feladat szakértelmek vannak hozzáadva.

![Karbantartási feladat szakterület oldala.](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Karbantartási-ellenőrzőlista változó létrehozása

Amikor karbantartási-ellenőrzőlista sorokat hoz létre az alapértelmezett karbantartási feladattípusban, ki kell választania egy karbantartásiellenőrzőlista-típust. A **Változó** egy karbantartásiellenőrzőlista-típus. Ez egy munkarendelési sorral kapcsolatos karbantartási ellenőrzőlista-sor egy tartományának lehetséges eredményét határozza meg. A változók segítségével egy előre meghatározott eredményt állíthat be, anélkül, hogy pontos mérést kellene végeznie.

**1. példa** : Az olajszintet három érték definiálásával lehet mérni: **túlmagas szint**, **túlalacsony szint** és **tartományon belüli szint**. Minden érték esetében meg kell adni, hogy az érték eredménye **Sikeres**, **Sikertelen** vagy **Nincs**.

**2. példa** : Egy berendezés vizuális vizsgálatának elvégzése a kopás vagy elhasználódás felméréséhez.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Karbantartási ellenőrzőlisták** \> **Karbantartásiellenőrzőlista-változók** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A **Változó** mezőben adjon meg egy azonosítót a karbantartási-ellenőrzőlista változójához.
4. A **Név** mezőben adjon meg egy nevet.
5. Az **Általános** gyorslapon válassza a **Hozzáadás** lehetőséget, ha egy változóhoz szeretne hozzáadni egy sort.

    A **Sor száma** mezőben a sorrendben következő sorszámot automatikusan meg lesz adva. Miután hozzáadta az összes sort, igény szerint megváltoztathatja a sorszámokat. Amikor kiválaszt egy sort, majd megnyomja a **Le nyíl** billentyűt, a program automatikusan beírja a következő sorhoz a következő sorszámot.

6. Az **Érték** mezőben adja az érték leírását.
7. Az **Eredmény** mezőben válassza ki a sorhoz tartozó eredményt.

![Karbantartási-ellenőrzőlista változók oldala.](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Karbantartási-ellenőrzőlista sablonjának létrehozása

A karbantartási ellenőrzőlista sablonokat olyan gyakori feladatokhoz lehet használni, amelyeket a dolgozónak végre kell hajtania egy munkarendelés helyes befejezéséhez. A sablonokra hivatkozás a karbantartási feladatok alapértelmezett típusának karbantartási ellenőrzőlista soraiból történik. A sablonok hivatkozhatnak több karbantartási feladattípus alapértelmezett sorára. Ezért egyszerűen újra felhasználhatja a gyakori karbantartásiellenőrzőlista-feladatok egy készletét. A karbantartási ellenőrzőlista sablonokat tartalmazzák az általános biztonsági utasításokat, valamint azoknak a cikkeknek és feltételeknek a listája, amelyeket ellenőrizni kell egy adott szivattyúnál vagy hasonló szállítószalag-modellnél.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Karbantartási ellenőrzőlisták** \> **Karbantartásiellenőrzőlista-sablonok** lehetőséget.
2. Válassza az **Új** lehetőséget.

    A program automatikusan beírja a sablon azonosítóját a **Karbantartásiellenőrzőlista-sablon** mezőbe.

3. A **Név** mezőben adja meg az új karbantartásiellenőrzőlista-sablon nevét.
4. A **Karbantartásellenőrzőlista-sorok** gyorslapon válassza a **Hozzáadás** lehetőséget egy sablonsor hozzáadásához.

    A **Sor száma** mezőben a sorrendben következő sorszámot automatikusan meg lesz adva. Miután hozzáadta az összes sort, igény szerint megváltoztathatja a sorszámokat. Amikor kiválaszt egy sort, majd megnyomja a **Le nyíl** billentyűt, a program automatikusan beírja a következő sorhoz a következő sorszámot.

5. A **Típus** mezőben válasszon egy típust karbantartásiellenőrzőlista-sorhoz. Minden karbantartásiellenőrzőlista-típushoz a **Sor részletei** gyorslap kapcsolódó mezőket jelenít meg. A következő értékek állnak rendelkezésre:

    - **Szöveg** – A sorhoz tartozik szöveg, amely leírja funkcióját. Ezt a karbantartásiellenőrzőlista-típust akkor kell használni, ha azt szeretné, hogy a dolgozó ellenőrizzen vagy megvizsgáljon valamit, de nem vár konkrét (mérhető) eredményt. Miután kiválasztotta a típust, írjon be egy nevet vagy egy fejlécet a **Név** mezőbe. A **Utasítások** mezőbe írja be, hogy mi a feladat. Ha a lépést kötelező megadni a karbantartási ellenőrzőlistához, akkor a **Kötelező** beállítást **Igen** értékre kell beállítani.
    - **Fejléc** – Ez a sor fejlécként használatos az alatta megjelenő karbantartásiellenőrzőlista-sorok csoportosításához. Ez a típus akkor hasznos, ha több karbantartásiellenőrzőlista-sor van, amelyek meghatározott területekre oszthatók fel. A fejlécek áttekintést nyújtanak annak a dolgozónak, aki olyan karbantartási ellenőrzőlistát tölt ki amelynek több karbantartásiellenőrzőlista-sora van. Miután kiválasztotta a típust, írjon be egy leíró nevet a **Név** mezőbe.
    - **Sablon** – Ezt a sort egy meglévő sablonra mutató hivatkozásként lehet használni. Miután kiválasztotta a típust, írjon be egy nevet a sablonnak a **Név** mezőbe. A **Sablon** mezőben válassza ki a sablont.
    - **Változó** – Ez a sor a lehetséges eredményének meghatározására szolgál egy tartományban. A karbantartási ellenőrzőlisták változóinak beállításával kapcsolatos további tudnivalókat lásd: [Karbantartásiellenőrzőlista-változó létrehozása](#create-a-maintenance-checklist-variable). Miután kiválasztotta a típust, írjon be egy leíró nevet a változónak a **Név** mezőbe. A **Változó** mezőben válassza ki a változót. A **Utasítások** mezőbe írja be, hogy mi a feladat. Ha a lépést kötelező megadni a karbantartási ellenőrzőlistához, akkor a **Kötelező** beállítást **Igen** értékre kell beállítani.
    - **Mérés** – Ez a sor egy adott mérés rögzítésére szolgál. Beállíthatja azt a mérést amelynek az előre meghatározott számlálóhoz kell kapcsolódnia. Miután kiválasztotta a típust, írjon be egy nevet a sablonnak a **Név** mezőbe. Ha ez a lépés kötelező a karbantartási ellenőrzőlistához, akkor a **Kötelező** beállítást **Igen** értékre kell beállítani. Ha a mértéksort számláló regisztrációként szeretné használni, válassza ki a számlálót a **Számláló** mezőben. A kapcsolódó **Mértékegység** mező frissítése automatikusan történik. Ha kiválasztott egy számlálót, válassza ki a frissítési módszert az **Érték** mezőben. A **Min . érték** és a **Max. érték** mezőkben adja meg a megengedett értéktartományt. A **Utasítások** mezőbe írja be, hogy mi a feladat.

        > [!NOTE]
        > Bármely **Mérés** típusú sor, amelyhez nem tartozik számlálóbeállítás egyéni mértékregisztrációként vannak kezelve, amelyekhez nincs automatikus utánkövetés az Eszközkezelésben. Hasonlóképpen, ha a kiválasztott számláló típusa nem szerepel a munkarendeléshez kapcsolódó eszközön, akkor a karbantartási ellenőrzőlista feladatát független mérésként kezeli a program. A számláló értéke többször is módosítható. Ha nincs közzétéve, amíg a [munkarendelés életciklus-állapota](work-order-lifecycle-states.md), olyan állapotra nem változik, ahol a **Karbantartási ellenőrzőlista feldolgozása** beállítás értéke nincs **Igen** értékre van állítva.

    A **Részletek** gyorslapon a **Csekkek** mező a sablonban található ellenőrzőlistasorok teljes számát jeleníti meg. Ez a szám tartalmazza a sablonban hivatkozott bármely meglévő sablon beágyazott sorait.

![Karbantartási-ellenőrzőlista sablonok oldala.](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Karbantartásifeladat-típus létrehozása

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Karbantartási feladattípusok** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A **Karbantartási feladat típusa** mezőben adja meg a karbantartási feladat típusának azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.

    A **Részleteket** gyorslap áttekintést nyújt a karbantartási feladattípushoz létrehozott karbantartási feladattípus-változatok, szakértelmek, tanúsítványok, sikeres feladatok és eszközök számáról. A **Beállítási sorok** mezőben látható a karbantartási feladattípusban beállított alapértelmezett karbantartási feladattípusok száma. Az **Eszközök** mező a karbantartási feladattípust jelenleg használó aktív eszközök számát jeleníti meg.

5. Az **Általános** gyorslapon **Karbantartási feladattípus kategóriája** mezőben válasszon egy karbantartási feladattípus kategóriáját .
6. Ha a karbantartási feladattípusnál le kell állítani a karbantartáshoz a berendezést, hogy el lehessen végezni a feladatot állítsa a **Karbantartás miatti üzemkimaradási tevékenységek** beállítást **Igen** értékre.
7. A **Leírás** gyorslapon adja meg a karbantartási feladattípus leírását.
8. A **Karbantartási feladattípus változatai** gyorslapon változatokat adhat meg a karbantartási feladat típusához.
9. A **Szükséges szakértelmek** és a **Szükséges tanúsítványok** gyorslapokon szakértelem és tanúsítvány követelményei adhatók meg a karbantartási feladattípushoz.
10. Ha egy bizonyos karbantartási feladattípust végre kell hajtani következőként, adja azt hozzá a **Következő feladatok** gyorslapon. A karbantartási feladattípushoz kapcsolódó, a karbantartási feladattípus-változatot is be lehet állítani. Ha a következő feladatnak meghatározott számú nappal előbb vagy később el kell kezdődnie ahhoz feladathoz képest, amely ezt a karbantartásifeladat-típust használja, adja meg a napok számát a **Késleltetés napokban** mezőben. A pozitív számok a kapcsolódó feladat kezdetét követő napokat jelentik, a negatív számok pedig a kapcsolódó feladat ütemezett kezdése előtti napokat jelentik. Ha például az **5** értéket adja meg, a következő feladat a karbantartási feladattípushoz kapcsolódó feladat kezdete után öt nappal fog kezdődni. Ha a **-3** értéket adja meg, a következő feladat a karbantartási feladattípushoz kapcsolódó feladat kezdete előtt három nappal fog kezdődni.

    > [!NOTE]
    > Ha egynél több karbantartási feladattípus sort ad hozzá, a sorok sorrendje jelzi, hogy milyen sorrendben kell elvégezni azokat. A sorrend a lista tetején kezdődik.

11. Az **Eszköztípusok** gyorslapon a karbantartási feladattípushoz hozzáadhatók eszköztípusok.

![Karbantartási feladat típusok oldala.](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Karbantartási feladattípusok alapértelmezett sorai és a kapcsolódó előrejelzések, karbantartási ellenőrzőlisták, eszközök, leírások és mellékletek létrehozása

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Karbantartási feladattípusok alapértelmezései** lehetőséget.

    – vagy –

    Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Karbantartási feladattípusok** lehetőséget, válasszon ki egy karbantartás feladattípust, majd válassza a **Karbantartási feladattípus alapértelmezései** lehetőséget.

2. Válassza az **Új** lehetőséget.
3. A **Funkcionális hely**, **Eszköz típusa**, **Gyártó**, **Modell** és **Eszköz** mezőkben válassza ki a megfelelő értékeket attól függően, hogy mennyire kell specifikusnak lennie a karbantartási feladattípus alapértelmezéseinek.
4. A **Karbantartási feladattípus** mezőben válassza ki a karbantartási feladattípust, ha az nem lett automatikusan kiválasztva.
5. A **karbantartási feladattípus változója** és a **Szakma** mezőben válasszon ki egy karbantartási feladattípust és karbantartási feladat szakmát.
6. Válassza az **Előrejelzés** lehetőséget.
7. A **Karbantartási feladattípus alapértelmezett előrejelzése** lapon előrejelzéseket készíthet az órákról, cikkekről és kiadásokról. A megfelelő lapokon válassza a **Hozzáadás** lehetőséget, majd válasszon lehetőségeket a szükséges előrejelzések létrehozásához a karbantartási feladattípushoz.
8. A **Cikkek előrejelzése** lapon kiválaszthatja a cikksorban megjelenítendő készletdimenziókat. Válassza a **Készlet** \> **Dimenziók** lehetőséget, válassza ki a megjelenítendő dimenziókat, állítsa a **Beállítás mentése** lehetőséget **Igen** értékre, majd válassza az **OK** lehetőséget.
9. A **Cikk előrejelzése** lapon válassza a **Cikket hol használják** lehetőséget, ha szeretne áttekintést kapni arról, hogy az Eszközkezelésben hol használják a kiválasztott sorban található cikk az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban. 

    A **Karbantartási előrejelzés összesítése** gyorslap áttekintést jelenít meg az előrejelzett összegekről. Ez az áttekintés a létrehozott órák és előrejelzési sorok teljes számát tartalmazza.

    > [!NOTE]
    > Ha szeretné átmásolni az előrejelzés-beállításokat egy másik karbantartási feladattípusból, válassza az **Előrejelzés másolása** parancsot, majd válassza ki azt a karbantartási feladattípust, amelyből másolni szeretné a beállítást.

11. A változtatások mentéséhez válassza a **Mentés** elemet.
12. Zárja be a **Karbantartási feladattípus alapértelmezett előrejelzése** lapot, hogy visszatérjen a **Karbantartás feladattípus alapértelmezései** lapra.
13. Válassza a **Karbantartási ellenőrzőlisták** lehetőséget.
14. A **Karbantartási feladattípus alapértelmezéseinek ellenőrzőlistája** lapon felvehet karbantartási ellenőrzőlista sorokat a kiválasztott karbantartási feladattípus alapértelmezéséhez. A **Karbantartási ellenőrzősorok** gyorslapon válassza az **Új** lehetőséget egy karbantartási ellenőrzőlistasor hozzáadásához.

    A rendszer automatikusan beszúrja a sorszámokat a **Sorszám** mezőbe; ez jelöli az eszközök karbantartási ellenőrzőlistasorok sorrendjét. A sorszámozás igény szerint módosítható. Miután létrehozta az első karbantartási ellenőrzőlistasorát, válassza ki a sort, majd a **Le nyílbillentyűvel** adjon egy sort a sor alá. Azt is megteheti, hogy kijelöl egy karbantartási ellenőrzőlista sort, majd az **Új** lehetőséget választja. Ebben az esetben a kiválasztott karbantartási ellenőrzőlista sor felett új sort ad hozzá a program.

15. A **Típus** mezőben válassza ki a sor típusát, majd adja hozzá a karbantartási ellenőrzőlistatípushoz kapcsolódó adatokat. A rendelkezésre álló típusok és a kapcsolódó mezők leírását lásd a [Karbantartás ellenőrzőlista sablon létrehozása](#create-a-maintenance-checklist-template) szakaszban.

    > [!NOTE]
    > Ha szeretné átmásolni a karbantartási ellenőrzőlista beállításokat egy másik karbantartási feladattípusból, válassza a **Karbantartási ellenőrzőlista másolása** parancsot, majd válassza ki azt a karbantartási feladattípust, amelyből másolni szeretné a beállítást.
    >
    > Egyszerűen létrehozhat egy sablont egy meglévő karbantartási ellenőrzőlistából. Ezután újra felhasználhatja a sablont több karbantartási ellenőrzőlistában. Az új sablon pontos másolata lesz az aktív karbantartási ellenőrzőlistának. Válassza a **Sablon létrehozása** lehetőséget, majd adja meg a sablon nevét a Sablon neve mezőben. Ha a meglévő karbantartási ellenőrzőlistát egyetlen sorra szeretné cserélni, ami az új sablonra hivatkozik, állítsa a **Csere** beállítást **Igen** értékre. A sablon tartalmát a **Karbantartás ellenőrzőlistasablonok** részletei oldalán tekintheti meg.

16. A változtatások mentéséhez válassza a **Mentés** elemet.
17. Térjen vissza a **Karbantartási feladattípusának alapértelmezései** lapra.
18. Válassza ki az **Eszközök** elemet.
19. A **Karbantartási feladattípus alapértelmezett eszközei** lapon felveheti a karbantartási feladattípushoz használandó eszközöket (erőforrásokat). Válassza az **Új** lehetőséget, majd válassza ki az eszközt az **Erőforrás** mezőben.

    > [!NOTE]
    > Ha szeretné átmásolni az eszközbeállításokat egy másik karbantartási feladattípusból, válassza az **Eszközök másolása** parancsot, majd válassza ki azt a karbantartási feladattípust, amelyből másolni szeretné a beállítást.

20. A változtatások mentéséhez válassza a **Mentés** elemet.
21. Térjen vissza a **Karbantartási feladattípusának alapértelmezései** lapra.
22. Válassz a **Munkaleírás** lehetőséget.
23. A **Munkaleírás** lapon válassza a **Szerkesztés** elemét, majd vegyen fel egy leírást, amely a kiválasztott karbantartási feladattípushoz kapcsolódik.
24. A Leírás mentéséhez válassza a **Mentés** parancsot.

    Ha itt egy munkaleírást ad meg, akkor felülbírál minden, a karbantartási feladattípushoz beállított leírást a **Karbantartás feladattípusok** oldalon. Ha nem ad hozzá itt munkaleírást, akkor a program a karbantartási feladattípushoz beállított bármely leírást használja. A leírásokat a program automatikusan átviszi az olyan munkarendelésekre, amelyek a karbantartás feladattípust vagy a karbantartás feladattípus alapértelmezést használnak.

25. Térjen vissza a **Karbantartási feladattípusának alapértelmezései** lapra.
26. A kiválasztott karbantartási feladattípus alapértelmezett sorában a mellékletek beállításához Válassza a **Dokumentumok csatolása** jelölőnégyzetet. A karbantartási feladattípus alapértelmezett sorához beállított mellékleteket a program automatikusan beilleszti azokba a Munkarendelés-sorokba, amelyek a karbantartási feladattípus alapértelmezett sorát használják.
27. Válassza a az **Új** lehetőséget, majd válasszon egy dokumentumtípust.
28. Dokumentum vagy a fájl feltöltése.
29. Állítsa be a mezőket a **Mellékletek** oldalon. A mellékletbeállítások a szokásos dokumentum-beállítási funkciókat használják.
30. A melléklet mentéséhez válassza a **Mentés** parancsot.

    > [!NOTE]
    > A karbantartási feladattípushoz tartozó mellékleteket a program csak akkor nyomtatja ki a munkarendelésről szóló jelentéssel együtt, ha a mellékletek dokumentumtípusa ki van kiválasztva **Dokumentumkezelés** alatt a **Vagyonkezelési paraméterek** lapon (**Eszközkezelés** \> **Beállítás** \> **Eszközkezelési paraméterek**). A mellékletek egy része olyan útmutatókat tartalmaz, amelyek elmagyarázzák, hogyan lehet egy adott feladatot elvégezni vagy egy előre definiált karbantartási ellenőrzőlistát kitölteni (ha nem használja a karbantartási ellenőrzőlista funkciót a karbantartási feladattípus alapértelmezett soraihoz).

    A **Karbantartási feladattípus alapértelmezési** lapon minden sor megjeleníti az előre jelzett órák számát, valamint a cikkekhez, költségekhez, karbantartási ellenőrzőlistához és eszközökhöz létrehozott sorok számát. Az **Eszközök** mező a karbantartási feladattípus alapértelmezett sorához kapcsolódó aktív eszközök számát jeleníti meg.

31. Ha egy karbantartási feladattípust alapértelmezést szeretne másolni egy másik karbantartó feladattípus alapértelmezésre, válassza ki a karbantartási feladattípus alapértelmezés sorát, és másolja át egymásik beállításba, válassza a **Beállítás másolása** lehetőséget, majd jelölje ki a másolandó karbantartási feladattípust.
32. Ha meg szeretné tekinteni azoknak az eszközöknek, karbantartási terveknek vagy fenntartási köröknek a listáját, amelyek jelenleg a karbantartási feladattípust alapértelmezés sort használják, válassza ki a sort, majd válassza a **Használó** lehetőséget.

![Karbantartási feladattípus alapértelmezések oldala.](media/07-setup-for-work-orders.png)

Amikor a rendszer kiválasztja a rendelkezésre álló karbantartási feladattípus alapértelmezést, amelyet a Munkarendelés sorában kell használni, akkor a kiválasztás az eszközön és a kapcsolódó eszköztípus beállításon alapul. Az eszközkezelés minden olyan karbantartási feladattípus alapértelmezésen végigmegy, amely ahhoz a karbantartási feladattípushoz kapcsolódik, amely kapcsolódik az eszköztípushoz, hogy megkeresse a lehetséges egyezést. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szóval, a leginkább specifikus kombináció megtalálásához az eszközkezelés először ellenőrzi a **Szakma** mező esetleges egyezését. Ha nem talál egyezést, akkor a **Karbantartási feladat típusának változata** mezővel való egyezést ellenőrzi. Ha nem **talál egyezést, akkor ellenőrzi a karbantartási feladattípus** mező egyeztetését, és így tovább (**Szakma**, majd **Karbantartási feladattípus-változat**, majd **Eszköz**, majd **Eszköz**, majd **Modell**, majd **Gyártó**, majd **Eszköz típusa**). Ha nem talál egyezést, akkor az alapértelmezett rekord, amelyben csak a karbantartási feladattípus van kiválasztva, lesz használva.

A projekt tevékenységazonosítója automatikusan létrejön minden olyan karbantartási feladattípus alapértelmezési sorhoz, amelyet létrehoz. A projekttevékenység a vagyonkezelési paraméterek lap eszközök lapjának a **karbantartás előrejelzési projekt** mezőben jön lértre az **Eszközök** lapon az **Eszközkezelési paraméterek** oldalon. A projekttevékenység célja a munkarendeléssel kapcsolatos órák, cikkek és kiadások előrejelzésének kezelése. A karbantartási feladattípus-előrejelzéseket a program automatikusan átviszi a munkarendelés sorába, és a program átmásolja az előrejelzési projektből a munkarendelési sorhoz létrehozott munkarendelési projektbe. A projekttevékenység célja a munkarendeléssel kapcsolatos előrejelzések kezelése.

Beállíthat egy kötegelt feladatot úgy, hogy rendszeres időközönként frissítse a karbantartási feladattípusok alapértelmezésinek hivatkozásait, vagy manuálisan is futtathatja a feladatot. Kötegelt feladat létrehozásához vagy manuális frissítés futtatásához válassza az **Eszközkezelés** \> **Időszakos** \> **Megelőző karbantartás** \> **Karbantartási feladattípus alapértelmezések hivatkozásainak frissítése**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Eszközökhöz kapcsolódó karbantartási feladattípusok áttekintése

Miután létrehozta a szükséges karbantartási feladattípus alapértelmezések kombinációit a **Minden eszköz** lapon áttekintést kaphat az aktuális karbantartási feladattípus alapértelmezésről, amely egy adott eszközhöz kapcsolódik. Az áttekintés megmutatja az összes olyan karbantartási feladattípus alapértelmezéskombinációt, amely az eszközhöz kiválasztott eszköztípushoz használható. Ezek a kombinációk olyan kombinációkat tartalmaznak, amelyekben rendelkeznek karbantartási feladattípus változatokkal és a karbantartási feladattípus szakmákkal.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.
2. A listában válassza ki azt az eszközt, amelyhez karbantartásifeladattípus-kombinációk áttekintéséét meg szeretné jeleníteni.
3. A Művelet ablaktábla **Általános** lapjának **Kapcsolódó információk** csoportjában válassza a **Karbantartási feladattípusok** elemet.

    Az **Eszközök karbantartási feladattípusai** lap bal oldali ablakában látható a kiválasztott eszközhöz kapcsolódó összes karbantartási feladattípus-kombináció.

4. Válasszon ki egy karbantartási feladattípus-kombinációt, hogy megtekinthesse a kapcsolódó beállításokat a karbantartási ellenőrzőlistákhoz, előrejelzésekhez és eszközökhöz. A **Karbantartási feladattípus alapértelmezései** gyorslap **Részletek** szakasza a kiválasztott karbantartó feladattípus-kombinációhoz kapcsolódó kapcsolódó karbantartási ellenőrzőlisták, előrejelzett órák, cikkek stb. számát jeleníti meg.
5. A kiválasztott karbantartási feladattípus részleteinek megtekintéséhez válassza a **Karbantartási feladattípusok** elemet.

![Eszközkarbantartási feladattípusok oldala.](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Karbantartási feladatoktípusok előrejelzéseinek automatikus frissítése

Az Eszközkezelésben automatikusan frissítheti a karbantartási feladattípusok előrejelzéseinek módosításait az óraköltség, a cikköltségekhez és más kiadásokhoz, amelyek frissítve lettek más modulokban. Ilyen módon garantálhatja, hogy a karbantartási feladattípus-előrejelzések mindig a legfrissebb költségárakat használják.

1. Válassz az **Eszközkezelés** \> **Időszakos** \> **Előrejelzés** \> **Karbantartási feladattípus előrejelzésének frissítése** lehetőséget.
2. A **Karbantartási feladattípus előrejelzés frissítése** párbeszédpanelen a **Belefoglalandó rekordok** gyorslapon igény szerint megadhat kijelöléseket specifikus karbantartási feladattípusokhoz Válassza ki a **Szűrőt** majd válassza a **Kiválasztás** a lehetőséget, ha ki szeretne valamit jelölni.
3. A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.
4. Az előrejelzés frissítése az **OK** gombot választva indítható el.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]