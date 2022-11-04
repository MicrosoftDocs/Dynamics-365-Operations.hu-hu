---
title: Dynamics 365 Human Resources infrastruktúra-egyesítés – áttekintés
description: Ez a témakör a Microsoft infrastruktúra-egyesítését Dynamics 365 Human Resources írja le.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f79ef3ed5db7583eb44b99e49c010778ce8524d1
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2022
ms.locfileid: "9732770"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Dynamics 365 Human Resources infrastruktúra-egyesítés 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics Emberi erőforrások 365

A Microsoft Dynamics 365 Human Resources olyan eszközöket biztosít, amelyek segítik a HR-csoportokat a szervezeti agitás növelésében, az alkalmazotti tapasztalatok átalakításában és a HR-programok optimalizálásában, hogy olyan munkahelyet hozzanak létre, ahol az alkalmazottak és a vállalkozás növekedhet. További tudnivalók:Dynamics 365 Human Resources [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/)

- **Az alkalmazotti tapasztalat átalakítása.** A fő teljesítmény megőrzése a vezetők és alkalmazottak révén a kapcsolódó önkiszolgáló tapasztalatokkal, amelyek az együttműködés és a növekedés jegyében állnak elő.
- **HR-programok optimalizálása.** A működési költségek csökkentésének és a személyek által központú szabadság- és távollét,idő-, juttatás- és kompenzációkezelési programok létrehozása.
- **Szervezeti agilitység növelése.** A HR számára a vállalat által megkövetelt kézügyesség Dataverse Microsoft Power Platform engedélyezése az adatok használatával és a személyek adatainak központosított kezelésével, valamint az adatok egyszerű kiterjesztésével Dynamics 365 Human Resources.
- **Munkaerő-információkat lehet leásni.** Adatvezérelt döntéseket hoz az olyan, az adatok elemzésére és megjelenítésére való képességen keresztül, amelyek bármilyen eszközön elérhetők a felhasználói irányítópultokon.

## <a name="human-resources-infrastructure-merge"></a>Az emberi erőforrások infrastruktúra-egyesítésének egyesítése

Dynamics 365 Human Resources Olyan önálló alkalmazás, amely jelenleg más infrastruktúrát használ, mint a többi pénzügyi és műveletalkalmazás, például a Dynamics 365 Pénzügy vagy Dynamics 365 Supply Chain Management a. Az infrastruktúra-egyesítés ugyanazon Dynamics 365 Human Resources infrastruktúra-egyesítést fogja lehetővé venni, mint a többi pénzügyi és műveletalkalmazás.

