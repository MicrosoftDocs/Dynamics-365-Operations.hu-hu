---
title: Szolgáltatások kezelése
description: Útmutató a Dynamics 365 Human Resources rendszerében található új szolgáltatások be- és kikapcsolásához.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009249"
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

## <a name="preview-feature-benefits-management"></a>Előnézeti funkció: Juttatások kezelése

A juttatások kezelése rugalmas megoldást nyújt, amely a juttatások széles választékát támogatja, valamint egyszerű használhatóságot biztosít az alkalmazottak számára, amelyek bemutatják az ajánlatait. A juttatások kezeléskonfigurációjával és a használatával kapcsolatos további tudnivalókat lásd [Juttatáskezelés – áttekintés](hr-benefits-management-overview.md).

A juttatások kezelése helyettesíti a funkciót a **Juttatások** munkaterületen. Ha engedélyezi a Juttatások kezelése előnézeti funkciót, akkor a következő képernyők már nem érhetők el a **Juttatások** munkaterületen:

- **Juttatások**
- **Juttatás elemei**
- **Hozzájárulás-számítási mértékek**
- **Juttatásban való részesítés eredményei**
- **Juttatás lejáratának beállítása és bővítése – eredmények**
- **Juttatásra való jogosultság irányelvszabály-típusai**
- **Juttatásra vonatkozó jogosultsággal kapcsolatos irányelvek**
- **Jogosultsági események**

A képernyők adatait csak olvasható módban lehet megtekinteni. Ha szerkeszteni szeretné az adatokat, először le kell tiltania a Juttatások kezelése előnézeti funkcióját.

### <a name="benefits-management-known-issues"></a>Juttatáskezelés – ismert problémák

#### <a name="life-events"></a>Életesemények

Az életesemények feldolgozásakor a felhasználó hibaüzenetet kap:

A fedezet kezdő dátumának a *Tervidőszak kezdete* és a *Tervidőszak vége* között kell lennie. 

Az életesemény feldolgozása a várakozásnak megfelelően folytatódik.

#### <a name="eligibility-processing"></a>Jogosultság feldolgozása

Ha jogosultságokat futtat olyan juttatásokra, amelyek 1–5-szörös fizetést, a fizetés százalékát és a fix összeg fedezeti összegét használják, akkor a juttatási részletek dátumát az alkalmazott kezdési dátumára kell állítani az **Alkalmazási előzményekben**, a ledolgozott munkaórákkal, a fizetési gyakorisággal és az évi juttatások fizetési összegével együtt. Ha a dolgozóhoz fix kompenzáció van megadva, adja meg a ledolgozott órákkal együtt a fizetési gyakoriságot, és a program kiszámítja az éves fizetés összegét. Ha az alkalmazott bérezéses, akkor a ledolgozott órákat nem kell megadni. Javasoljuk, hogy új dolgozók létrehozásakor először adja meg a fix kompenzációt. A juttatás részleteire vonatkozó rekord frissítéséhez lépjen a következőre: **Dolgozó > Dolgozói előzmények > Foglalkoztatás részletei**. A dátum módosítása a dolgozók kezdő dátumára.

#### <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer

Az alkalmazottak ki tudnak választani egy olyan tervet, amelyre nem jogosultak, de amelyet meg tudnak tekinteni. Például: egy dolgozónak nincsenek függő felei, de kiválaszthat egy egészségügyi konstrukciót családi fedezet lehetőséggel.

A program nem számítja ki az alkalmazotti összeget az életbiztosítás fedezeti összegének frissítésekor. Például ha egy alkalmazottnak életbiztosítási csomagot ajánl fel, akkor egészen 50 000 dollár fedezeti összegig választhatnak 0,36 dollár/1000 dollár fedezeti költségen.  Amikor az alkalmazott frissíti a fedezet összegét, az alkalmazotthoz kapcsolódó költség nulla marad.

Olyan juttatási terv esetében, amely csak az adott tervtípus egyetlen beállítását teszi lehetővé, a felhasználó hibaüzenetet kap arra vonatkozóan, hogy a terv kiválasztása után megpróbálták-e lemondani a tervet. Például egy felhasználó kiválaszt egy egyészségügyi konstrukciót, és kosárba teszi. A felhasználó ezután kiválasztja a **Lemondás** lehetőséget, ezzel lemondva a másik egészségügyi konstrukciót. A felhasználó hibaüzenetet kap.

## <a name="preview-features-in-leave-and-absence"></a>Előnézeti funkciók a Szabadság és távollét pontban

A Szabadság és távollét pontban található előnézeti funkciók a következők:

