---
title: "A toborzási folyamat kezelése"
description: "Ez a cikk egy fogalom recruiters segítségével nyomon követheti a lépéseket a toborzási folyamatban, többek között a nyitott pozíciók hirdetése és a pályázók felvételéhez szükséges, pályázó és az alkalmazás nyomon követésére, kikérdezése pályázók és egy vagy több jelöltek ki kell töltenie a szervezeten belüli nyitott pozíciók kiválasztása."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 551e15ed31953d6e5fc99a1177c1310194ea95d0
ms.lasthandoff: 03/31/2017


---

# <a name="manage-a-recruiting-process"></a>A toborzási folyamat kezelése

Ez a témakör leírja a koncepció, amely a felvétellel foglalkozóknak a toborzási folyamat lépéseinek nyomon követésére használhatja, beleértve a nyitott pozíciók meghirdetése és a pályázók Toborzáshoz, pályázók és a pályázatok nyomon követésére, a kérelmező meghallgatása és töltse ki a nyitott pozíciók a szervezet egy vagy több jelöltek kiválasztása.

<a name="overview"></a>Áttekintés
--------

Toborzási projektek is megkönnyítik a lépéseket is hajtsa végre a jogi személyben nyitott pozíciók kitöltésekor. A kérelmező az a személy, aki foglalkoztatási a vállalatra vonatkozik.  Egy alkalmazás egy kérelmező kifejezés, amely a társaság által alkalmazott kamat, és egy toborzási projekthez adott megnyitása során kifejezett érdekét lehet kötni.  Egy kérelmező több alkalmazást az azonos jogalany vagy több vállalat lehet a szervezetben.

<a name="recruitment-projects"></a>Toborzási projektek
--------------------

Toborzási projektek lehetővé teszik a felvétellel foglalkozóknak nyomon követési kitöltését egy vagy több nyitott pozíciók ellen.  A toborzási projekt azonosítja az osztály és a feladat, amelynek egy vagy több beosztás nyitva. Toborzási projektek is nyomon követhető következő nyitott pozíciók vonatkozó információkat:
-   Nyitott pozíciók egyedi száma
-   A felvételi vezető és a beosztás egy másodlagos kapcsolattartó
-   A tranzakció jóváhagyásának dátuma
-   Jelentkezési határidő
-   Becsült kezdő dátum

A toborzási projektben a **Álláshirdetés** használja a **Alkalmazotti önkiszolgáló áruház** számára, hogy a nyitó. Meg szeretné jeleníteni a nyitó hozzá az alkalmazottakhoz, a toborzási projekt rendelkeznie kell egy **álláshirdetés**, a** megjelenítése az alkalmazotti önkiszolgáló szolgáltatás** mezőt be kell állítani az Igen, a **Jelentkezési határidő** egy jövőbeli dátumot kell megadni, és a toborzási projekt kell egy **projekt állapota** elindítva. A következő táblázat a lehetséges toborzási projekt állapota és azok leírását.

| **Status**    | **Indicates that…**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Ütemezve | Toborzás erőfeszítések készítenek elő.  Felvételi még nem kezdődött a projekt. |
| Elkezdve   | Alkalmazások most éppen elfogadható a betöltendő pozíciók ebbe a projektbe.                    |
| Befejezve  | Minden betöltendő pozíciók, a projekt ki van töltve.                                          |
| Érvénytelenítve  | A tábla szinkronizálása megszakadt.                                           |

Recruiters is lehet rögzíteni a **Media** hirdetése a nyitó külső értékesítési keresztül, valamint a nyomon követésére használt **Fejlesztések** a projekt vagy alkalmazások szemben.

<a name="applicants"></a>Pályázók
----------

A kérelmező az a személy, aki kell alkalmazni a vállalati projekt.  A kérelmezők a szervezetben, így a keresés tehetség nagy készlete minden jogi személy között vannak osztva. Megadhat és karban tarthat személyes információkat, állásinterjú dátumokat és időpontokat, referenciákat, kompetenciákat és a pályázó kérvényeit. Ha létrehoz egy pályázói rekordot, egy személyes rekord jön létre a pályázószámára a globális címjegyzékben. Használhatja a **Jelentkező** lap frissítése a következő globális címjegyzék adatait a pályázók számára:
-   Címadatok
-   Kapcsolattartási adatok
-   Azonosító adatok megtekintése
-   Név részletei
-   Személyes információk

