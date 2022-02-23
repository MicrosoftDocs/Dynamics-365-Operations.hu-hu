---
title: Szolgáltatások kezelése
description: Útmutató a Dynamics 365 Human Resources rendszerében található új szolgáltatások be- és kikapcsolásához.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9176e9519c3bf65ef7a4f1b5ae43dbeb411750f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418889"
---
# <a name="manage-features"></a>Szolgáltatások kezelése

A Microsoft Dynamics 365 Human Resources lehetőségeit folyamatosan bővítjük, és szeretnénk, hogy az ügyfelek a lehető leghamarabb használhassák az új funkciókat. Előnézeti funkciókat biztosítunk, amelyek már majdnem készen állnak arra, hogy általánosan elérhetőek legyenek, illetve kiterjedt tesztelésen mentek át. Az általánosan elérhető kibocsátás előtt egy utolsó visszajelzési és ellenőrzési kört végzünk az ügyfelekkel.

A Human Resources alkalmazásban található új funkciókkal kapcsolatos információkért lásd: [A Human Resources újdonságai](hr-admin-whats-new.md), illetve a [Dynamics 365 és a Power Platform kiadási tervei](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

A **Funkció-kezelés** munkaterülete az egyes kiadásokban kiadott funkciók listáját tartalmazza. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt. A funkciókezeléssel kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig. A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el. Amint az új funkciókat a **Funkciókezelés** munkaterületen látja, be lehet kapcsolni őket. Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.

Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva. A **funkciókezelés** munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé. Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják. Nem kapcsolhatja ki a kötelező funkciókat. Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.

## <a name="enable-or-disable-preview-features"></a>Előnézeti szolgáltatások engedélyezése vagy letiltása

Az előzetes funkciók eléréséhez előbb engedélyeznie kell azokat a környezetben. Az előzetes funkciók engedélyezése és letiltása környezetfüggő.

> [!IMPORTANT]
> Az előnézeti szolgáltatások csak **tesztkörnyezetekben** érhetők el. Az előnézeti funkciók bekapcsolása során a szervezet összes olyan felhasználója számára engedélyezi azokat, akik az adott környezetben vannak. A beállítás kikapcsolása során letiltja az előnézeti funkciókat, és hozzáférhetetlenné teszi azokat a felhasználók számára. Az előnézeti funkciók támogatása korlátozott a Human Resources alkalmazásban. Előfordulhat, hogy ezek kevesebb adatvédelmi és biztonsági intézkedést alkalmaznak, és nem szerepelnek a Human Resources szolgáltatásiszint-szerződésében (SLA). Ne használja az előnézeti funkciókat személyes adatok (azaz az Önt bármilyen módon azonosítani képes adatok) feldolgozására, illetve más jogi vagy szabályozási, megfelelési követelmények hatálya alá tartozó adatok feldolgozására.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. Válassza ki a **Funkció kezelése** csempét.

3. Az előnézeti funkció engedélyezéséhez válassza ki a listából, majd válassza az **Engedélyezés** lehetőséget. Az előnézeti funkció letiltásához válassza ki a listából, majd válassza a **Letiltás** lehetőséget.

## <a name="enable-or-disable-benefits-management"></a>Juttatáskezelés engedélyezése vagy letiltása

Ha engedélyezni szeretné a juttatások kezelését, használja ugyanezt az eljárást az [Előzetes funkció engedélyezése vagy letiltása](hr-admin-manage-features.md?enable-or-disable-preview-features) részben.

> [!IMPORTANT]
> Miután engedélyezte a Juttatások kezelését egy **Termelési** környezetben, azt nem lehet letiltani. A **Teszt** környezetekben azonban letilthatja a juttatások kezelését.

A juttatások kezeléskonfigurációjával és a használatával kapcsolatos további tudnivalókat lásd [Juttatáskezelés – áttekintés](hr-benefits-management-overview.md).

A juttatások kezelése helyettesíti a funkciót a **Juttatások** munkaterületen. Ha engedélyezi a Juttatások kezelése előnézeti funkciót, akkor a következő képernyők már nem érhetők el a **Juttatások** munkaterületen:

- **Juttatások**
- **Juttatás elemei**
- **Hozzájárulás-számítási mértékek**
- **Juttatásban való részesítés eredményei**
- **Juttatás lejáratának beállítása és bővítése – eredmények**
- **Juttatásra való jogosultság irányelvszabály-típusai**
- **Juttatásra vonatkozó jogosultsággal kapcsolatos irányelvek**
- **Jogosultsági események**

A képernyők adatait csak olvasható módban lehet megtekinteni. Ha szerkeszteni szeretné az adatokat, először le kell tiltania a Juttatások kezelését (csak a **Teszt** környezetekre érvényes).

## <a name="enable-or-disable-leave-and-absence"></a>Szabadság és távollét engedélyezése vagy letiltása

Ha engedélyezni szeretné a Szabadág és távollét funkciót használja ugyanazt az eljárást az [Előzetes funkció engedélyezése vagy letiltása](hr-admin-manage-features.md?enable-or-disable-preview-features) részben.

> [!IMPORTANT]
> A **Több szabadságtípust** nem lehet letiltani a Szabadság és távollét modulban, miután engedélyezte azt. Ez a **Teszt** és a **Termelési** környezetekre egyaránt vonatkozik.

Szabadság és távollét előzetes funkcióival kapcsolatos további tudnivalókat a [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features) részben találja.

## <a name="send-us-feedback"></a>Visszajelzés küldése

Szívesen vesszük visszajelzését bármely előnézeti funkcióval kapcsolatos tapasztalatairól. Javasoljuk, hogy a rendszeresen küldje el a visszajelzését a következő webhelyeken, amikor ezeket a funkciókat használja vagy bármilyen más funkciót használ:

- [Közösségi](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ez a webhely remek fórum, ahol a felhasználók megbeszélhetik az eseteket, kérdéseket tehetnek fel és segítséget kaphatnak a közösségtől.
- Tájékoztasson bennünket, hogy mely funkciókat szeretné látni a termékben, illetve milyen változásokat végezzünk a meglévő funkciókon. Ossza meg ötleteit a termékkel kapcsolatban: [Ötletek a Human Resources alkalmazással kapcsolatban](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
Ne adjon meg személyes adatokat (azaz az Önt bármilyen módon azonosítani képes adatokat) a visszajelzésében vagy a termékértékelés benyújtásakor. Előfordulhat, hogy az összegyűjtött információkat tovább elemzik, és azokat nem használjuk fel kérdések megválaszolására az alkalmazandó adatvédelmi törvényekkel összhangban. A programokhoz kapcsolódóan külön gyűjtött személyes adatokra a [Microsoft adatvédelmi nyilatkozat](https://privacy.microsoft.com/privacystatement) vonatkozik.

## <a name="see-also"></a>Lásd még

- [A Human Resources újdonságai](hr-admin-whats-new.md)
- [A Dynamics 365 és a Power Platform programverzióra vonatkozó kiadási tervek](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)