- **Szabadság és távollét – naptár** – a szabadság és távollétre vonatkozó paraméterek az **Emberi erőforrások – paraméterek** pontból egy új képernyőre kerülnek: **Szabadság és távollét – paraméterek**. Az új képernyő tartalmaz egy új **Naptár** lapot. Ez az előnézet csak a paraméterek egy részhalmazát engedélyezi. Az új képernyőt a **Hivatkozások** lapról érheti el, amely a **Szabadság és távollét** munkaterületen található. A naptárak a következőket tartalmazzák:
  - **Vállalati naptár** – megjeleníti minden alkalmazott távolléti kérelmét. Az **Emberi erőforrás** szerepkörrel rendelkező személyek hozzáférhetnek ehhez a naptárhoz a **Hivatkozások** lapon, amely a **Szabadság és távollét** munkaterületen található.
  - **Vezetői csoport naptára** – megjeleníti az összes közvetlen jelentést a távolléti kérelmekkel kapcsolatban. A vezetők a naptárt a **Saját csapat** lapon érhetik el az alkalmazotti önkiszolgáló rendszeren, a **Szabadság és távollét** munkaterületen. 

- **Szabadság és távollét – ünnepnapokat tartalmazó naptárak** – a szabadságtípusok tartalmaznak egy új, **Ünnepnap** lehetőséget is, amely a munkaidő-naptárral együtt használatos. Az ünnepnapok és a leállások által meghatározott napok **Ünnepnap** típusúként vannak meghatározva a munkanapok létrehozásakor. Az elhatárolások feldolgozásakor megtörténik a naptárhoz hozzárendelt alkalmazottak korrekciója a munkanapra eső ünnepnapok esetén.

- **Szabadságelhatárolás ellenőrzése** – az új képernyő lehetővé teszi annak ellenőrzését az összes, illetve egyes alkalmazottak számára, hogy mikor dolgozták fel vagy törölték az elhatárolást. Ezt az új képernyőt a **Hivatkozások** lapról érheti el, amely a **Szabadság és távollét** munkaterületen található.

- **Szabadságelhatárolás törlése** – most már törölhet bizonyos szabadsági tervekre vonatkozó elhatárolási rekordokat. Ezt az új beállítást a **Hivatkozások** lapról érheti el, amely a **Szabadság és távollét** munkaterületen található. Az egyes alkalmazottak esetében ez a beállítás a **Szabadság és távollét** csoportosításban jelenik meg az alkalmazott profilján. 

- **A szabadságelhatárolás kerekítése** – a **Szabadság típusa** pont új beállításai meghatározzák a kerekítés típusát, valamint a kerekítés tizedesjegy-pontosságát az elhatárolási folyamat során. Az elhatárolások feldolgozása során a kerekítés és a pontosság az elhatárolási rekordokban is alkalmazandó. 

- **Több szabadságtípus konfigurálása egyetlen szabadságtervhez** – a szabadság típusú elhatárolási ütemezés új oszlopa lehetővé teszi a szabadságon és a távolléti tervben a különböző elhatárolási ütemezések megadását. Az előző **Szabadságtípus** mezőt eltávolították. Az alkalmazotti belépés során a szabadságtípusra vonatkozó egyenlegek ezentúl egy táblázatban jelennek meg, nem a képernyő felső részén.

  > [!IMPORTANT]
  > Ez a funkció nem kapcsolható ki, miután engedélyezte.

- **Az alkalmazott teljes munkaidő foglalkoztatással való egyenértékűség (FTE) alkalmazása az elhatároláshoz** – a szabadság elszámolási ütemezésének új oszlopa lehetővé teszi a FTE használatát az elhatároláshoz. Az elhatárolások feldolgozásakor az alkalmazás az alkalmazott elsődleges beosztását, valamint az arányosított elhatárolt összeg megállapításához meghatározott FTE-t használja.

  > [!NOTE]
  > Ez a funkció csak akkor érhető el, ha engedélyezi a **Több szabadságtípus konfigurálása egy szabadsági terven belül** opciót. 

## <a name="feedback"></a>Visszajelzés

Szívesen vesszük visszajelzését bármely előnézeti funkcióval kapcsolatos tapasztalatairól. Javasoljuk, hogy a rendszeresen küldje el a visszajelzését a következő webhelyeken, amikor ezeket a funkciókat használja vagy bármilyen más funkciót használ:

- [Közösségi](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ez a webhely remek fórum, ahol a felhasználók megbeszélhetik az eseteket, kérdéseket tehetnek fel és segítséget kaphatnak a közösségtől.
- Tájékoztasson bennünket, hogy mely funkciókat szeretné látni a termékben, illetve milyen változásokat végezzünk a meglévő funkciókon. Ossza meg ötleteit a termékkel kapcsolatban: [Ötletek a Human Resources alkalmazással kapcsolatban](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
Ne adjon meg személyes adatokat (azaz az Önt bármilyen módon azonosítani képes adatokat) a visszajelzésében vagy a termékértékelés benyújtásakor. Előfordulhat, hogy az összegyűjtött információkat tovább elemzik, és azokat nem használjuk fel kérdések megválaszolására az alkalmazandó adatvédelmi törvényekkel összhangban. A programokhoz kapcsolódóan külön gyűjtött személyes adatokra a [Microsoft adatvédelmi nyilatkozat](https://privacy.microsoft.com/privacystatement) vonatkozik.

## <a name="see-also"></a>Lásd még

- [A Human Resources újdonságai](hr-admin-whats-new.md)
- [A Dynamics 365 és a Power Platform programverzióra vonatkozó kiadási tervek](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)