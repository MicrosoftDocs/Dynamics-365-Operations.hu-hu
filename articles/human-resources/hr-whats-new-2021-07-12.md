---
title: A Dynamics 365 Human Resources új vagy módosult elemei (2021. július 12.)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2021. július 12-re.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7fb922a35504b69aa8cc3d92cb981e8fb060290
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067586"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>A Dynamics 365 Human Resources új vagy módosult elemei (2021. július 12.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4353-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
|  A szolgáltatás évének megjelenítése váltása | |Ez a funkció lehetőséget nyújt különböző dátumok használatára a **Korszerű alkalmazotti belépés** oldalon és a **Személyek** lapon megjelenített szolgáltatási évek kiszámításához.  Ez elérhető lesz az [Emberi erőforrások paraméterei](/dynamics365/human-resources/hr-setup-parameters) között. |


### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.

| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 595871 | A Human Resources Névjegy ablaktáblája helytelen Dataverse terminológiát használ | A Common Data Service helyett a Dataverse márka bevezetésével a terminológia frissítve lett a Microsoft Dynamics 365 Human Resources információs ablakában (**Súgó és támogatás > Névjegy**). |
| 598676 | Az egyszerű alkalmazotti beviteli űrlap felülbírálásai hibát hozhatnak létre a Mentett nézet használata esetén| Ha a **Dolgozó lapon** be van kapcsolva az "Egyszerűsített alkalmazotti bejegyzés" funkció, az alkalmazás leállhat, ha egy mentett nézetben be van állítva a **Mindig meg van nyitva szerkesztésre** lehetőség. |
| 592344 |A dolgozók juttatásai szakasz a beosztásnak csak olvashatónak kell lennie, ha engedélyezve van a juttatások kezelése | A dolgozók juttatási információit örökölt juttatások funkcióival lehet létrehozni.  Ha engedélyezve van a juttatások kezelése, a mezők csak olvashatók lesznek. Ha a juttatások kezelése be van kapcsolva, és az **Örökölt juttatási űrlapok elrejtése** beállítása **Igen** a HR megosztott paraméterekben, akkor a **Dolgozók kompenzációja** lap el lesz rejtve. |
| 598617 | A **HcmDiscussion** űrlap aktiválási lapja végtelen ciklust okoz, amikor személyre szabásokat alkalmaznak | Ha mind a rács, mind a részletek nézetben be van kapcsolva a **M,indig megnyitva szerkesztésre**, akkor a felülbírált feladat metódus lapját aktiváló kód ütközik azzal a személyre szabási művelettel, ami meghatározza, hogy melyik vezérlő legyen fókuszban, és végtelen ciklust hoz létre. |
| 593553 | A Teljesítménynapló Naplódátum mezője UTC-formátumban jelenik meg | A teljesítménynaplók **Napló dátuma** mezője a rendszerdátum-beállításban megadott időzóna helyett UTC-időzónában jelenik meg, ami bizonyos időzónák esetében helytelen dátumot eredményez. |
| 586930 | Tevékenységek megnyitása a teljesítménycélokhoz egy teljesen eltérő rekordot nyit meg | Ha a Funkciókezelésben engedélyezve van a "Teljesítménynaplók kiterjesztett jelentésnézete" funkció, akkor a teljesítménycélok kiválasztása a kibővített jelentésekhez a **Csapatom** lapon a **Munkavállalói önkiszolgáló rendszerben** egy munkavállaló céljait nyitja meg a kiválasztott munkavállaló helyett. |
| 569959 |  A HcmPositionWorkerAssignmentV2 entitás nem társít dolgozót beosztáshoz | A felhasználók hibát kaptak, amikor egy beosztás-hozzárendelési rekordot adott hozzá az entitáson keresztül, és a közzététel nem sikerült. |
| 582259 | A VETS 4212 jelentés a 2020-as űrlap helyett a 2017-es űrlapot használja | 2020-as formátumra frissítve.  Az új formátum betöltéséhez menjen a **Jelentéskonfigurációk** helyre, és törölje VETS-4212 a jelentést a bal oldali oszlopban. Nyissa meg az **Elektronikus jelentéskészítés – Tárházak – HR erőforrások** menüt, és válassza a **Megnyitás** lehetőséget.  Válassza ki a **VETS-4212 PDF-nyomtatás**, majd az **Importálás** lehetőséget.|


## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|
|  A szabadságkezelés engedélyezése a távollét-kezelőnek | [A szabadságkezelés engedélyezése a távollét-kezelőnek](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Távollétkezelő szerepkör konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Melléklet követelményének konfigurálása szabadságtípusonként | [Melléklet követelményének konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Szabadság-mértékegységek konfigurálása szabadságtípusonként | [Szabadság-mértékegységek konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Az alkalmazottak kifizetésre készként való jelölésének engedélyezése | [Az alkalmazottak kifizetésre készként való jelölésének engedélyezése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Kifizetésre kész](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| Platform frissítése erre: 10.0.20 (44) | A 10.0.20-es verziófrissítés az ütemezés szerint a szolgáltatáskiadással, 2021. július 26-én indul el. A további tudnivalókat [lásd a Pénzügyi és üzemeltetési alkalmazások 10.0.20-as verziójának Platformfrissítései (2021. augusztus)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

