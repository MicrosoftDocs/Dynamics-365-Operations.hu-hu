---
title: "Üzleti folyamatok formalizálása"
description: "Az üzleti folyamat funkcióval üzletifolyamat-sablont lehet létrehozni a szervezeten belül végrehajtandó üzleti folyamatokhoz."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1b50a97f5e2fc94255ff71702faf91ab36e68eb4
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="formalize-business-processes"></a>Üzleti folyamatok formalizálása
Az üzleti folyamat funkcióval üzletifolyamat-sablont lehet létrehozni a szervezeten belül végrehajtandó üzleti folyamatokhoz. Például a vállalat évente HR-auditot végezhet. Sablont lehet létrehozni az ellenőrzés összes feladatának nyomon követéséhez annak érdekében, hogy minden feladat elvégezhető legyen minden egyes alkalommal, amikor a folyamat befejeződik, és szükség esetén annak biztosítására, hogy a feladatok a helyes sorrendben kövessék egymást. A sablonok újra felhasználhatók az ismétlődő folyamatokhoz, vagy újak létrehozásának kiindulási pontjaként használhatók.

Sablon létrehozása után folyamat indítható és követhető az Üzleti folyamat munkaterületen.  Az üzleti folyamat indításakor a feladatokat a rendszer hozzárendeli a megfelelő személyekhez, és az esedékességi dátumot is hozzáadja. Ezeket az összetevőket lent ismertetjük részletesen.

## <a name="business-process-template"></a>Üzleti folyamat sablonja
Az Üzleti folyamat sablon felsorolja az üzleti folyamatot alkotó feladatok csoportját. Az emberierőforrás-kezelők és asszisztensek alapértelmezés szerint létrehozhatnak üzleti folyamatokat.  Ez azonban megváltoztatható a biztonsági konfigurációban a Általános üzleti folyamatok karbantartása kötelesség szerkesztésével.

Minden folyamathoz meghatározható egy folyamattulajdonos. A folyamat tulajdonosa rálátást kap a folyamat feladataira, és újra kioszthatja a feladatokat vagy módosíthatja határidőket.  A HR-igazgató például létrehozhat egy üzletifolyamat-sablont juttatások ellenőrzésére.  A kompenzációkért és juttatásokért felelős vezető megadható a folyamat tulajdonosaként, így betekinthet az olyan feladatokba, amelyeket a felülvizsgálat részeként kell végrehajtani.  A folyamat tulajdonosa nem tud létrehozni vagy törölni aktív üzleti folyamatokat vagy üzletifolyamat-sablonokat.

## <a name="task"></a>Feladat
Az üzleti folyamat gyakran több feladatot is magában foglal. Bizonyos feladatokat a Dynamics 365 for Talent megoldáson belül lehet elvégezni, például a belső tanfolyamajánlatok ellenőrzését. Ebben a példában egy menüelemet választunk ki a feladathivatkozás a Feladathivatkozás mezőben. Egyéb feladatok weboldalon lévő űrlapok áttekintését vagy kitöltését foglalhatják magukban. Az URL-cím kiválasztása a feladathivatkozás mezőben engedélyezi a webcím megadását. Ebben a mezőben a belső és a külső webhelyekhez is URL-címet adhat meg. Feladatokat is létrehozhat a manuálisan elvégzett munkákhoz, például minden struktúra hozzáférhetőségének ellenőrzéséhez. Ebben az esetben feladathivatkozás használata nem kötelező. A rugalmasság segítségével többféle feladat követhető nyomon egyetlen átfogó folyamatban.

Feladatok is hozzárendelhetők egy adott dolgozóhoz vagy pozícióhoz. Például a kompenzációkért és juttatásokért felelős vezető minden esetben a személy, aki a biztosítási díjak felülvizsgálatát végrehajtja.   A feladat létrehozásakor válassza ki a pozíciót a hozzárendelés-típus számára, majd válassza a Kompenzációkért és juttatásokért felelős vezetőt a Pozíciók listáról. A folyamat megkezdésekor a Kompenzációkért és juttatásokért felelős vezető pozícióban levő dolgozó kapja a feladat. Egy adott dolgozóhoz is hozzárendelhető egy feladat, ehhez válassza ki a dolgozót a hozzárendelés-típus mezőben, majd válassza ki a megfelelő személyt.

