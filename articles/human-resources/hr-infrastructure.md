---
title: Dynamics 365 Human Resources infrastruktúra összevonása – 10.0.25 frissítés
description: Ez a témakör a Microsoftról nyújt információkat Dynamics 365 Human Resources A 10.0.25-ös kiadás, amely a képességek első hullámát hozza el az infrastruktúra egyesítésében.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a80bedd0224f1e31dfec4e9f4c39ad1ed75d7f2f
ms.sourcegitcommit: 948978183a1da949e35585b28b8e85a63b6c12b1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2022
ms.locfileid: "8024567"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Dynamics 365 Human Resources infrastruktúra összevonása – 10.0.25 frissítés

A 10.0.25-ös kiadás hozza a képességek első hullámát az infrastruktúra egyesítésében. Az infrastruktúra-összevonás során a Microsoft Dynamics 365 Human Resources összevonják a Finance and Operations infrastruktúrával. Azonban továbbra is önálló alkalmazásként lesz engedélyezve, mint pl Dynamics 365 Finance és Dynamics 365 Supply Chain Management. Az infrastruktúra-egyesítéssel kapcsolatos további információkért lásd: [Dynamics 365 Human Resources infrastruktúra összevonás GYIK](../human-resources/hr-infrastructure-merge-faq.md).

Az összevonás a következő módokon biztosítja a következetességet a humánerőforrás-felhasználók számára:

- [A környezetkezelés és az integráció konzisztens a Human Resources és a Finance and Operations alkalmazások között.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Környezetek kezelése Microsoft Dynamics Életciklus-szolgáltatások, problémakeresés és Regression Suite Automation Tool.
    - Egyetlen kódalap létezik, ahol a Human Resources új funkcionalitása a szokásos One Version frissítési folyamat részeként jelenik meg.
    - A frissítések, frissítések és gyorsjavítások környezetekre való alkalmazása egységes.

- [A bővíthetőségi lehetőségek javultak.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options.md)

    - Továbbra is használhatja Microsoft Power Platform szükség szerint bővíthető eszközök.
    - A funkciókat űrlapokkal, táblákkal, metódusokkal és alkalmazásprogramozási felületekkel (API-k) bővítheti.
    - Létrehozhat és kiterjeszthet entitásokat.

    Az elérhető bővítési lehetőségekről további információért lásd: [A Dynamics 365 bővíthetőségének áttekintése](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Hozzon létre egy humánerőforrás-képességkészletet a Dynamics 365-ben.](/dynamics365-release-plan/2021wave2/human-resources/create-one-set-human-resources-capabilities-within-dynamics-365.md)

    A 10.0.25-ös kiadásban a Finance and Operations infrastruktúrán elérhetővé tették azokat a funkcionális képességeket, amelyek csak a Human Resources részlegnél léteztek. Ahhoz, hogy az ügyfelek kihasználhassák ezeket a lehetőségeket egy Finance and Operations környezetben, a következő humánerőforrás-szolgáltatásokat kell engedélyezni a Feature Management alkalmazásban.

    | Funkció neve | Áttekintés | Kiadási állapot | 
    |--------------|----------|----------------| 
    | Szolgálati évek számítása | Egy beállítási lehetőség lehetővé teszi a beállításhoz használt dátum kiválasztását **Több éves szolgálat** számítás. | Általánosan elérhető | 
    | Munkafolyamat használatának fejlesztései | Ez a funkció továbbfejlesztett felhasználói élményt biztosít a munkafolyamat-beküldések és jóváhagyások során. | Általánosan elérhető | 
    | Teljesítményértékelések nyomtatása | A teljesítményértékeléseket PDF formátumban nyomtathatja ki. | Általánosan elérhető | 
    | Egyéni linkek be **Menedzser önkiszolgáló** | Létrehozhat egyéni hivatkozásokat, amelyek megjelennek a **Kapcsolódó linkek** szakasza **Menedzser önkiszolgáló**. | Általánosan elérhető | 
    | Vállalatközi kompenzációs nézet | A felhasználók megtekinthetik a kompenzációs terveket **Menedzser önkiszolgáló** minden jogi személyre kiterjedően, cégváltás nélkül. | Általánosan elérhető | 
    | Konfiguráljon több kompenzációs szintet munkánként\*&dagger; | A munkák mostantól többféle kompenzációs szintet támogatnak. | Előnézet | 
    | Feladatkezelés\* | Létrehozhat ellenőrző listákat és feladatokat a belépési, kilépési és átállási folyamathoz. | Előnézet | 
    | Korszerű alkalmazotti belépés | Ez a funkció frissített felhasználói élményt biztosít a meglévőkhöz **Munkás** oldalon. | Előnézet | 
    | Emberi erőforrások – felhasználói élményt érintő fejlesztések | Lásd a táblázatot a következő részben.  | Előnézet | 

\* Ezt a funkciót be kell kapcsolni, mielőtt a **Az emberi erőforrások felhasználói élményének javítása** funkció.

&dagger; Ez a funkció nem tiltható le az engedélyezés után.

## <a name="human-resource-user-experience-enhancements"></a>Emberi erőforrás felhasználói élmény fejlesztései

| Funkció neve | Áttekintés | 
|--------------|----------| 
| Foglalkoztatás törlése | Törölheti a munkavállaló munkaviszonyát. | 
| Munkacsaládok | Nyomon követheti a munkák egy csoportját, amelyek hasonló munkát foglalnak magukban, és hasonló képzést, készségeket, ismereteket és szakértelmet igényelnek. | 
| További foglalkoztatási területek | A következő mezők kerültek hozzáadásra: **Foglalkoztatási kategória**, **típus**, és **A foglalkoztatás jellege**. | 
| **Munkavállalás nélkül dolgozók** oldalon | Egy oldalon azon munkavállalók listája látható, akiknek nincs munkaviszonya. | 
| A pozíciódimenzió felhasználói élményének frissítése | Továbbfejlesztett felhasználói élményt nyújt a pozíciódimenziók jogi személyenkénti hozzárendelése. | 
| A cím megváltozott **Személyzeti menedzsment** munkaterület | Ez a szolgáltatás megadja az összes címváltozás számát, amely a megadott számú napon belül történt, ahogy az a **Emberi erőforrás paraméterek** oldalon. | 
| Lejáró rekordok **Személyzeti menedzsment** munkaterület | Ez a szolgáltatás lejárt vagy lejárt tételek listáját tartalmazza a tanúsítványok, azonosítások, próbaidőszakok, szűrések vagy tesztek tekintetében. | 
| **Pozícióhierarchia érvényesítése** oldalon | Ellenőrzi a körkörös hivatkozásokat a pozíciósor-hierarchiában. | 
| Országspecifikus bérszámfejtési információk | További bérszámfejtési mezők állnak rendelkezésre a **Munkás foglalkoztatás** oldal, attól függően, hogy a jogi személy melyik országban vagy régióban dolgozik, ahol a munkavállalókat foglalkoztatják. | 
| Megfelelőségi jelentési fejlesztések | További jelentési lehetőségek állnak rendelkezésre az EEO-1, a Vets 4212 és az OSHA300a esetében. | 
| Frissítések a **Személyzeti menedzsment** munkaterület | Frissítések történtek a címváltozások és a lejáró rekordok nyomon követése érdekében. Emellett az új lapok felsorolják a dolgozói és pozícióműveleteket. | 
