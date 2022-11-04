---
title: Human Resources ügyféláttelepítési GYIK
description: Ez a cikk megválaszolja a Microsoft Dynamics 365 Human Resources pénzügyi és műveletek egyesített infrastruktúrába való áttelepítésével kapcsolatos gyakori kérdéseket.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0e11d26ebe084762a8616c8aa0aa041a87306473
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734358"
---
# <a name="human-resources-customer-migration"></a>Az Emberi erőforrások m<

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>Hogyan tervezik Dynamics 365 Human Resources az ügyfelek a pénzügyi és a műveleti infrastruktúrára való áthelyezést?

A művelet a Microsoft két vevőkategóriáját Dynamics 365 Human Resources érinti, ezek módosításaival gondoskodhat arról, hogy a legújabb pénzügyi és műveleti infrastruktúra területének megfelelőek leselkednek:

- Azok a vevők, Dynamics 365 Human Resources akik a Dynamics 365 más műveleti alkalmazásait használják, de nem használják őket
- Azok a vevők, akik mind Dynamics 365 Human Resources a Dynamics 365 Pénzügy, Dynamics 365 Supply Chain Management, vagy Dynamics 365 Commerce Dynamics 365 Project Operations

A vevőknek a kategóriától függetlenül az újonnan létrehozott környezetbe kell áthelyezni az adatokat a pénzügyi és a műveleti infrastruktúra területén, és ellenőrizniük, hogy az egyesítés sikeresen befejeződött-e.

Tovább haladva az Dynamics 365 Human Resources alkalmazásnak saját pénzügyi és műveleti környezete lesz, amely el van választva a többi műveleti alkalmazástól. Ily módon a vevők az aktuális adatok egyesítése nélkül is kihasználhatják a lehetőségeket. A Microsoft eszköz- és üzenetkészlet-környezetet biztosít, amelyek segítségével az ügyfelek tesztelni és ellenőrizni tudják az adatáttelepítést, mielőtt éles környezetbe lépnek. Az eszköz egy közel automatizált folyamatot tesz lehetővé, amely 2022. augusztus és november között lesz elérhető.

Azok a vevők, akik más alkalmazásokat is használnak a pénzügyi és műveleti infrastruktúrában, lehetőség van arra, hogy az emberi erőforrások adatait összevonják egy meglévő környezettel. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>Mikor fogják áthelyezni a vevőket a pénzügyi és a műveleti infrastruktúrába?

Az egyes vállalatváltások a vállalat aktuális konfigurációitól és a pénzügyi és műveleti infrastruktúrára való ugrásra való alkalmasságtól függenek. Javasoljuk, hogy az ügyfelek a Microsoft-partnerük segítségével határozzák meg a legjobb útvonalat.

- **A** Dynamics 365 Pénzügy Dynamics 365 Human Resources modult az Emberi erőforrások modult használják szervezetei a szokásos Egyverziós frissítési folyamat részeként engedélyezhetik az új képességeket. A tervek szerint az új funkciók 2022 januártól általánosan elérhetővé válnak.
- Azok a szervezetek, amelyek hozzáférhetnek Dynamics 365 Human Resources az infrastruktúra-egyesítés egyesítéséhez használható eszközhöz. A Microsoft az átállás során együtt fog működni a vevőkkel, hogy megakadályozza a szolgáltatás bármilyen megszakítását. A vevőknek 12 hónapjuk lesz az átállásra attól az időponttól kezdve, amikor az áttelepítési eszköz elérhetővé válik.
- Azok a szervezetek, amelyek mind Dynamics 365 Human Resources **az** Emberi erőforrások modult használják, áthelyezheti önálló emberierőforrás-infrastruktúrájukat a pénzügyi és a műveleti infrastruktúrába. Egy másik lehetőség az egyesítési eszköz használata a környezetek egyetlen környezetbe való beállításának érdekében. Nincs meg az a követelmény vagy időkeret, amely a két környezet egyesítéséhez szükséges.

