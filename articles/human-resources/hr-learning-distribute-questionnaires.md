---
title: Kérdőívek terjesztése és ütemezése
description: A cikk leírja, hogyan terjesztheti a megtervezett kérdőíveket, hogy azok csak a kijelölt személy vagy csoportok számára legyenek elérhetők.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91b2c94c74fd51765a2545424504149fff1f4bfd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908861"
---
# <a name="distribute-and-schedule-questionnaires"></a>Kérdőívek terjesztése és ütemezése


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A cikk leírja, hogyan terjesztheti a megtervezett kérdőíveket, hogy azok csak a kijelölt személy vagy csoportok számára legyenek elérhetők. 

A kérdőívek terjesztésének több módja van:

-   A kérdőív megjelölése **aktívként**. A kérdőív ezt követően elérhetővé válik minden alkalmazott számára, kivéve ha a kérdőív csoport úgy van beállítva, hogy a hozzáférés korlátozva van.
-   Rendeljen jogokat a kérdőív csoporthoz. A kérdőív ezt követően a kiválasztott csoport minden tagja számára elérhető lesz.
-   Hozzon létre tervezett válaszmunkameneteket. A kérdőív ekkor csak egy bizonyos személy részére áll rendelkezésre.
-   Hozzon létre egy ütemezést. A kérdőív ekkor több felhasználó számára is elérhető lehet.

## <a name="marking-a-questionnaire-as-active"></a>Kérdőív aktívként való megjelölése

Ha szeretné, hogy a kérdőívet minden alkalmazott kitölthesse, állítsa az **Aktív** mezőt **Igen** értékre a **Kérdőívek** oldalon. A válaszadók több alkalommal is kitölthetik a kérdőívet. Ez a funkció akkor hasznos, ha azt szeretné, hogy egész évben folyamatosak legyenek a visszajelzések. Például létrehozhat egy kérdőívet, amelyen keresztül az alkalmazottak a menza étkezési lehetőségeivel kapcsolatban adhatnak visszajelzéseket.

## <a name="questionnaire-groups"></a>Kérdőívcsoportok

Létrehozhat kérdőívcsoportokat, amelyekhez beállíthatja azon lehetséges válaszadókat, akiknek a kérdőív szól. 

A következő oldalakról hozhat létre kérdőív csoportokat:

-   **Kérdőív csoportok**– Csak az egyes kérdőív csoportokban szereplő személyek tölthetik ki a kérdőívet. Például ha csak az alvállalkozókat szeretné megkérdezni, létrehozhat olyan kérdőív csoportokat, amelyekbe ezen specifikus válaszadókat vonhatja be.
-   **Kérdőív csoportok tagjai** – Személyek adhat hozzá a kérdőív csoportokhoz.

Kérdőívhez kérdőívcsoport hozzárendeléséhez a **Kérdőívek** oldalon kattintson a **Felhasználói jogok** elemre. A kérdőív aktívként történő elmentése után a kérdőívcsoport tagjai kitölthetik a kérdőívet. Ez a funkció akkor hasznos, ha szeretné a kérdőívet tesztelni személyek egy kiválasztott csoportján, mielőtt nagyobb csoport számára közzétenné, illetve ha egy kérdőívvel egy nagyon specifikus célközönséget szeretne megcélozni.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Tervezett válaszmunkamenet egy kérdőívenben

A tervezett válaszmunkamenetek olyan kérdőívek, amelyek megtervezettek és a kijelölt válaszadóknak szólnak. 

> [!NOTE]
> Egy tervezett válaszadási munkamenet beállítása előtt meg kell terveznie a kérdőívet. 

A **Tervezett válaszmunkamenetek** képernyőn lehet létrehozni tervezett válaszmunkamenetet egy bizonyos alkalmazotthoz. A lapon megjelenő listában megjelenik minden tervezett kérdőív. 

A tervezett válaszadási munkamenetek a **Kérdőív ütemezés** oldalon is használhatók, ahol többféle személy számára alkalmas kérdőíveket lehet tervezni:

-   Alkalmazottak
-   Tanfolyam résztvevői
-   Szervezeti egységek

Minden egyes ember csak egyszer töltheti ki a kérdőívet.

## <a name="scheduling-a-questionnaire"></a>Kérdőív ütemezése

Lehetőség van több válaszadó részére is ütemezni egy kérdőívet.

### <a name="planning-types"></a>Tervezés típusai

A tervezési típusokra akkor van szükség, ha több válaszadó részére szeretné ütemezni a tervezett válaszadási munkameneteket. A tervezési típusok a kérdőív-ütemezések osztályozására szolgálnak. Például az alábbi célokból ütemezhet kérdőíveket:

-   Értékelés
-   Felmérés
-   Tesztelés

A **Kérdőív-ütemezések** oldalon megadhat tervezési típusokat egy kérdőív-ütemezéshez.

### <a name="reference-types-for-questionnaire"></a>Hivatkozástípusok kérdőívhez

Hivatkozástípusok használatával megadhat feltételeket, amelyek segítségével kijelölhet bizonyos válaszadókat a kérdőív ütemezésekor. 

