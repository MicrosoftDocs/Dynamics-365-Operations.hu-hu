---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. december 6.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f3d53440c5d19dd52fbab17305c3e99a73e570be
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742586"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-6-2018"></a>Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. december 6.)

[!include [banner](includes/banner.md)]

**Build 8.1.2071**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.


## <a name="platform-update-22"></a>22-es platformfrissítés

### <a name="export-up-to-1-million-rows-to-excel"></a>Legfeljebb 1 millió sor exportálása az Excel programba

Az Excel programba történő exportálás funkció most már beállítható úgy, hogy a felhasználók legfeljebb 1 millió sort exportálhassanak a Talent rácsaiból, ami jelentős növekedés az előző, 10 000 soros korláthoz képest. 

### <a name="restyled-personalization-toolbar"></a>Újratervezett személyre szabási eszköztár

A személyre szabási eszköztárat újraterveztük a 22-es platformfrissítéshez, hogy a felhasználók könnyebben szabhassák testre a Talent megoldást. Az alábbi módosítások történtek: 

-  Minden egyes személyre szabása eszköz neve most már megjelenik az ikon mellett, ami lehetővé teszi, hogy a felhasználók gyorsan felismerjék az őket érdeklő eszközt.
-  Most már az aktuális eszköz használatának leírása is megjelenik, amelyek segítségével a felhasználók könnyebben megérthetik, hogyan lehet végrehajtani a szükséges személyre szabást.  
-  A teljes személyre szabási eszköztárat mozgatni lehet a képernyőn húzással adott területre az eszköztár bal szélén. Ez lehetővé teszi a felhasználóknak, hogy testre szabjanak elemeket, amelyeket korábban eltakart az eszköztár.   

### <a name="optimized-is-one-of-filtering-experience"></a>Optimalizált „egyike a következőknek” szűrési élmény

