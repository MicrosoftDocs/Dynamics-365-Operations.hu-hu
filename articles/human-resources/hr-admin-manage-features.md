---
title: Funkciók kezelése Human Resources rendszerben
description: Ez a témakör bemutatja a funkciókezelés szolgáltatást, valamint azt, hogy hogyan használhatja azt.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61e40f7177a1c8cf3d60a9a991ecbb0ed4d93aa1
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414633"
---
# <a name="manage-features-in-human-resources"></a>Funkciók kezelése Human Resources rendszerben

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources lehetőségeit folyamatosan bővítjük, és szeretnénk, hogy az ügyfelek a lehető leghamarabb használhassák az új funkciókat. Előnézeti funkciókat biztosítunk, amelyek már majdnem készen állnak arra, hogy általánosan elérhetőek legyenek, illetve kiterjedt tesztelésen mentek át. Az általánosan elérhető kibocsátás előtt egy utolsó visszajelzési és ellenőrzési kört végzünk az ügyfelekkel.

A Human Resources alkalmazásban található új funkciókkal kapcsolatos információkért lásd: [A Human Resources újdonságai](hr-admin-whats-new.md), illetve a [Dynamics 365 és a Power Platform kiadási tervei](/dynamics365/release-plans/?panel=products1#pivot=products).

A **Funkció-kezelés** munkaterülete az egyes kiadásokban kiadott funkciók listáját tartalmazza. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt. A funkciókezeléssel kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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

Az ezeken az oldalakon található információkat csak olvasási módban tekintheti meg. Ha szerkeszteni szeretné az adatokat, először le kell tiltania a Juttatások kezelését (csak a **Teszt** környezetekre érvényes).

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
- [A Dynamics 365 és a Power Platform programverzióra vonatkozó kiadási tervek](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