## <a name="applications"></a>Alkalmazások
A megkapott alkalmazotti pályázatokból rögzíthet adatokat a **Jelentkezés** képernyőn. Az alkalmazás a kérelmező kifejezés érdekű feladat megnyitása a szervezetben.  Alkalmazás létrehozása a kérelmező már léteznie kell egy személy vagy a rendszerben.
Webes pályázó által beküldött alkalmazotti pályázatokat vagy kért azon alkalmazásai, amelyek egy Álláshirdetésre reagálva vittek be, illetve kéretlen pályázatok. A kért pályázatok automatikusan ahhoz a felvételi projekthez kerülnek, amelyikből a hirdetés létrejött. A toborzási projekt megadott kéretlen pályázatok tartoznak a **Toborzási** területe a **Emberierőforrás-paraméterek** oldalon.
### <a name="application-status"></a>Pályázat állapota

A pályázat állapota jelzi, hogy a pályázat hol áll a toborzási folyamatban. Az alábbi táblázat felsorolja a lehetséges toborzási projekt állapota, és azok leírását.

| Állapot    | Értelmezés...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Bevételezve  | Pályázat beérkezésének dátuma.                                                             |
| Visszaigazolva | A pályázónak egy értesítés lett elküldve a pályázat beérkezésének visszaigazolásáról.            |
| Interjú | A pályázónak egy interjúmeghívás lett elküldve.                                     |
| Elutasítás | A pályázónak egy elutasító levél lett elküldve.                                          |
| Érvénytelenítve  | A pályázónak egy visszavonási visszaigazolás lett elküldve. Ezt az értéket kézzel rendelik hozzá. |
| Alkalmazott  | A pályázónak egy felvételi ajánlat lett elküldve.                                         |

### <a name="correspondence-actions"></a>Levelezési tevékenységek

Egy **Alkalmazás** kapcsolattartási művelet határozza meg, hogy a dokumentum vagy e-mail sablont használó kommunikálni a a pályázatot benyújtó jelentkező. Társíthat **pályázati könyvjelzők** levelezés műveletek lehetővé teszi értékek az alkalmazásból, a kérelmező, interjú és a toborzási projekt lapok, a pályázókkal való kommunikáció.  **Alkalmazás e-mail sablonjainak** gyorsan küldése e-mailek kérelmet nyújt be egy bizonyos állapot és levelezést művelet kombinációja kérelmezőknek levelezés intézkedések hozhatók létre. Például egy visszaigazoló e-mailt küldhet az alkalmazások a **állapota** érkezett, és egy **levelezés művelet** Bevételezve.  Az e-mail elküldése után lehetősége van az alkalmazások állapotának automatikus frissítése.

## <a name="application-routing"></a>Pályázat útválasztása

Ha egy pályázatot több alkalmazottnak is át kell néznie, akkor a folyamat kezeléséhez a **Pályázat útválasztása**  oldalon létrehozhat egy alkalmazotti terjesztési listát.

## <a name="interviews"></a>Interjúk

**Pályázói interjúk** ütemezi a a **alkalmazások** oldalon.  Használja a **küldése az értekezlet adatait** a gombra kattintva az interjú ütemezési adatokat tartalmazó naptár fájl küldése a kérelmező és a kérdezőt.

## <a name="skill-mapping"></a>Szakértelem feltérképezése

**Szakértelem-feltérképezés** és **szakértelem-feltérképezési profilok** lehet egy nyitólap jó közelítést jelentkezőket azonosítására is használható.

## <a name="hiring-applicants"></a>Pályázók felvétele

Használja a **alkalmazások** pályázó lapra. Pályázó felvételekor az alkalmazás rekord állapotú lesz, **alkalmazott** és az új dolgozói rekordot a kérelmező személy globáliscímjegyzék rekordja kapcsolódik. A globális címjegyzék adatait az új dolgozó rekord módosításai is megjelennek a pályázó rekordját. Ez segít adatbevitel csökkentése, ha az új dolgozó valaha egy vállalaton belül más munkakörre érvényes.  Kattintson egy meglévő dolgozó felvétele új helyzetbe, **helyének módosítása** a a **pályázat állapota** vetett initiate az átviteli folyamat le.