Az „egyike a következőknek” szűrési operátor rendelkezésre áll a legtöbb mezőben a szűrés panel és a rács fejléc legördülő listák használata esetén. Az operátor lehetővé teszi a mező szűrését több érték alapján. Az „egyike a következőknek” operátor új és továbbfejlesztett lehetőségei a 22-es platformfrissítéssel érhetők el. További információ: [Optimalizált „egyike a következőknek” szűrési élmény](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Listák beillesztése az Excel programból a szűrőmezőkbe az „egyike a következőknek” operátorral.

Egyes feladatok esetén a felhasználók Exceles értéklistával rendelkezhetnek, amelyet az adatok szűrésére szeretnének használni a Talent megoldásban. Például előfordulhat, hogy egy emberierőforrás-felhasználó azonosít egy, a rendszerben további kutatást igénylő alkalmazottcsoportot egy jelentésben, és hasznos lenne, ha a felhasználó közvetlenül az Excel programból másolhatná ki a listát a Talent szűrőmezőjébe.

A 22-es platformfrissítéstől kezdve az „egyike a következőknek” operátor a szűrőpanelen és a szűrés rácsoszlopban felismeri az Excel programból kimásolt listákat, amelyek így közvetlenül a szűrőmezőkbe illeszthetők be. Ez magában foglalja az Excel különböző soraiból és oszlopaiból kimásolt értékek gyűjteményét. A funkcióval kapcsolatos további tudnivalókért lásd: [Listák beillesztése az Excel programból a szűrőmezőkbe az „egyike a következőknek” operátorral](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>Előnézetben

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Egyesült királyságbeli bérlista-integráció konfigurálása a Talent és a Dayforce között

Az Egyesült Királyságban előnézetben elérhető Microsoft Dynamics 365 for Talent és a Ceridian Dayforce közötti integráció. További tudnivalókért lásd a következő témakört: [Bérlista-integráció konfigurálása a Talent és a Dayforce között](https://docs.microsoft.com/dynamics365/unified-operations/talent/configure-payroll-integration).

## <a name="coming-soon"></a>Hamarosan

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Szabadság és távollét: jövőbeli szabadság és távolléti egyenlegek előrejelzése

Azzal a változással, amely lehetővé teszi az alkalmazottak számára a szabadságok előrejelzését és a jövőbeli szabdságkérelmek benyújtását anélkül, hogy ez befolyásolná a jelenlegi szabadságegyenlegeiket, a szabadságegyenlegek megjelenési módja is változik. 

A rendelkezésre álló egyenleg jelenleg megjeleníti a szabadságkérésre rendelkezésre álló időt, beleértve a könyveléseket a mai dátumig, és az összes jóváhagyott távollétkérelmet az idők végezetéig. 

Az előrejelzési képesség kiadásával a megjelenített egyenleg megváltozik: az aktuális szabadságegyenleg lesz, beleértve a könyveléseket a mai dátumig, és a kéréseket a mai dátumig. Az alkalmazottak és vezetők számára a frissített egyenlegek az alkalmazotti és a vezetői önkiszolgáló felületen jelennek meg a **Szabadság** kártyán és a **Szabadságegyenlegek** ablakban. A HR-vezetők a frissített egyenlegeket a **Személyek** munkaterületen és az alkalmazott **Alkalmazotthoz rendelt szabadságtervek** ablakában láthatják.

## <a name="other-changes"></a>Egyéb változtatások 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>A dolgozó beosztás-hozzárendelési rekordja nem frissül a felmondási kóddal

Végrehajtottunk egy módosítást, amely felveszi az okkódot a beosztás-hozzárendelési rekordba a felmondási folyamat során.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>A használatban lévő személyzeti szám ellenőrzéséhez további részletek szükségesek

További információk jelennek meg, amikor a számsorozatok használatban vannak, a problémák jobb megértéséhez, amikor nem hozhatók létre új számok.
 
### <a name="attachments-buttons-not-available-for-workers"></a>A mellékletek gombok nem állnak a dolgozók rendelkezésére

Módosításokat végeztünk a mellékletek kijavítására. Új melléklet hozzáadásakor egy dolgozóhoz, az **Új** és **Szerkesztés** gombok már elérhetők, amikor a dolgozó ablakában nyitva vannak az adatterületek. 

## <a name="known-issues"></a>Ismert problémák

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>A Finance and Operations integráció hibáinek leképezése

A következő problémákat azonosítottuk a Talent és a Finance and Operations integrációjának aktuális sablonjában. Hamarosan új sablont teszünk közzé, amely minden létrehozott új integrációs projektekre alkalmazva lesz. A meglévő integrációs projektek esetén a feladat-hozzárendelésekhez lehet frissíteni. A frissített leképezésekért tekintse át a következő táblázatot. 

>[!NOTE]
> A Munkabeosztások a szülő munka-hozzárendelésbe feadat nem integrálja az adatokat. Ezt a hibát jelenleg vizsgáljuk. Az aktuális leképezésben nincs megkerülő megoldás. 

A részlegek az üzemi egységbe feladat esetében frissíteni kell a következő hozzárendeléseket.

| Meglévő forrásmező          | Új forrásmező |
| -------------------------------|------------------|
| cdm_description (leírás)  | cdm_name (név)  |

Egy további leképezést is kell megadni. Válassza ki az utolsó **Nincs** mezőt a következő leképezések hozzáadásához.

| Forrásmező                   | Célmező    |
| -------------------------------|----------------------|
| cdm_description (leírás)  | NAMEALIAS (NAMEALIAS)|

A frissített leképezéseknek az alábbiak szerint kell kinézniük.

![Részlegek az üzemi egységbe feladat](./media/DepartmentMapping.png)


A feladatok a feladat részleteibe feladat esetében frissíteni kell a következő hozzárendeléseket.

| Meglévő forrásmező          | Új forrásmező                   |
| -------------------------------|------------------------------------|
| cdm_name (név)                | cdm_description (leírás)      |
| cdm_name (leírás)         | cdm_jobdescription(munkaköri leírás)|


A frissített leképezéseknek az alábbiak szerint kell kinézniük.

![Feladatok a feladat részleteibe feladat](./media/JobMapping.png)

A dolgozók a munkához feladat esetében frissíteni kell a következő hozzárendeléseket.

| Meglévő forrásmező                 | Új forrásmező                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (1. e-mail-cím)   | cdm_primaryemailaddress (elsődleges e-mail-cím) |
| cdm_telephone1 (1. telefon)          | cdm_primarytelephone (elsődleges telefonszám)       |

A Nem mezőtranszformációt is frissíteni kell. Válassza ki a **fn** (függvény) leképezéstípust a nemhez, és frissítse a következő értékleképezéseket.

| Common Data Service érték   | Finance and Operations érték | | ------------|------------------ -----------| | 75440000    | Férfi                         | | 75440001    | Nő                       | | 75440002    | Nincs                         | | 75440003    | Nem meghatározott                  |

A frissített leképezéseknek az alábbiak szerint kell kinézniük.

![Dolgozók a munkához feladat](./media/WorkerMapping.png)

![Nem mezőtranszformáció](./media/WorkerTransform.png)

