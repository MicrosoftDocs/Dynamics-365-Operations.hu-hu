---
title: Integráció a Finance GYIK szolgáltatással
description: Ez a cikk bemutatja, hogy a rendszer milyen adatokat szinkronizál a Human Resources és a Finance integrációja során.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4f57e995dfcc04de8384d15f238c45290b3c3cbd
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067616"
---
# <a name="integration-with-finance-faq"></a>Integráció a Finance GYIK szolgáltatással


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a cikk megválaszolja a Dynamics 365 Human Resources Dynamics 365 Pénzügy integrálásakor szinkronizált adatokkal kapcsolatos gyakori kérdéseket.

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a>Szerkeszthetem az Dynamics 365 Talent alkalmazás felhasználóját a Power Apps-ben?

Nem. Ha módosítja a Human Resources alkalmazás felhasználóját, a Human Resources és a Dataverse integrációja sikertelen lehet. Az alábbi táblázat a Talent alkalmazásfelhasználó alapértelmezett beállításait mutatja be.

| Teljes név | Pályázat azonosítója | Azure AD Objektumazonosító | Alkalmazásazonosító URI |
| --- | --- | --- | --- |
| Dynamics365 for Talent | f9be0c49-aa22-4ec6-911a-c5da515226ff | 27fd8129-4b3c-43f7-b1bf-47495d3a049b | f9be0c49-aa22-4ec6-911a-c5da515226ff |

