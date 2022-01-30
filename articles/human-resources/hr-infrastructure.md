---
title: Dynamics 365 Human Resources infrastruktúra-egyesítés - 10.0.25-ös kiadás frissítése
description: Ez a témakör a Microsoft 10.0.25-ös kiadásának lépésekkel kapcsolatban tartalmaz tájékoztatást, amely az infrastruktúra-egyesítés első képességek Dynamics 365 Human Resources hullámát hozza.
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
ms.openlocfilehash: b785248c31c2cc4feb5cedd77264f36bfe927e0e
ms.sourcegitcommit: 10b85a09e8a550155a69aa2a8877a7c88b887242
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/20/2022
ms.locfileid: "8014490"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Dynamics 365 Human Resources infrastruktúra-egyesítés - 10.0.25-ös kiadás frissítése

A 10.0.25-ös verzió hozza az infrastruktúra-egyesítés első képességhullámát. Az infrastruktúra-egyesítés során a Microsoft egyesít majd a Pénzügyi és üzemeltetési Dynamics 365 Human Resources infrastruktúrával. A licenc azonban továbbra is független alkalmazásként lesz licencezve, például Dynamics 365 Finance a következőként:Dynamics 365 Supply Chain Management Az infrastruktúra-egyesítésről az infrastruktúra-egyesítési gyakori [Dynamics 365 Human Resources kérdéseknél olvashat bővebben](../human-resources/hr-infrastructure-merge-faq.md).

Az egyesítés a következőképpen biztosítja a konzisztenciát az Emberi erőforrások felhasználói számára:

- [A környezetkezelés és integráció konzisztens az Emberi erőforrások, a Pénzügy és a Műveletek alkalmazások között.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Környezetek kezelése Microsoft Dynamics a Lifecycle Services szolgáltatásban, problémakeresés és Regression Suite Automation Tool.
    - Egyetlen kódbázis van, ahol az Emberi erőforrásokhoz használható új funkciók a szokásos One Version frissítési folyamat részeként adták ki.
    - A frissítések, frissítések és gyorsjavítások környezetben alkalmazott alkalmazása egységes.

- [Az extensibility lehetőségek továbbfejlesztettek.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options.md)

    - A szükség szerint tovább Microsoft Power Platform bővítheti az eszközöket.
    - A funkciókat képernyőkre, táblákra, módszerekre és alkalmazásprogramozói felületekre (API-kra) is kiterjesztheti.
    - Entitásokat hozhat létre és bővíthet.

    A rendelkezésre álló kiterjesztési lehetőségekkel kapcsolatos további tudnivalókat lásd [a Dynamics 365 bővítményének](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) áttekintésében.

- [Egyetlen emberierőforrás-képességekből álló készletet hozhat létre a Dynamics 365-ben.](/dynamics365-release-plan/2021wave2/human-resources/create-one-set-human-resources-capabilities-within-dynamics-365.md)

    A 10.0.25-ös verzióban a csak az Emberi erőforrásokban meglévő funkcionális képességek elérhetővé teve a pénzügyi és műveleti infrastruktúra területén. Ahhoz, hogy az ügyfelek kihasználják ezeket a lehetőségeket a Pénzügyi és üzemeltetési környezetben, engedélyezni kell a funkciókezelésben az emberi erőforrások alábbi funkcióit.

    | Funkció neve | Áttekintés | Kiadási állapot | 
    |--------------|----------|----------------| 
    | Szolgálati évek számítása | A beállítási lehetőségek segítségével kiválaszthatja a szolgáltatási évek számításához **használt** dátumot. | Általánosan elérhető | 
    | Munkafolyamat használatának fejlesztései | Ez a funkció továbbfejlesztett felhasználói felületi funkciókat biztosít a munkafolyamatok benyújtásához és jóváhagyásához. | Általánosan elérhető | 
    | Teljesítményértékelések nyomtatása | A teljesítmény-áttekintéseket PDF formátumban is kinyomtathatja. | Általánosan elérhető | 
    | Egyéni hivatkozások a **Vezetői önkiszolgáló szolgáltatásban** | A Vezetői önkiszolgáló rendszer Kapcsolódó hivatkozások szakaszában megjelenő egyéni hivatkozásokat **lehet** **létrehozni**. | Általánosan elérhető | 
    | Vállalatközi kompenzációs nézet | A felhasználók az összes jogi személy között megtekinthetik a vezetői önkiszolgáló rendszer kompenzációs konstrukcióját anélkül, hogy **váltaniuk** kell a vállalatok között. | Általánosan elérhető | 
    | Több kompenzációs szint konfigurálása feladat szerint\*&dagger; | A feladatok mostantól több kompenzációs szintet támogatnak. | Általánosan elérhető | 
    | Feladatkezelés\* | Ellenőrzőlisták és feladatok hozhatók létre a be- és kijelentkezési, valamint az áttérési folyamathoz. | Előnézet | 
    | Korszerű alkalmazotti belépés | Ez a funkció frissített felhasználói felületi funkciókat biztosít a meglévő **Dolgozó** lapon. | Előnézet | 
    | Emberi erőforrások – felhasználói élményt érintő fejlesztések | Lásd a táblázatot a következő szakaszban.  | Előnézet | 

\* Ezt a funkciót be kell kapcsolva lennie az Emberi erőforrások felhasználói élmény **fokozása szolgáltatás** előtt.

&dagger; Ez a funkció az engedélyezése után nem tiltható le.

## <a name="human-resource-user-experience-enhancements"></a>Az emberi erőforrásokkal kapcsolatos felhasználói élmény fokozásai

| Funkció neve | Áttekintés | 
|--------------|----------| 
| Speciális hozzáférés | Az alkalmazottakhoz való hozzáférés korlátozva van a jogi személy alapján. | 
| Foglalkoztatás törlése | Lehetőség van alkalmazottak foglalkoztatásának törlésére. | 
| Állásajánlatok | Nyomon lehet követni a hasonló munkát igénylő, hasonló képzéssel, szakértelemmel, tudással és szakértelemmel rendelkező munkák csoportját. | 
| További foglalkoztatási mezők | A következő mezőket adott hozzá: **Foglalkoztatási** kategória, Foglalkoztatás **típusa és** Foglalkoztatási **állapot**. | 
| **Alkalmazás nélküli** dolgozók lap | A lapon azok a dolgozók vannak felsorolva, akiknek nincs munkarekordja. | 
| Beosztásdimenzió felhasználói felületének frissítése | Jobb felhasználói felület áll rendelkezésre a beosztásdimenziók jogi személyenkénti hozzárendelése során. | 
| Címváltozások **a Személyzeti kezelés** munkaterületen | Ez a funkció beszámol minden címváltozást, amely megadott számú nap alatt történt, az Emberi erőforrások paraméterei lapon **megadottak** szerint. | 
| Lejáró rekordok a **Személyzeti kezelés** munkaterületén | Ez a funkció felsorolja azokat a cikkeket, amelyek már lejártak vagy lejárnak a bizonyítványok, azonosítók, próbaidejük, szűrések és tesztek esetében. | 
| **Beosztáshierarchia ellenőrzési** oldala | A pozíciósor-hierarchiában körkörös hivatkozások ellenőrzése történik. | 
| Országspecifikus bérlistainformációk | A Dolgozó alkalmazás oldalán további bérlistamezők érhetők el, attól függően, hogy a jogi személy milyen országban vagy régióban alkalmazásban **áll**. | 
| Megfelelési jelentések továbbfejlesztései | Az EEO-1, a Vets 4212 és az OSHA300a rendszerben további jelentési lehetőségek érhetők el. | 
| A Személyzeti kezelés **munkaterület** frissítései | A rendszer frissíti a címváltozásokat és a lejáró rekordokat. Ezenkívül az új lapok felsorolják a dolgozói és a beosztási műveleteket. | 
