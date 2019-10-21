---
title: Üzleti folyamatok formalizálása
description: Ez a témakör ismerteti, hogy az üzleti folyamat funkcióval üzletifolyamat-sablont hogyan lehet létrehozni a szervezeten belül végrehajtandó üzleti folyamatokhoz.
author: andreabichsel
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.openlocfilehash: 51f8102afc28b3836d5fee13aa1e950351af3c4f
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008373"
---
# <a name="formalize-business-processes"></a>Üzleti folyamatok formalizálása

[!include[banner](includes/banner.md)]

Az üzleti folyamat funkcióval üzletifolyamat-sablont lehet létrehozni a szervezeten belül kötelezően végrehajtandó üzleti folyamatokhoz. Például a vállalata minden évben emberi erőforrások (HR) ellenőrzést hajt végre. Ebben az esetben létrehozhat egy sablont, amely nyomon követi a feladatokat, amelyekből az ellenőrzési folyamat áll. Ezzel a sablonnal garantálható, hogy az összes feladatot elvégzik minden alkalommal, amikor ellenőrzés történik. Ezenkívül ha a feladatokat egy adott sorrendben kell elvégezni, a sablon segítségével garantálható, hogy a megfelelő sorrendben végezzék őket.

Az ismétlődő folyamatokhoz a sablonok újrafelhasználhatók. Le is másolhatók, és új sablonokat kiindulópontjaként szolgálhatnak.

Üzletifolyamat-sablon létrehozása után üzleti folyamat indítható és követhető az **Üzleti folyamat** munkaterületen. Az üzleti folyamat indításakor a feladatokat a rendszer hozzárendeli a megfelelő személyekhez, és az esedékességi dátumot is hozzáadja.

## <a name="business-process-templates"></a>Üzleti folyamat sablonjai
Az Üzleti folyamat sablon felsorolja az üzleti folyamatot alkotó feladatok csoportját. Az emberierőforrás-vezetők és asszisztensek alapértelmezés szerint létrehozhatnak üzleti folyamatokat. Azonban módosíthatja az üzleti folyamatok létrehozására jogosult szerepköröket az **Általános üzleti folyamatok kezelése** kötelesség módosításával a biztonsági beállításokban.

Minden üzleti folyamathoz meghatározható egy folyamattulajdonos. A folyamat tulajdonosa rálátást kap a folyamat feladataira, és újra kioszthatja a feladatokat vagy módosíthatja határidőket. Például a HR-igazgató a juttatások ellenőrzésére egy üzleti folyamat sablont hoz létre, és megadja a kompenzációkért és juttatásokért felelős vezetőt a folyamat tulajdonosának. A kompenzációs és a juttatásokért felelős vezető akkor rálátást kap az ellenőrzés részeként elvégzendő feladatokra.

A folyamat tulajdonosa nem hozhat létre új üzleti folyamatokat, illetve az üzleti folyamat sablonokat, és nem törölhet aktív üzleti folyamatokat, illetve üzleti folyamat sablonokat.

## <a name="tasks"></a>Feladatok
Az üzleti folyamat gyakran több feladatot is magában foglal. Bizonyos feladatokat a Dynamics 365 Talent megoldáson belül lehet elvégezni, például a belső tanfolyamajánlatok ellenőrzését. Ebben az esetben egy beállítás van megadva a **Tevékenységkapcsolat** mezőben. Egyéb feladatok weboldalon lévő oldalak áttekintését vagy kitöltését foglalhatják magukban. Ebben az esetben az **URL-cím** van kiválasztva a **Tevékenységkapcsolat** mezőben, és ezután megadható az URL-cím. A belső és a külső webhelyekhez is URL-címet adhat meg. Feladatokat is létrehozhat a manuálisan elvégzett munkákhoz, például minden struktúra hozzáférhetőségének ellenőrzéséhez. Ebben az esetben feladathivatkozás használata nem kötelező. A rugalmasság segítségével többféle feladat követhető nyomon egyetlen átfogó folyamatban.

Feladatok is hozzárendelhetők egy adott dolgozóhoz vagy pozícióhoz. Például a kompenzációkért és juttatásokért felelős vezető minden esetben a személy, aki a biztosítási díjak felülvizsgálatát végrehajtja. Ezért a feladat létrehozásakor válassza ki a **pozíciót** a **hozzárendelés-típus** mezőben, majd válassza a **Kompenzációkért és juttatásokért felelős vezetőt** a **Pozíciók** listáról. Az üzleti folyamat megkezdésekor a **Kompenzációkért és juttatásokért felelős vezető** pozícióban levő dolgozó kapja a feladat. Egy adott dolgozóhoz hozzárendelhető egy feladat, ehhez válassza ki a **dolgozót** a **hozzárendelés-típus** mezőben, majd válassza ki a megfelelő személyt.