![A Talent alkalmazásfelhasználó alapértelmezett beállításai.](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>A programok minden adatokat szinkronizálják vagy csak bizonyos adatentitásokat?

A rendszer szinkronizálja az adatok egy részhalmazát. Az összes entitást a [Dynamics 365 Pénzügy integrációja című témakör tartalmazza](hr-admin-integration-finance.md).

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a>Miért nem látok semmilyen adatot szinkronizálva a Dataverse megoldásba?

Alapértelmezés szerint az Dataverse integráció ki van kapcsolva olyan új környezetekben, amelyekben nem szerepelnek a bemutató adatok. Alapértelmezés szerint a bemutatóadatokat tartalmazó új környezetekben be van kapcsolva, és az adatok szinkronizálása a környezet létesítése alkalmával kezdődik. Miután a környezet készen áll az adatok szinkronizálására, be lehet kapcsolni az integrációt. További információ: [A Dataverse integráció konfigurálása](hr-admin-integration-common-data-service.md).

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Létrehozhatok egy új hozzárendelést a sablonok használata nélkül?

Sablonok a kiindulási pontok. Saját sablon is létrehozhat, de a sablonra mindig szükség van , egy alkalmazásintegrációs projekt létrehozása során. Az Adatintegrátor (DI), a sablonokkal és a projektekkel kapcsolatos további tudnivalókat lásd: [Adatok integrálása a Microsoft Dataverse](/powerapps/administrator/data-integrator) for Apps szolgáltatásba.

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>Hozzárendelhetek-e pénzügyi dimenziókat átvitelre a Human Resources és a Finance alkalmazás között?

Pénzügyi dimenziók jelenleg nem szerepelnek a Dataverse szolgáltatásban, és ebből következően nem az alapértelmezett sablon részei. Ez az entitás tervezett, de jelenleg nincs a kiadási időterv.

Azon adatok esetében, amelyek léteznek a Finance alkalmazásban, de a Human Resources rendszerben nem, a Human Resources rendszer **Hivatkozások konfigurálása** funkciójával kapcsolja össze.

![Pénzügyi dimenziók leképezése.](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>Bizonyos esetekben, amikor az alkalmazottakat importálok, inaktív dolgozókként kerülnek be a Finance rendszerbe. Miért?

Ez a hiba akkor jelenhet meg, ha az alkalmazottnak nincs aktív foglalkoztatási rekordja a Human Resources rendszerben. Probléma megoldásához lépjen a **Személyzeti kezelése \> Alkalmazottak \> Foglalkoztatási előzmények \> Dátumkezelő** menübe, és győződjön meg arról, hogy van aktív foglalkoztatási adatok rekord.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Ha mezőknek csak egy elkészletét választom ki hozzárendelésre, a nem hozzárendelt mezők módosításai elindítják a szinkronizálást?

Adatszinkronizálás végrehajtási ütemezést követi. Az integráció átvesz egy rekordot, ha a rekord bármelyik mezője megváltozik, függetlenül attól, hogy az mező az integrációs hozzárendelés része-e.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Hogyan lehet átküldeni a csak az aktív dolgozók módosításait és a kilépett rekordokat nem?

A „Speciális lekérdezés” használatával szűrheti és átformálhatja a forrásadatokat a célhelyre történő továbbítás előtt.

![Aktív dolgozók speciális lekérdezése.](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>Meghatározhatom, hogy mely mezők legyenek átküldve a Finance rendszerbe egy adott entitáshoz?

Mezők hozzáadhatók vagy eltávolíthatók az integrációs feladatból. A Human Resources nem minden, a Dataverse-táblában lévő mezőt tölt ki.
A további adatok a Power Apps segítségével tölthetők ki.

![Mezők hozzáadása vagy eltávolítása az integrációs feladatból.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Kötegelt feladatként állítottam be az integrációt, de a Human Resources kapcsolata megszakadt a célrendszerrel. Hogyan lehet elküldeni a célrendszernek ugyanazokat a módosításokat?

Speciális beállítás nem szükséges a kivételek kezeléséhez. Az Adatintegrátor automatikusan észleli és jelenti a hibákat, amelyek felmerülnek a forrásnál és a célnál, és engedélyezi a manuális bejegyzéseket. Azonban nem teszi lehetővé a manuális adatjavítást. Ha adatfrissítésekre van szükség, az a forrásnál vagy a célnál kell történjen.

## <a name="can-i-set-up-bi-directional-integration"></a>Beállíthatók kétirányú integrációt?

Nem, az integráció jelenleg egy megoldás (emberi erőforrások a pénzügyhez és a műveletekhez). Azonban van egy alapértelmezett sablon, amelynek segítségével adatokat küldhet a Human Resources rendszerből a Finance alkalmazásba.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Rekordok törlését engedélyezhetem integráció részeként?

Nem, az Adatintegrátor nem rögzít adatátvitelre törölt rekordokat. Csak az adatok létrehozása és frissítése (UPSERT) érhető el jelenleg.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Futtathatok ismét egy a hibás végrehajtást? Ha igen, akkor elküldi teljes a fájlt, vagy csak a módosításokat?

Az Adatintegrátor első futása mindig teljes futás. További futások változáskövetésen alapulnak. Futtatás hibás végrehajtásakor, kigyűjti a futáshoz tartozó rekordokat, és elküldi a legfrissebb módosításokat a Dataverse szolgáltatásból.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>A projekt mentésekor a következő hibaüzenetet kapom: „Projektben hozzárendelési hibák vannak.” Mi a teendő?

Az integrációs kulcsok beállításának ellenőrzése, végezze el a szükséges módosításokat a beállításokon, majd frissítse a projekthez tartozó entitásokon.

Az alapértelmezett sablon használata esetén az integráció kulcsok automatikusan importálva lesznek. Ez akkor fordulhat elő, amikor új tevékenységeket adnak hozzá egy meglévő sablonhoz.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Ha N számú jogi személyem van, ahol a dolgozónak munkaviszonya van, kell létrehozni a hozzárendelést mindegyikhez?

Igen, az egyes jogi személyekhez a Finance alkalmazásban külön integrációs projekt szükséges az adatintegrációban.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Olyan adatokat kell átvinnem, amelyek nem szerepelnek a Microsoft által biztosított alapértelmezett sablonban. Megtehetem ezt?

Igen, mezőket lehetséges felvenni vagy eltávolítani a meglévő sablon esetében. A sablont módosíthatóm hogy tartalmazzon további adatokat más Dataverse-táblákból. Az entitásnak szerepelnie kell a Dataverse megoldásban, hogy bekerülhessen a sablonba. 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Új Finance és Human Resources környezeteket hoztam létre, és a következő hiba jelenik meg: „Az adatérték sérti az integritási megszorításokat.” Miért?

A hiba okai a következők lehetnek:

- Az adatok átvitele az ismétlődő rekordokok kivonását eredményezte a forrásnál (Dataverse).

- Az adatátvitel null értéket tartalmaz a pénzügyben és műveletekben kötelező mezőkben. Ellenőrizze , hogy a Dataverse adatai megfelelnek a Finance and Operations követelményeinek.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Ha a végrehajtási hibák vannak és az Alkalmazott azonosítója nem lett szinkronizálva, hogyan találom meg az előzményfeladatot, amelyben meghiúsult az alkalmazotti rekord?

Adatintegrátor több projektet hoz létre a Finance alkalmazásban. Az Adatintegrátor feladat és a Finance projekt közötti kapcsolat egy az egyhez.

Kövesse nyomon az időt az adatintegrátor végrehajtási előzményeiben és keresse a -1 indexű projektet a Finance alkalmazásban. Ha az Adatintegrátorban a feladat száma 9, az index a Finance alkalmazásban 8.

1. Rögzítse a tevékenységindexet az Adatintegrátorból (ebben a példában a „9”).

    ![A feladatindex rögzítése az Adatintegrátorból.](media/CaptureTaskIndex.png)

2. Kövesse nyomon a projekt végrehajtási idejét.

    ![A projekt végrehajtási idejének nyomon követése.](media/CaptureTimeOfExecution.png)

3. A Finance alkalmazásban azonosítsa be a -1 indexet. Ebben a példában a „8” utótaggal rendelkező projekt és az index „0” projekt végrehajtási ideje felel meg a 2. lépés végrehajtási idejének.

    ![Index azonosítása.](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>A Human Resources és a Finance integrációját követően nem látom a Human Resources alkalmazás adatait a Finance alkalmazásban. Mi a teendő?

A Finance integrációja két lépésből áll. Először ellenőrizze, hogy a Human Resources adatai frissítve vannak-e, és elérhetők-e a Dataverse megoldásban. Ez közel valós idejű szinkronizálási, és ellenőrizhető a Power Apps alkalmazásban az adattáblák közötti adatok megtekintésével.

![Adatok a Dataverse megoldásban.](media/DataInCDS.png)

Ha az adatok nem a várt módon jelennek meg a Dataverse megoldásban, győződjön meg róla, az entitást az integráció támogatja. További adatok felvételéhez a Dataverse megoldásba módosításara van szükség a Microsoft oldalán.

Ha az entitás támogatott, és az adatok elérhetők a Dataverse megoldásban, ellenőrizze, hogy a hozzárendelés megfelelő-e az Adatintegrátorban. Ha az integrátor leképezése megfelelőnek tűnik, ellenőrizze, hogy az adatkezelési feladatok sikeresen lefutottak-e. Hibák fordulhatnak elő a kötegelt feladatok végrehajtása során. Az Adatkezeléssel kapcsolatos további tudnivalókért lásd: [Adatkezelés](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>A saját alkalmazottak címei helytelenek a Finance alkalmazásban importálás után. Mit tegyek?

A **Helyazonosító** számsorozata ugyanazt a mintát használja a Human Resources és a Finance alkalmazásban is. A számsorozatnak mindkét oldalon egyedinek kell lennie, Dataverse így a címütközések nem ütköznek a pénzügyekbe és a műveletekbe származó adatok integrálása során.

A Human Resources alkalmazás végrehajtása során ellenőrizze, hogy a számsorozatok ne legyenek azonosak a Human Resources alkalmazásban és a Finance alkalmazásban találhatókkal. Ellenőrizze, hogy nem azonosak számsorozatok egyetlen esetben sem, amikor az adatokat mindkét rendszer kezeli.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Csatlakozókészlet létrehozása során nem látom a kapcsolatot a Kapcsolat legördülő listában. Mi a teendő?

A kapcsolatok létrehozásakor a Dynamics 365 Pénzügy és a Dataverse.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Munkaviszonyok szinkronizáláskor a következő hibaüzenet jelenik meg: „CompanyInfo_FK nem létezik” vagy „A 12/31/2154 11:59:59 pm' érték a 'Munkaviszony befejezésének dátuma' mezőben a kapcsolódó 'Munkaviszony' táblában nem található” Mit tegyek?

Győződjön meg róla, hogy a megfelelő jogi személyekhez rendel hozzá. Jogi személy szinkronizálása nem az alapértelmezett sablon része, így elvárt, hogy minden egyes jogi személy, amely szerepel a Human Resources és a Dataverse megoldásban, szerepeljen a Finance alkalmazásban is. Győződjön meg arról is, hogy a helyes jogi személyeket választja ki a társított Csatlakozókészletben.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>A projektem beállítását követően a Finance alkalmazáshoz tartozó mezőtársítás üres. Mit tegyek?

Frissítse a Finance adatentitásait az **Adatkezelés \> Keretrendszer paraméterei \> Entitásbeállítások \> Entitáslista frissítése** helyen. Ez eltart néhány percig, majd láthatóvá válnak azok a hozzárendelések. Ez a probléma új projektek létrehozásakor merülhet fel.

![Hiányzó mező-hozzárendelés.](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>További erőforrások

- Adatintegrátor(DI): 

  - [Adatok integrálása: Microsoft Dataverse](/powerapps/administrator/data-integrator)

  - [Hibakezelés és hibaelhárítás az Adatintegrátorban](/powerapps/administrator/data-integrator-error-management)

  - [Válasz DSR kérésekre a rendszer által generált naplókhoz a Power Apps, Microsoft Power Automate és Dataverse szolgáltatásban](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Adatkezelés:

  - [Adatkezelés](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