A feladat esedékességi dátuma a folyamat elején bevitt céldátumtól függ. Bizonyos feladatokat el kell végezni a céldátumig, és néhány a céldátumot követően is végrehajtható.  Feladat meghatározásakor meg kell adnia egy esedékességi dátumot, amely a céldátumhoz viszonyított a Határidő eltérése a céldátumtól mezőben. Tegyük fel például, hogy a kompenzációkért és juttatásokért felelős vezetőnek 10 nappal a HR vizsgálat befejezése előtt felül kell vizsgálnia a biztosítási díjakat. A létrehozott feladat a céldátumhoz képest -10 határidőt fog tartalmazni. Ezért ha a folyamat indítása május 13., a feladat határideje május 3. lesz. Megjegyzés: Esedékességi dátum azután is módosítható, hogy a folyamat elindult.

A komplex feladatok több lépést igényelhetnek, vagy a feladatok egyéni végrehajtása lehet szükséges további információk érdekében. Utasításokat adhat a tevékenységhez, és az utasítások rich text formázásokat is tartalmazhatnak. Az utasítások annak a személynek, aki hozzá van rendelve a feladat végrehajtásához, további információt nyújthatnak a végrehajtással kapcsolatban.

## <a name="starting-a-process"></a>Folyamat indítása
A folyamat egy üzletifolyamat-sablonban indítható el a Folyamat indítása lehetőség kiválasztásával.  A folyamat indításakor a kijelölt, az üzletifolyamat-sablonban megtalálható feladatokban meghatározott dolgozókhoz és/vagy beosztásokhoz létrejönnek a feladatok. A határidő is hozzá lesz rendelve az egyes feladatokhoz úgy, hogy a külön napokat hozzáadjuk vagy kivonjuk a céldátumból (a külön napokat illetően lásd a feladatokról szóló részt). Az aktív üzleti folyamatok az üzleti folyamatok munkaterületen tekinthetők meg. 

## <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer
Ha feladat van kiosztva egy alkalmazottnak, az alkalmazott hozzárendelt feladatai megtekinthetők az alkalmazott önkiszolgáló lapján. Azok az alkalmazottak, akikhez üzleti feladatok vannak rendelve, megtekinthetik a feladatot, leírását, kitöltési utasításait és egy kapcsolattartó személy nevét, és megnyithatják a kapcsolódó Dynamics365 oldalt vagy weboldalt az alkalmazotti önkiszolgáló oldalról. A feladatok a folyamatban lévő megszakítva vagy befejeződött megjelölésűek lehetnek.

## <a name="business-process-workspace"></a>Üzleti folyamat munkaterülete
A HR szakemberek az Üzleti folyamat munkaterületről megtekinthetik az aktív üzleti folyamatokat. A munkaterület listázza az összes aktív folyamatot, valamint a hozzájuk kapcsolódó összes feladatot. A legrészletesebb feladatlistát szűrni lehet az esedékességi dátum szerint. A lap a lejárt határidejű tevékenységeket is felsorolja, és a kifejezetten a HR-szakemberhez rendelt feladatokat is. Az összes feladat állapotát is frissíthetik, és szükség esetén áthelyezhetik a feladatokat a teljes üzleti folyamat előrehaladásának megőrzése érdekében.

## <a name="my-business-processes-workspace"></a>Saját üzleti folyamatok munkaterület
A folyamattulajdonosok a hozzájuk rendelt aktív üzleti folyamatokat rendeli a Saját üzleti folyamatok munkaterületről tekinthetik meg. A munkaterület listázza az összes aktív folyamatot és a kapcsolódó feladatokat, amelyek az adott felhasználó tulajdonában vannak.  A legrészletesebb feladatlistát szűrni lehet az esedékességi dátum szerint. A lap felsorolja a kifejezetten a folyamattulajdonoshoz rendelt feladatokat is. A folyamat tulajdonosa frissítheti is a feladatok állapotát, valamint máshoz is rendelheti a feladatokat.

## <a name="navigating-business-processes"></a>Navigálás az üzleti folyamatok között
1. Üzletifolyamat-sablon hozzáadásához keresse meg az üzleti folyamatokat - a hivatkozásokat –, és az üzleti folyamatok adminisztrációját.
   - a.   Az Új elem új sablont hoz létre.
   - b.   A sablonból történő másolás a kiválasztott sablont átmásolja egy újba.
   - c.   A folyamat indítása elindítja a kiválasztott üzleti folyamatot, kiosztja a feladatokat, és kiszámítja a határidőket.  
2. Az aktív folyamatok és a hozzájuk kapcsolódó feladatok megtekintéséhez keresse meg az üzleti folyamatok munkaterületet.

