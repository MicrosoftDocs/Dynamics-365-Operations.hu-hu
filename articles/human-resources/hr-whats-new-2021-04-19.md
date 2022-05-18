---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban, 2021. április 19.
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. április 19-i kiadásban.
author: marcelbf
ms.date: 04/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6734069b1448999c62a8c538f97d786fc10995e5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685742"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban, 2021. április 19.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4113-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Platform frissítése erre: 10.0.17 (41) | -- | [A Pénzügy és műveletek alkalmazások 10.0.17-es verziójának platformfrissítései (2021. április)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Egyéni mezők támogatása a Juttatások kezelése űrlapokon | [Egyéni mező támogatása a juttatások kezelésében](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Juttatáskezelés áttekintése](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás |  Leírás |
| --- | --- | --- |
| 552164 | **Mentett nézet** az **Alkalmazott önkiszolgáló rendszer > Nyitott tanfolyamok** nem működnek napirendet tartalmazó tanfolyamokhoz | Ha a Nyitott tanfolyamokon (ESS) egy Mentett nézetet használnak, és valamelyik tanfolyamhoz tartozik napirend, akkor a nézet a továbbiakban nem fog több sort megjeleníteni a tanfolyamnál |
| 560614 | **Juttatások > Életesemény beállításai** megjeleníti az elemleírás dokumentációjának és a kód viselkedésének eltérését. | Módosított elemleírások az **Életesemény beállításokban** a helyes viselkedés megjelenítéséhez. |
| 560616 | **Juttatások > Életesemény beállításai** szerkeszthetők a dolgozói juttatási tervben, de ez nem befolyásolja a változásokat. | Az életesemény beállítás frissített viselkedése az elemleírás-dokumentációnkénti függésbeállításoktól függően engedélyez vagy letilt. |
| 565054 | Nem lehet megtekinteni a **Munkanélküli dolgozók** listáját, ha a **Speciális hozzáférés** be van kapcsolva. | Ez a kiadás kijavítja azt a problémát, amikor a **Speciális hozzáférés** be volt kapcsolva, akkor csak a rendszergazdák tekinthették meg a **Munkanélküli dolgozók** listáját. Mivel ez a javítás biztonsági módosítás, ezért be kell jelentkeznie a Funkciókezelésbe. Ha a funkció be van kapcsolva, akkor azokkal a szerepkörökkel rendelkezők, akik hozzáférnek az űrlaphoz, látni fogják a tartalmat, még akkor is, ha a speciális hozzáférés be van kapcsolva. További információért lásd: [Munkanélküli dolgozók](hr-personnel-workers-without-employment.md). |
| 570586 | A szabadságkérelem megerősítése sikertelen lesz, ha a foglalkoztatás a dolgozóhoz tartozó összes szabadságtervben a legutolsó tranzakció előtt ér véget. | A munkaviszony befejeződése után a szabadságkérelem megerősítése az alkalmazott szabadságtranzakciói alapján nem lesz sikertelen.|
| 570783 | A vállalatközi szabadság Emberi erőforrások osztott paramétereiben való engedélyezése és tiltása módosítja, hogy az egyetlen vállalatban alkalmazottak milyen szabadságra vonatkozó kéréseket látnak. | Az egyetlen vállalatban alkalmazottak nem látnak változtatást a időkorlátban, ha a paraméter engedélyezve van vagy le van tiltva. |
| 572343 | Ha a Vállalatközi szabadság nézet funkció engedélyezve van, nem jelenik meg a kötelező okkód. | Ha a Vállalatközi szabadság funkció engedélyezve van, megjelenik a várt okkód. |
| 573676 | Nem lehet **Időszakot** hozzáadni a **Juttatások kezelése > Hivatkozások > Juttatási tervek** lehetőséghez. | El lettek hárítva a hibák ott, ahol az **Időszakot** nem sikerült hozzáadni vagy frissíteni a meglévő **Juttatási terv** űrlapon. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Szabadság és távollét munkafolyamat-élmény javításai | [Szabadság és távollét munkafolyamat-élmény javításai](https://go.microsoft.com/fwlink/?linkid=2147528) | [Távollét kérelmezése](hr-employee-self-service-request-time-off.md)|
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |
| Platform frissítése erre: 10.0.18 (42) | A 10.0.18-es verziófrissítés az ütemezés szerint a szolgáltatáskiadással, 2021. május 17-én indul el. A további tudnivalókat [lásd a Pénzügyi és üzemeltetési alkalmazások 10.0.18-as verziójának Platformfrissítései (2021. május)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Egyéni mező támogatása a Juttatások kezelése jogosultsági szabályokban  | [Egyéni mezőtámogatás a jogosultságok feldolgozásához](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
