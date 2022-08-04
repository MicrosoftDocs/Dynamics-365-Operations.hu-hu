---
title: A Dynamics 365 Human Resources új és módosult elemei 2021. június 22.
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2021. június 22-én.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61c457abf87ce2da554ddb1472512416159c4dca
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068424"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>A Dynamics 365 Human Resources új és módosult elemei 2021. június 22.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4258-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Tájékoztatás a foglalkoztatás nélküli dolgozókról – ha be van kapcsolva a speciális hozzáférés, és a Funkciókezelés funkcióban az **Összes, foglalkoztatás nélküli dolgozó megtekintése** funkció le van tiltva, akkor a foglalkoztatás nélküli dolgozóknál megjelenik egy üzenet. A rendszer arra fogja irányítani a felhasználót, hogy bekapcsolja az **Összes, foglalkoztatás nélküli dolgozó megtekintése** funkciót. | Nem alkalmazható| [Foglalkoztatás nélküli dolgozók](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Egyéni mező támogatása a Juttatások kezelése jogosultsági szabályokhoz | [Egyéni mezőtámogatás a jogosultságok feldolgozásához](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Jogosultsági szabályok konfigurálása](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Szabadságelhatárolási tranzakció auditálása | Nem alkalmazható | [Szabadságelhatárolási tranzakció auditálása](hr-leave-and-absence-accrue.md)|
| Szabadság és távollét munkafolyamat-élmény javításai | [Szabadság és távollét munkafolyamat-élmény javításai](https://go.microsoft.com/fwlink/?linkid=2147528) | [Távollét kérelmezése](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.

| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 583052 | A visszajelzést fogadó felhasználó szerkesztheti a kapott visszajelzést | Ha egy alkalmazott visszajelzést kap egy teljesítménynaplóról, a **Külső hivatkozás hozzáadása** lehetőséget választja, a képernyő szerkeszthetővé válik, lehetővé téve, hogy az alkalmazott szerkessze a kapott teljesítményre vonatkozó visszajelzést. |
| 522281 | Helytelen eredményekhez vezet, ha kiválasztja az alkalmazottak számát a kompenzációs struktúrában található Kompenzációkezelésben| Amikor a kompenzációs munkaterületről leásás történik a kompenzációs konstrukciókban, a megfelelő számú alkalmazott jelenik meg. |
| 580683 | Az Alkalmazottak és Vezetői szerepkörökhöz hozzárendelt felhasználók nem csatolhat jegyzeteket és nem frissítheti a Teljesítménynaplókat | Az Alkalmazottak és Vezetői szerepkörökhöz hozzárendelt felhasználók nem csatolhat jegyzeteket és nem frissítheti a Teljesítménynaplót. A felhasználó a következő hibát kapja: "Nem lehet rekordot létrehozni a Teljesítménynapló bejegyzésében (HcmPerfJournal). Biztonsági irányelv engedélye megtagadva." |
| 583077 | Egy alkalmazott távolléthez vagy távolléthez való vállalati naptárban való születési dátuma helytelen dátumot mutat | A felhasználók megtekinthetik az alkalmazottak születési dátumát a szabadsági és távolléti vállalati naptárban. |
| 586996 | A több vállalatot is elhagyó nézet funkció hatására az egyenlegek üresek lesznek, ha a hozzáférés csak egyetlen vállalatra van korlátozva | Ha a vállalatközi szabadság nézet engedélyezve van, a felhasználók megfelelően megtekinthetik az alkalmazottak jövőbeli szabadságegyenlegét. |
| 581014 | A vállalatközi szabadság és távollét nézet engedélyezése hibát okoz a jövőbeli egyenlegek megtekintésekor | A hibákat rögzítették, amikor a felhasználók a vállalatközi szabadságnézetben megtekintték a jövőbeli szabadságegyenlegeket. |
| 509404 | A részleg létszámelemzése nem veszi figyelembe az alkalmazottak részlegek közötti mozgását. | Amikor egy alkalmazott áttelepíti a részleget egy másik részleghez, a részleg létszámának adatai nem tükrözik azt a régi részleget, amelyről az alkalmazott átvált, ha a beosztás adatai az aktuális évben lejártak. |
| 584851 | A "Nincs" juttatás-jóváírási szabály soha nem ad meg jóváírást |A "Nincs" rugalmasidő-jóváírási szabály azt eredményezi, hogy az alkalmazottak nulla jóváírást kapnak a juttatási időszakban, függetlenül attól, hogy mikor vették fel őket. Ez úgy van rögzítve, hogy az alkalmazott teljes rugalmasidő-jóváírást kap, ha még a juttatási időszak kezdete előtt felvették őket, és ha az időszak kezdete után már nem, akkor nem. |
| 584897 | Az "Alapszintű külső funkció használata" feladat másolása hibát jelez | Az "Alapszintű külső funkció használata" feladat másolására tett kísérlet közben a felhasználó a következő hibát kapta: "Nem található UserDefinedAppHostDialogView azonosítójú objektum." |
| 575692 | Az elhatárolt szabadság és a távollét nem érhető el a függőben lévő dolgozók számára | A távollétek és távollétek könyvelése a jövőbeli felvételekkel futtatható, ha engedélyezve van a **Korszerű alkalmazotti belépés**. |
| 580110 | Vállalat hozzáadása a bérlista-integrációhoz alaphelyzetbe állítja az integrációt, hogy minden entitást használjon, még akkor is, ha a lehetőség be van állítva, hogy ne frissülje a projekt | Ha egy vevő entitásokat törölt, vagy módosította az adatprojektet a bérlista-integráció számára, és be van állítva, hogy megakadályozza a projekt automatikus frissítését, akkor egy új vállalat hozzáadása az integrációhoz figyelmen kívül hagyja a beállítást, és frissíti a projektet.  |
| 584518 |Juttatásfeldolgozási teljesítménybeli probléma regisztrálása | Ez a hiba az örökölt juttatások juttatásra való felvételének folyamatában teljesítménnyel kapcsolatos problémákkal foglalkozik. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| Platform frissítése erre: 10.0.19 (43) | A 10.0.19-es verziófrissítés az ütemezés szerint a szolgáltatáskiadással, 2021. június 28-én indul el. A további tudnivalókat [lásd a Pénzügyi és műveleti alkalmazások 10.0.19-es verziójának Platformfrissítései (június 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  A szolgáltatás évének megjelenítése váltása | Ez a funkció lehetőséget nyújt különböző dátumok használatára a **Korszerű alkalmazotti belépés** és a **Személyek** képernyőn megjelenített szolgáltatási évek kiszámításához.  Ez elérhető lesz az Emberi erőforrások paraméterei között. |
|  A szabadságkezelés engedélyezése a távollét-kezelőnek | [A szabadságkezelés engedélyezése a távollét-kezelőnek](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Rendelet mellékletei adott szabadságtípusokhoz | Ezzel a funkcióval a rendszergazdák előírhatják, hogy adott szabadságtípusokra vonatkozó kérelmek beküldésekor a felhasználóknak mellékletet kelljen csatolniuk. |
|  Szabadság-mértékegységek konfigurálása szabadságtípusonként | Ez a funkció lehetővé teszi a rendszergazdák számára, hogy minden egyes szabadságtípushoz beállítja a szabadságegységeket (órákat vagy napokat).  |
| Az alkalmazottak kifizetésre készként való jelölésének engedélyezése | [Az alkalmazottak kifizetésre készként való jelölésének engedélyezése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