A naprakész információkért rendszeresen ellenőrizze a kiadási [terveket](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>Így is szükség van az ügyfelek egyéni integrációjára az Dynamics 365 Human Resources Emberi erőforrások modul és az ügyfél között?

- Azok a vevők, akiknek mind Dynamics 365 Human Resources a pénzügyi, mind az üzemeltetési infrastruktúra környezete integrálva van, az egyesítést követően is integrálni kell a két környezetet.
- Azok a vevők Dynamics 365 Human Resources, akik úgy döntik, hogy környezetüket elkülönítik a meglévő pénzügyi és műveleti alkalmazáskörnyezettől, továbbra is integrálni kell a környezeteket ahhoz, hogy az adatokat mindkét környezetben elérhetővé t t használják.
- Az ügyfelek továbbra is az Data Integrator segítségével másolhatják az adatokat a két környezet között. Az adatokat egyetlen környezetbe az áttelepítés után egyesítő vevőknek már nem kell integrálni őket, mivel minden adat egyetlen adatbázisban lesz.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>Automatikusan áttelepítik a vevői ISV-megoldásokat?

A független szoftverszállítói (ISV) megoldásoknál az áttelepítési élmény a megoldás integrációs módszerétől függően eltérő lehet. A Microsoft szorosan együttműködik az isvekkel, hogy a pénzügyi és a műveleti infrastruktúra területének megfelelő átmenetet biztosítson. Számos isv. megoldás a <a0/10/<a1 Dataverse><a2/<a2/<a2/Microsoft Power Platform Ezek a megoldások a környezet és Dataverse a Dynamics 365 Human Resources környezet közötti integrációtól Dataverse függenek. Az Dataverse integráció értékcsökkenése az infrastruktúra-egyesítés részeként folyamatban van. A tervek szerint a pénzügyi és az üzemeltetési infrastruktúrában az integráció funkcióinak helyére új kétírásos leképezések állnak Dataverse majd be.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>Hogyan fogja érinteni az adatintegrátort Dynamics 365 Human Resources, amely az adatokat más Dynamics 365-alkalmazások között mozgatja?

Miután a vevők átlépnek a pénzügyi és az üzemeltetési infrastruktúrára, az adatokat továbbra is integrálni kell a két környezet között. Az ügyfelek továbbra is az Adatregrátor segítségével hajthatja végre ezeket az adatáttelepítési feladatokat. Azok a vevők, Dynamics 365 Human Resources akik úgy tervezik, hogy környezetüket elkülönítik a meglévő pénzügyi és műveleti alkalmazáskörnyezettől, továbbra is integrálni kell az adatokat a két környezet között. Azok az ügyfelek, akik a két környezetet egyetlen környezetbe egyesik, a két környezet közötti integrációra már nincs szükség.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>Hogyan lesznek áthelyezve Dynamics 365 Human Resources az adatok a pénzügyi és a műveleti infrastruktúra között, illetve az Dataverse áttelepítés után?

A jelenlegi Dataverse integráció a Dynamics 365 Human Resources Dataverse pénzügyi és a műveleti infrastruktúra részeként elavult. A tervek szerint két írásos leképezésekkel lehet leképezni a pénzügyi és műveletentitásokat a táblákra Dataverse. Az ügyfeleknek el kell dönteniük, hogy milyen kettős írású leképezések szükségesek a megvalósításukhoz. Javasoljuk, hogy a virtuális táblákat használja az integrációhoz és az isV-megoldásokhoz, Dataverse hacsak nincs konkrét üzleti szüksége az adatok másolására az üzleti logika futtatása érdekében.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>Hogyan érinti az áttelepítés a Dataverse bővítményeket Dynamics 365 Human Resources?

A vevőknek a termelési környezet áttelepítése előtt át kell áttelepítése őket egy üzenetdoboz-környezetbe. Amikor az ügyfelek áttelepítik a üzenetdoboz-környezetüket, létre kell hozniuk egy másolatot a Dataverse környezetükről, hogy kapcsolatot teremtsen az új pénzügyi és műveleti áttelepített környezethez. Javasoljuk, hogy az ügyfél másolja az adatokat és a megoldásokat is a környezetbe, hogy azok megegyeznek a vevő aktuális termelési környezetével.

Amikor az ügyfelek készen állnak a Dynamics 365 Human Resources termelési környezet áttelepítésére, a Microsoft automatikusan át fogja áttelepítése az adatbázist és az Azure Blob tárolót. Az áttelepített adatbázis és tárolás a pénzügyi és műveleti infrastruktúra új környezetére mutat ugyanannak a termelési környezetnek Dataverse. Dataverse Ahhoz, hogy az adatokat továbbra is másolni lehet a másikba, az ügyfélnek engedélyeznie kell minden olyan kettős írásos leképezését, amely az integrációhoz, a bővítményekhez és a beépített ISV-megoldásokhoz szükséges Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>Automatikusan Microsoft Power Platform fognak működni azok Dynamics 365 Human Resources az összetevők, amelyekre felépítettek az infrastruktúra-áttelepítés befejezése után?

Azok az alkalmazások, amelyek létre vannak hozva Power Apps, és Power Automate Microsoft Power Platform Dataverse a más testreszabások például bővítmények. A vevői termelési környezetek áttelepítése során Dataverse nincs hatással a környezetre, beleértve a bővítményeket is. Az alkalmazásoknak, folyamatoknak és a Power Microsoft Platform egyéb testreszabott beállításainak további konfigurálás nélkül is működniük kell.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>Mi történik a virtuális táblaentitások Dataverse számára az Dynamics 365 Human Resources áttelepítés során?

Ha az ügyfelek a pénzügyi Dynamics 365 Human Resources és műveleti infrastruktúrába áttelepítése történik, Dataverse akkor a környezet kapcsolatban marad az aktuálisan kapcsolódó környezettel Dynamics 365 Human Resources. A Dataverse környezetben létrehozott virtuális táblák további konfigurációk nélkül is működni fognak. Előfordulhat, hogy a virtuális táblákat Dataverse újra létre kell hozni olyan környezetben, amely a vevő meglévő pénzügyi és műveleti környezetéhez kapcsolódik.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>Hogyan fognak működni a pályázókövetési rendszer (ATS) API-t, bérszámfejtési API-t, Dataverse Dynamics 365 Human Resources virtuális táblákat vagy Dataverse más entitásokat használó integráció a webes API-munkához az infrastruktúra-egyesítés befejezése után?

Ha az ügyfelek a pénzügyi Dynamics 365 Human Resources és műveleti infrastruktúrába áttelepítése történik, Dataverse akkor a környezet kapcsolatban marad az aktuálisan kapcsolódó környezettel Dynamics 365 Human Resources. A webes API-val Dataverse kialakított integrációk az áttelepítés befejezése után is működni fognak.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>Szervezetünk egyéni biztonsági beállításokat konfigurált a következőben:Dynamics 365 Human Resources Az infrastruktúra-áttelepítés befejezése után is alkalmazza a rendszer?

Igen, az egyéni biztonsági konfigurációk bekerülnek az adatáttelepítésbe.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>Automatikusan áttelepítik a Dynamics 365 Human Resources munkafolyamatokat?

Igen, a munkafolyamat-konfigurációk, a munkafolyamat-előzmények és az aktuális folyamatban lévő munkafolyamatok áttelepítve lesznek az egyesített infrastruktúrába.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>Automatikusan áttelepíti a rendszer Dynamics 365 Human Resources a mentett nézeteket?

Igen, a mentett nézetek át lesznek telepítve az egyesített infrastruktúrába.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>Automatikusan elérhetők lesznek az infrastruktúra-egyesítést Dynamics 365 Human Resources követően engedélyezett funkciók?

- Az Emberi erőforrások modult **igénybe vevő** vevők esetében Dynamics 365 Human Resources a funkciókezelés kezeli a csak a modulban elérhető funkciókat. Ezek a funkciók alapértelmezés szerint nem lesznek engedélyezve. Minden olyan funkció dokumentálva lesz, amelyet alapértelmezés szerint engedélyezni kell.
- A szolgáltatást igénybe vevő vevők Dynamics 365 Human Resources számára elérhetővé válik az infrastruktúra szolgáltatásai. A nem elérhető funkciók dokumentálva lesznek. Az egyesített infrastruktúrában minden Dynamics 365 Human Resources, az aktuális környezetben engedélyezett funkciókezelési kulcs engedélyezve lesz. További tájékoztatás: [Funkciókezelés – áttekintés](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>Mi történik a BYOD-adatbázisokkal az áttelepítés során?

A saját adatbázis (BYOD) végrehajtásához szükséges konfigurációk importálása és exportálása a pénzügyi és műveleti infrastruktúrába lesz áttelepítve.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>Hatással van az Azure-régióra az ügyfélkörnyezet áttelepítésekor?

A Dynamics 365 Human Resources környezet ugyanabban az Azure-régióban marad az áttelepítéshez. Ha egy környezetet másik Azure-régióba kell áthelyezni, akkor az ügyfeleknek az áttelepítés befejezése után követniük kell az új régióba való áttelepítés szokásos lépéseit.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>Mi történik az Azure adatkapcsolatokkal az áttelepítés során?

Minden olyan exportálás, amely a Pénzügyi és műveletalkalmazások Azure Data Exportálás szolgáltatására van konfigurálva, az áttelepítés után is ugyanazt a konfigurációt fogja karbantartani.

> [!NOTE]
> A két írásos leképezések írását engedélyezni kell ahhoz, hogy az adatok írása folytatódjon az emberi erőforrások környezetből a következőbe Dataverse:

Azok a vevők, akik az emberi erőforrások adatait exportálni kívánják az adatfájlba, engedélyezhetik ezt a funkciót, miután befejeződött a pénzügyi és műveleti infrastruktúrára való áttelepítés. További információ az Adatközpontok [– Azure architektúraközpontjában található](/azure/architecture/data-guide/scenarios/data-lake).

Az ügyfelek több pénzügyi és műveleti környezetet kapcsolhat ugyanannak az adatkapcsolatnak. A környezetek azonban egy másik mappára és tárolóra mutatnak. A környezeteket később egyesíteni tervező vevőknek gondosan meg kell tervezni a megközelítésüket.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>Milyen áttelepítés szükséges, ha egy vevő éppen használja az Emberi erőforrások modult?

Az Emberi erőforrások **modult** Dynamics 365 Human Resources használják azok a vevők, akik az "Egy verzió" frissítési folyamaton keresztül a környezetükre alkalmazott új funkciókat fogják használni. Az ügyfelek elvárják, hogy az új funkciók minden frissítésben elérhetővé válnak a környezetükben. A vevők a funkciók engedélyezésére a funkciókezelést használják. Az ügyfelek úgy tervezik, hogy az új funkciók érvényességét a már érvényes folyamatok segítségével ellenőrzik, és a környezetük más frissítéseit is ellenőrzik.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>Mi történik a külső rendszerekkel való egyéni integrációval?

A vevőknek át kell áttelepítéseiket a pénzügyi és műveleti környezetbe. Mivel ennek a környezetnek a végpontja különbözik, előfordulhat, hogy az ügyfélnek frissítenie vagy módosítania kell az integrációt, hogy az új környezetre mutasson. Ez a feladat elsősorban kézi folyamat lesz, és a szükséges változtatások az integráció felépítésétől függenek. Az ügyfélnek a Microsoft-partnerével együtt kell működnie, hogy megállapítsa az integrációk mozgatása legjobb megközelítését.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>Mi történik a bővítményekben Microsoft Power Platform,Dataverse ha a vevők egyesítik a környezetet egy Dynamics 365 Human Resources meglévő pénzügyi és műveleti környezettel?

Ha az Dynamics 365 Human Resources Dataverse ügyfelek úgy döntenek, hogy egy környezetet és egy meglévő pénzügyi és műveleti környezetet egyetlen példányban egyesítenek az áttelepítés után, Dataverse akkor környezetüket az egyesítési folyamat részeként együtt kell összevonni. Ehhez a feladathoz az Power Apps szükséges, hogy minden, a használattal és minden egyéb testreszabással létrehozott alkalmazást újratelepítésre váltsa a rendszer az új környezetben.

## <a name="what-will-happen-to-documents-during-the-migration"></a>Mi történjen a dokumentumok az áttelepítés során?

Amikor a vevők a pénzügyi Dynamics 365 Human Resources és műveleti infrastruktúrába kerülnek, a dokumentumok megmaradnak a meglévő dokumentumtárolóban, és automatikusan hozzárendelik őket a pénzügyi és műveleti infrastruktúra új környezetéhez.

A későbbi verzióban új entitások fognak rendelkezésre állni. A módosítás után azok a vevők, akik úgy döntik, Dynamics 365 Human Resources hogy környezetüket egy meglévő pénzügyi és műveleti környezettel egyesíteni fogják, exportálni tudják a dokumentumokat, és áthelyezik őket a meglévő környezetbe.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Mi történik az áttelepítés után a konfigurált kötegelt feladatokkal Dynamics 365 Human Resources?

A kötegelt feladatokat újra kell konfigurálni a pénzügyi és műveleti környezetben. A vevőknek ki kell értékelniük az egyes kötegelt feladatokat, és össze kell hasonlíta azokat a pénzügyi és műveleti környezetben lévő kötegelt feladatok aktuális listájával. A vevőknek a kötegelt feladatok két készletének egyesítésekor szintén elemezniük kell a teljes köteg ütemezését, hogy meghatározzák, kell-e módosításokat eszközlni a köteg ütemezésében, a prioritásokban vagy a kötegcsoportokban.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>Milyen hatással lesz az áttelepítés az LCS-projektre Dynamics 365 Human Resources?

A vevőknek Microsoft Dynamics új Lifecycle Service (LCS) projektet kell létrehozniuk, **és** a projektek típusaként a pénzügyi és üzemeltetési alkalmazásokat kell kiválasztaniuk termékként és implementációként. Ezenkívül egy LCS-projekt létrehozásakor új mező érhető el az alprojekttípushoz. A vevőknek ki kell választaniák Dynamics 365 Human Resources a meglévő emberi erőforrások LCS-projektnek a pénzügyi és műveleti infrastruktúrába való áttelepítésére vonatkozó beállítást.

A pénzügyek és műveletek LCS-projektjeinek jellemzői különböznek az emberi erőforrásokkal kapcsolatos LCS-projektek jellemzőitől.

Az új vevőknek a következő feladatokat kell elvégezniük az élőben való ugráshoz:

- Projekt-onboarding befejezése.
- A módszertan teljes befejezése.
- Előfizetés becslésének kitöltése.
- Az élő készenlét folyamatának befejezése.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>Hogyan történik az üzletifolyamat-modellező áttelepítése?

A vevőknek exportálniük kell az üzletifolyamat-modelltárukat az Emberi erőforrások LCS-projektből, és azt be kell importálni a pénzügyi és műveleti LCS-projektbe. Ezenkívül a vevőknek frissíteniük kell az alkalmazás súgóbeállítását, hogy az új LCS-projektre mutassák.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>Hogyan fogja érinteni a szolgáltatásfrissítési folyamatot az áttelepítés?

Az áttelepítés után a vevők nagyobb rugalmasságot fognak kapni az alkalmazások életciklusának kezelése és a szolgáltatások frissítései számára. A szolgáltatásfrissítések már nem lesznek automatikusan alkalmazva az emberi erőforrások környezetére. Ehelyett a szolgáltatás az Egyverziós szolgáltatás frissítési folyamatait és funkcióit követi, és engedélyezi az LCS-n keresztüli frissítések konfigurációs beállításait.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>A vevők jogosultak lesznek a FastTrack támogatásra az infrastruktúra-egyesítéssel kapcsolatban?

A Microsoft még mindig azt határozza meg, hogy milyen eszközök és erőforrások érhetők el a FastTrack eszközből az egyesítés segítésében.

## <a name="licensing-impact"></a>Licencelési hatás

A licenceléssel kapcsolatos további tudnivalókat lásd az infrastruktúra-egyesítési [Dynamics 365 Human Resources témakörben](hr-infrastructure-merge.md#licensing).