A feladat esedékességi dátuma az üzleti folyamat elején bevitt céldátumtól függ. Bizonyos feladatokat el kell végezni a céldátumig, és néhány a céldátumot követően is végrehajtható. Feladat meghatározásakor meg kell adnia egy esedékességi dátumot, amely a céldátumhoz viszonyított a **Határidő eltérése a céldátumtól** mezőben. Tegyük fel például, hogy a kompenzációkért és juttatásokért felelős vezetőnek 10 nappal a HR vizsgálat befejezése előtt felül kell vizsgálnia a biztosítási díjakat. Ebben az esetben a felülvizsgálathoz létrehozott feladat esetében a **Határidő eltérése a céldátumtól** értéke **-10**. Ezért ha az üzleti folyamat indítása május 13., a feladat határideje május 3. lesz.

> [!NOTE]
> Esedékességi dátum azután is módosítható, hogy az üzleti folyamat elindult.

A komplex feladatok több lépést igényelhetnek, vagy a feladatokat végrehajtó egyéneknek további információkat kell megadniuk. Ilyen esetben a tevékenységhez lehet utasításokat adni. Az utasítások annak a személynek, aki hozzá van rendelve a feladat végrehajtásához, további információt nyújthatnak a végrehajtással kapcsolatban. Rich text formázást is adhat az utasításokhoz.

## <a name="starting-a-business-process"></a>Üzleti folyamat indítása
Az üzleti folyamat egy üzletifolyamat-sablonban indítható el a **Folyamat indítása** lehetőség kiválasztásával. A folyamat indításakor a kijelölt, a sablonban megtalálható feladatokban meghatározott dolgozókhoz és/vagy beosztásokhoz létrejönnek a feladatok. A határidő is hozzá lesz rendelve az egyes feladatokhoz úgy, hogy a külön napokat hozzáadjuk vagy kivonjuk a céldátumból, a „Feladatok„ részben leírtak szerint). Az aktív üzleti folyamatok az **üzleti folyamatok** munkaterületen tekinthetők meg.

## <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer
A feladat kiosztása után egy alkalmazottnak, az alkalmazott megtekintheti, az összes többi hozzárendelt feladatával együtt, az **Alkalmazotti önkiszolgáló rendszer** lapon. Minden egyes hozzá rendelt üzleti folyamat feladatnál, az alkalmazott láthatja a feladat nevét és leírását, az elvégzésével kapcsolatos tudnivalókat, és a kapcsolattartó személy nevét. Az **Alkalmazotti önkiszolgáló rendszer** lapról az alkalmazott megnyithatja a kapcsolódó lapot a Microsoft Dynamics 365 megoldásban, vagy a kapcsolódó weblapot, és megjelölheti a feladatokat folyamatban lévő, törölt vagy befejeződött feladatként.

## <a name="business-process-workspace"></a>Üzleti folyamat munkaterülete
A HR szakemberek az **Üzleti folyamat** munkaterületről megtekinthetik az aktív üzleti folyamatokat. Ez a munkaterület listázza az összes aktív folyamatot, valamint a hozzájuk kapcsolódó összes feladatot. A legrészletesebb feladatlistát szűrni lehet az esedékességi dátum szerint. A munkaterület a lejárt határidejű tevékenységeket is felsorolja, és a kifejezetten a HR-szakemberhez rendelt feladatokat is. A HR-szakemberek összes feladat állapotát is frissíthetik, és szükség esetén áthelyezhetik a feladatokat a teljes üzleti folyamat előrehaladásának megőrzése érdekében.

## <a name="my-business-processes-workspace"></a>Saját üzleti folyamatok munkaterület
A folyamattulajdonosok a hozzájuk rendelt aktív üzleti folyamatokat rendeli a **Saját üzleti folyamatok** munkaterületről tekinthetik meg. A munkaterület listázza az összes aktív folyamatot és a kapcsolódó feladatokat, amelyek az adott felhasználó tulajdonában vannak. A legrészletesebb feladatlistát szűrni lehet az esedékességi dátum szerint. A munkaterület a kifejezetten a folyamatgazdához rendelt feladatokat is felsorolja. A folyamat tulajdonosa frissítheti is az összes feladat állapotát, valamint máshoz is rendelheti bármelyik feladatot.

## <a name="navigating-business-processes"></a>Navigálás az üzleti folyamatok között
Üzleti folyamat sablon létrehozásához vagy másolásához, vagy egy üzleti folyamat elindításához, keresse meg a következőt: Üzleti folyamatok - Hivatkozások – Üzleti folyamatok felügyelete. A következő műveleteket végezheti el ezután:

- Válassza az **Új** lehetőséget új üzleti folyamat sablon létrehozásához.
- A **Másolás sablonból** lehetőséggel másolhatja át a kiválasztott sablont egy újba.
- A **Folyamat indítása** elindítja a kiválasztott üzleti folyamatot, kiosztja a feladatokat, és kiszámítja a határidőket.

Az aktív folyamatok és a hozzájuk kapcsolódó feladatok megtekintéséhez nyissa meg az **Üzleti folyamatok** munkaterületet.