Használja a **Hivatkozástípusok** lapot a kérdőívekhez tartozó hivatkozási típusok beállításához. Minden hivatkozástípus a Microsoft Dynamics 365 Pénzügy egy táblához tartozik. Kérdőív-ütemezések létrehozásakor meg lehet adni bizonyos rekordokat vagy tartományokat a táblázatban, amelyhez a kérdőívet társítani szeretné. 

Például ha a Tanfolyamok táblázatoz választja, megadhatja, hogy melyik tanfolyam résztvevőinek számára jelenjen meg a kérdőív. Miután beállított egy hivatkozást a Tanfolyamok táblázathoz, bizonyos mezők és gombok elérhetővé válnak a **Tanfolyamok** lapon.

### <a name="questionnaire-schedules"></a>Kérdőív-ütemezések

A kérdőív-ütemezések segítségével több tervezett válaszmunkamenetet is generálhat egy csoport számára, egy hivatkozástípus alapján. Az ütemezés létrehozása a **Kérdőív-ütemezések** oldalon történik. Válasszon ki egy tervezési típust az ütemezés kategorizálásához, valamint válassza ki azon hivatkozási típust, amellyel a meghatározott felhasználókat le szeretné kérdezni a rendszerből. Például a hivatkozás típusaként a Tanfolyamok táblázatot állítja be, kiválaszthat egy adott tanfolyamot a **Hivatkozás** mezőben. 

Kattintson a **Beállítás részletei** lehetőségre egy kérdőív és más feltételek kijelöléséhez. Például megadhatja az oktató nevét feltételként, ha a kérdőív az oktató teljesítményére kíváncsi. Miután befejezte a beállítások megadását, a rendszer létrehozza a tervezett válaszadási munkamenetek azon felhasználóknak, akik szerepelnek a lekérdezésben. 

Kattintson a **Tervezett válaszadási munkamenetek** lehetőségre, hogy megtekinthesse a válaszadási munkameneteket egy adott ütemezéshez. Ezt követően manuálisan további tervezett válaszadási munkameneteket is létrehozása, illetve kitörölheti azon tervezett válaszadási munkameneteket, amelyre még nem érkezett válasz. 

Kattintson a **Funkciók** &gt; **Start** lehetőségre, hogy a kérdőívet elérhetővé tegye a tervezett válaszmunkamenetekhez kapcsolódó személyek számára. Kattintson a **Válaszok** lehetőségre, hogy megtekinthesse a kitöltött kérdőíveket. Opcionálisan át is másolhatja egy kérdőív-ütemezés beállításait, a tervezett válaszmunkamenetek és válaszokat egy új kérdőív-ütemezésekbe.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Válaszadók értesítése a számukra elérhető kérdőívekről
Kérdőív terjesztésekor értesítést kell küldeni a válaszadóknak arról, hogy a kérdőív elérhető számukra. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Válaszadók értesítése egy tervezett válaszmunkamenetről

Ha tervezett válaszmunkamenetet használ, akkor közvetlenül kell értesítenie az adott személyt, például telefonon vagy e-mail üzenetben.

### <a name="notifying-respondents-about-a-scheduling"></a>Válaszadók értesítése egy ütemezésről

A **Kérdívek ütemezése** képernyőn e-mail üzenetet írhat a kérdőívhez társított válaszadóknak. Írja be az e-mail szövegét az E-mail **cím az alkalmazotti önkiszolgáló szolgáltatáshoz lapon**. Az ütemezés elkezdése után a **Funkciók** &gt; **küldése e-mail** gombra kattintva generálja és elküldi az e-mailt a válaszadóknak. A válaszadók ezután bejelentkezhetnek a webhelyre, és kitölthetik a kérdőívet. 

> [!NOTE]
> Az e-mail funkció használata előtt az rendszergazdának meg kell adnia az e-mail beállításait az e-mail **paraméterei oldalon**.

## <a name="ending-a-scheduled-questionnaire"></a>Ütemezett kérdőív lezárása

Ha az összes válaszadó befejezte a kiadott válaszmunkamenetet, akkor be lehet fejezni az ütemezett kérdőívet. Az ütemezett kérdőív befejezése után annak beállításait már nem lehet az új ütemezésekbe másolni. 

> [!NOTE]
>   Ha annak ellenére szeretné befejezni az ütemezést, hogy egy vagy több válaszadó még nem töltötte ki a kérdőívet, először törölje a szóban forgó válaszadókat a **Tervezett válaszmunkamenet** képernyő listájáról. Ezután befejezhető az ütemezés.

## <a name="completing-questionnaires"></a>Kérdőív kitöltése

Miután megtervezte és kiosztotta a kérdőívet, az csak a kijelölt válaszadók számára lesz elérhető. A rendelkezésre álló kérdőíveket két helyen töltheti ki:

-   Kattintson a navigációs ablak **Kérdőívek** &gt; **Terjesztés** &gt; **Kérdőív kitöltése** lehetőségére.
-   Kattintson az Alkalmazotti önkiszolgáló rendszer **Kitöltendő kérdőívek** lehetőségére.

A kérdőívek közzétehetők csak adott felhasználók vagy felhasználócsoportok számára is, illetve a hálózat minden tagja számára.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
