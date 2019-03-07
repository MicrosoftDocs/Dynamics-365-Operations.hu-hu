---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. december 14.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304610"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a>Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. december 14.)

[!include [banner](includes/banner.md)]

**Build 8.1.2085**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="changes"></a>Változások

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>US – ACA (Affordable Care Act) támogatás a 2018-as adózási évre, 1095-B és 1095 C űrlapok

Minden évben az alkalmazandó nagy munkáltatóknak (ALE-k) minden teljes munkaidős alkalmazottnak a rendelkezésére kell bocsátaniuk egy 1095-C-t. Ezenkívül, ha a munkáltató önálló biztosítási fedezetet kínál, rendelkezésre kell bocsájtania a teljes munkaidős vagy részmunkaidős alkalmazottaknak a 1095-C-t (ha ALE), és egy 1095-B-t (ha kis foglalkoztató), akikre kiterjed a munkaadó által ajánlott egészségügyi tervek egyike. Ez a funkció nyomtatható űrlapot biztosít a 1095-C és 1095-B esetében.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Az importálás során HcmPerfJournalEntity SubmittedByPersonId mezője nem lesz figyelembe véve

A teljesítmény-naplóbejegyzések importálásakor/exportálásakor az **Elküldte** mezőt a program figyelmen kívül hagyja. Ezzel a változtatással az **importált/exportált** érték azt az értéket tükrözi a táblában az exportálás során, hogy a rendszer importálását mikor frissíti a rendszer az importálási fájlban megadott értékkel.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>A „Szabadság és távollét” munkaterület Analitika lapja „OpenConnectionError” hibát jelenít meg a nem rendszergazdai szerepkörök esetén

A frissítés telepítését követően nem jelenik meg hiba, ha megnyitják az **Analitika** lapot a **Szabadság és távollét** munkaterületen.

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Az alkalmazotti önkiszolgáló rendszer, Beosztáshierarchia leásás a csempéről nem tudja beolvasni a szülőcsomópontot

Változtatás történt „A szülőcsomópont beolvasása nem sikerült” hiba kijavítására, amely akkor jelenik meg, ha egy beosztáshierarchiát testreszabtak, hogy egy meglévő munkaterületen jelenjen meg, és egy beosztást kiválasztanak a hierarchiában.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>A Beosztás oldal Bérlista lapjának megtekintéséhez rendszergazdának kell lenni

Változtatás történt, hogy a helyes biztonsági elemek szerepeljenek a meglévő jogosultságban: „Bérlista dolgozókra és beosztásokra vonatkozó részleteinek karbantartása”. Ezzel a módosítással alapértelmezés szerint a bérszámfejtő fér hozzá a Beosztás oldal Bérlista mezőihez.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Hiba a teljesítményáttekintés elküldésekor a vezetőnek, és a %Reviews.PerfPeriod% helyőrző van használatban a küldési utasításokban

Változtatás történt, amely javítja a „Null referencia” hibát a küldési utasításokban a %Reviews.PerfPeriod% helyőrző használatakor.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>A munkaerő Power BI jelentés hibát jelez, amikor az alkalmazott szolgálati idejének dátuma szökőnap

Ezt a változtatást a Power BI most már támogatja a szökőnapokat.

### <a name="integration-between-core-hr-and-attract"></a>Core HR és Attract integrációja

Változás történt, amely frissíti a Core HR és az Attract integrációját a pályázók felvételéhez kapcsolódóan. A felvételre váró pályázók láthatóvá tételéhez a **Személyzet kezelése** munkaterületen, a következő CDS for Apps (CD 2.0) entitások használatosak:

Álláspályázat
- Az állapot okát elfogadott ajánlatra kell állítani
-   A pályázókat és az álláslehetőségeket biztosítja

Pályázó
-   Jelölt adatokat biztosítja

Álláslehetőség
-   Az álláslehetőség-azonosítót és az álláslehetőség-résztvevőket biztosítja

Álláslehetőség-résztvevők
-   A munkaerő-felvételi vezetőt biztosítja

Egy jelöltnek a személyzet kezelésébe való felvétele után a jelöltet most már egy, a jelöltkártyán rendelkezésre álló új opcióval is ki lehet zárni.

## <a name="coming-soon"></a>Hamarosan

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Szabadság és távollét: jövőbeli szabadság és távolléti egyenlegek előrejelzése

Azzal a változással, amely lehetővé teszi az alkalmazottak számára a szabadságok előrejelzését és a jövőbeli szabdságkérelmek benyújtását anélkül, hogy ez befolyásolná a jelenlegi szabadságegyenlegeiket, a szabadságegyenlegek megjelenési módja is változik. 

A rendelkezésre álló egyenleg jelenleg megjeleníti a szabadságkérésre rendelkezésre álló időt, beleértve a könyveléseket a mai dátumig, és az összes jóváhagyott távollétkérelmet az idők végezetéig. 

Az előrejelzési képesség kiadásával a megjelenített egyenleg megváltozik: az aktuális szabadságegyenleg lesz, beleértve a könyveléseket a mai dátumig, és a kéréseket a mai dátumig. Az alkalmazottak és vezetők számára a frissített egyenlegek az alkalmazotti és a vezetői önkiszolgáló felületen jelennek meg a **Szabadság** kártyán és a **Szabadságegyenlegek** ablakban. A HR-vezetők a frissített egyenlegeket a **Személyek** munkaterületen és az alkalmazott **Alkalmazotthoz rendelt szabadságtervek** ablakában láthatják.

## <a name="known-issue"></a>Ismert probléma

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>A Finance and Operations integráció hibáinek leképezése

A következő problémákat azonosítottuk a Talent és a Dynamics 365 for Finance and Operations integrációjának aktuális sablonjában. Hamarosan új sablont teszünk közzé, amely minden létrehozott új integrációs projektekre alkalmazva lesz. A meglévő integrációs projektek esetén a feladat-hozzárendelésekhez lehet frissíteni. A frissített leképezésekért tekintse át a következő táblázatot. 

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

A frissített leképezéseknek a következő kép szerint kell kinézniük.

![Részlegek az üzemi egységbe feladat](./media/DepartmentMapping.png)


A feladatok a feladat részleteibe feladat esetében frissíteni kell a következő hozzárendeléseket.

| Meglévő forrásmező          | Új forrásmező                   |
| -------------------------------|------------------------------------|
| cdm_name (név)                | cdm_description (leírás)      |
| cdm_name (leírás)         | cdm_jobdescription(munkaköri leírás)|


A frissített leképezéseknek az alábbi kép szerint kell kinézniük.

![Feladatok a feladat részleteibe feladat](./media/JobMapping.png)

A dolgozók a munkához feladat esetében frissíteni kell a következő hozzárendeléseket.

| Meglévő forrásmező                 | Új forrásmező                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (1. e-mail-cím)   | cdm_primaryemailaddress (elsődleges e-mail-cím) |
| cdm_telephone1 (1. telefon)          | cdm_primarytelephone (elsődleges telefonszám)       |

A Nem mezőtranszformációt is frissíteni kell. Válassza ki a **fn** (függvény) leképezéstípust a nemhez, és frissítse a következő értékleképezéseket.

| CDS-érték                   | Finance and Operations érték                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Férfi                                             |
| 75440001                    | Nő                                           |
| 75440002                    | Egyik sem                                             | 
| 75440003                    | Nem meghatározott                                      |

A frissített leképezéseknek a következő képek szerint kell kinézniük.

![Dolgozók a munkához feladat](./media/WorkerMapping.png)

![Nem mezőtranszformáció](./media/WorkerTransform.png)