Az emberi erőforrásokkal kapcsolatos infrastruktúra-egyesítésről [az Egyesítés – HR-ajánlatok egyesítésével kapcsolatban olvashat bővebben](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). A gyakran feltett kérdésekre adott válaszok az emberi [erőforrás-infrastruktúra egyesítési gyakori kérdéseknél tartalmaznak választ](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Vevőáttelepítés és vevőegyesítés

Az infrastruktúra-egyesítés részeként az Emberi erőforrások alkalmazás minden képessége elérhetővé válik a pénzügyi és a műveleti környezetekben. Az ügyfelek a Lifecycle Microsoft Dynamics Services szolgáltatásban elérhető áttelepítési eszköz használatával át tudjanek áttelepítési környezeteikre. Lehetőség van arra is, hogy adataikat egyesíteni tudják a meglévő pénzügyi és műveleti környezettel. 

A vevők áttelepítése és a vevők egyesítése a következő módon különbözik:

- **Vevők áttelepítése** – az automatizált áttelepítési eszköz az ügyfél-adatbázisnak az emberi erőforrás-infrastruktúrából a pénzügyi és a műveleti infrastruktúrába történő "növekedési és műszaktelepítés" (lift and shift migration) végrehajtásához szükséges. Az eredmény egy új pénzügyi és műveleti környezet, amely a vevő emberi erőforrások adatbázisát használja. 
- **Vevőegyesítés** – a Microsoftnak nincs szüksége erre a további lépésre. A vevő saját belátása szerint és a vevő saját időrendben történik. A lépés során a vevőadatok már meglévő környezetbe, például pénzügyi vagy projektműveleti környezetbe kerülnek. Ez elsősorban manuális, és a DMF(DMF) adatentitások használatával használhatja. 

## <a name="planning-a-human-resources-environment-migration"></a>Az emberi erőforrások környezetének áttelepítése

Az infrastruktúra-egyesítés részeként minden vevőnek át kell áttelepítése a meglévő emberi erőforrások környezeteit az önálló infrastruktúrából. Ennek a folyamatnak az érdekében javasoljuk, hogy a Lifecycle Services automatizált áttelepítési eszközével helyezze át az aktuális környezetet az új infrastruktúrába. 

A következő szakaszok részletesebben ismertetik, hogyan használhatók a Lifecycle Services eszközök egy önálló emberierőforrás-környezet áttelepítésére. 

Az áttelepítést tervező vevőkre a következő várakozások közül választhatnak:

- A termelési környezet áttelepítése előtt minden vevőnek át kelltelepítenie egy üzenetdoboz-környezetet. 
- Az áttelepítési eszköz csak a "box-to-box" és a "termelésről termelésre" áttelepítést engedélyezi. Ebből következően a környezettípus meghatározza, hogy milyen környezetben lehet megfelelően áttelepíteni az adatokat. 
- Ha rendelkezésre áll egy cél boxhely, akkor a vevők a szükséges több mezőből át tudják áttelepítését a termelési környezetbe. A vevők egy áttelepített boxot is törölnek, és többször áttelepítik őket. 
- Ha nem sikerül az áttelepítés, vagy ha újra szeretne indulni, törölhet egy környezetet a pénzügyi és a műveleti infrastruktúra rendszerből, és újra át tudja áttelepítését ugyanazon a környezeten belül.
- Az emberi erőforrások környezetének URL-címe az áttelepítés után más lesz.
- Tervezze meg a megfelelő mennyiségű leállást a termelési környezet áttelepítéséhez. Az automatizált áttelepítési folyamat befejezésének becsült időkerete 3–4 óra. Az időkeret a szervezet adataitól függően eltérő lehet. Abox környezetek áttelepítése során érvényesnek kell lennie a szükséges időnek, és időt kell hagyni minden további kézi feladat elvégzésére.

> [!IMPORTANT] 
> Ha egy termelési környezet sikeresen áttelepítve a pénzügyi és műveleti infrastruktúrába, a forrás önálló termelési környezet automatikusan törlődik. Ne törölje az áttelepített termelési környezetet. 

Az áttelepítés folyamata elsősorban automatikus. Az üzleti felhasználóknak azonban az áttelepítés után kézi lépéseket és ellenőrzést kell végrehajtania.

A következő kézi lépéseket kell végrehajtani:

- Új Lifecycle Services-projekt létrehozása az áttelepítéshez
- A régi környezetben található integrációk felülvizsgálata az új környezetben, az új URL-címek/végpontok integrációjának az egyes integrációs konfigurációk alapján való mutatása alapján.
- A beágyazott jelentések adattárának Power BI frissítése.
- Az adatentitás-lista frissítése a DMF munkaterületről
- A Lifecycle Services szolgáltatásra mutató hivatkozás súgót nyújt.
- Pénzügyi naptárak létrehozása.

Az automatikus folyamat során a következő műveleteket kell végrehajtani, és ellenőrizni kell:

- Adatok:

    - Konfigurációk
    - Biztonsági szerepkörök (beleértve az egyéni szerepköröket is)
    - Munkafolyamatok
    - Személyre szabás és mentett nézetek
    - Tranzakciók
    - Egyéni mezők
    - Mellékletek

- Adatkezelés – saját adatbázis (BYOD) létrehozása.
- Funkciókezelés – engedélyezett/letiltott szolgáltatások.
- Beágyazott Power Apps.
- Power Platform rendszergazdai központ által csatolt környezet (csak termelés)
- Kötegelt feladatok.
- Minden jogi személyhez létrejön egy üres főkönyv. Az egyes főkönyvek alapértelmezett árfolyamtípusa és könyvelési pénzneme be van állítva.
- A program minden jogi személy **esetén** automatikusan létrehoz egy új számladiagramot, és csatolja azt a Főkönyv laphoz. Az Emberi erőforrások környezetben beállított pénzügyi dimenziókat a program automatikusan hozzáadja egy új számlastruktúrához, és csatolja a főkönyvhöz. 

> [!NOTE]
> A Dynamics 365 Pénzügyi termék részeként főkönyvet kell megadni a pénzügyi és a műveleti infrastruktúra területén. Az önálló alkalmazásban már meglévő egyéni Dynamics 365 Human Resources dimenzióvezérlő nem érhető el. Az Emberi erőforrások modul egyesített infrastruktúrája a Pénzügyi logika függvénye, amely a pénzügyi dimenziókat az Emberi erőforrások **modulban mutatja**. A számlatükre és a pénzügyi [dimenziókról az alábbi táblázatban olvashat bővebben](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Megfontolások

- A környezetek áttelepítése mindig a legújabb, általánosan elérhető (GALL) verzión lesz. Az áttelepítési tervtől és a tesztelési tervtől függően, ha abox környezetek áttelepítésének ellenőrzése másik verzión volt, javasoljuk, hogy a termelési környezettel azonos verziójú üzenetdoboz-áttelepítést ellenőrizze. 
- Az áttelepítés során az áttelepített környezetek ugyanabban a régióban lesznek elhelyezve, mint a forrás önálló emberi erőforrások környezete.

## <a name="licensing"></a>Licenckezelés

A licencelés nem változik a Dynamics 365 Human Resources következő területeken: 

- **Minimális licencbevásárlási követelmény**
- **Licencek termelési és üzenetdoboz-környezethez – ha olyan önálló emberierőforrás-licencekkel rendelkezik, amelyek egy termelési környezetet és egy üzenetdoboz-környezetet engedélyeznek, akkor ugyanannak a licencnek a száma érhető el a** pénzügyi és a műveleti infrastruktúra területén, további költség nélkül.
- **További** üzenetkészlet-licencek – ha további boxlicenceket vásárolt a különálló Emberi erőforrások alkalmazáshoz, akkor ugyanennek a jelölőnégyzet-licencnek a száma érhető el a pénzügyi és műveleti infrastruktúra szabványos elfogadási tesztkörnyezetében, egyéb költség nélkül. 
