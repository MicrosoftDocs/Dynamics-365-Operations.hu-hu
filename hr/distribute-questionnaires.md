---
title: "Kérdőívek terjesztése és kitöltése"
description: "Ez a témakör bemutatja, hogyan tervez, kérdőívek terjesztésére, így érhetők el a személy vagy csoport, akik végre őket."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: 8e09c6b042d557e3b2d608fb5e278169fc3c1d88
ms.lasthandoff: 03/31/2017


---

# <a name="distribute-and-complete-a-questionnaire"></a>Kérdőívek terjesztése és kitöltése

Ez a témakör bemutatja, hogyan tervez, kérdőívek terjesztésére, így érhetők el a személy vagy csoport, akik végre őket. 

A kérdőívek terjesztésének több módja van:

-   Jelölje meg aktívként a kérdőívet. A kérdőív ezt követően elérhetővé válik minden alkalmazott számára, kivéve ha a kérdőív csoport úgy van beállítva, hogy a hozzáférés korlátozva van.
-   Rendeljen jogokat a kérdőív csoporthoz. A kérdőív ezt követően a kiválasztott csoport minden tagja számára elérhető lesz.
-   Hozzon létre tervezett válaszmunkameneteket. A kérdőív ekkor csak egy bizonyos személy részére áll rendelkezésre.
-   Hozzon létre egy ütemezést. A kérdőív ekkor több felhasználó számára is elérhető lehet.

## <a name="marking-a-questionnaire-as-active"></a>Kérdőív aktívként való megjelölése
Beállításával a **aktív** mező **Igen** meg a **kérdőívek** lap, elérhetővé teheti a kérdőív befejezéséhez minden alkalmazott. A válaszadók több alkalommal is ki a kérdőívet. Ez a funkció akkor hasznos, ha azt szeretné, hogy egész évben folyamatos visszajelzések. Például létrehozhat egy kérdőívet, amelyen keresztül az alkalmazottak a menza étkezési lehetőségeivel kapcsolatban adhatnak visszajelzéseket.

## <a name="questionnaire-groups"></a>Kérdőívcsoportok
Létrehozhat kérdőívcsoportokat, amelyekhez beállíthatja azon lehetséges válaszadókat, akiknek a kérdőív szól. 

A következő oldalakról hozhat létre kérdőív csoportokat:

-   **Kérdőív csoportok **– Csak az egyes kérdőív csoportokban szereplő személyek tölthetik ki a kérdőívet. Például ha csak az alvállalkozókat szeretné megkérdezni, létrehozhat olyan kérdőív csoportokat, amelyekbe ezen specifikus válaszadókat vonhatja be.
-   **Kérdőív csoportok tagjai** – Személyek adhat hozzá a kérdőív csoportokhoz.

Egy kérdőívet a kérdőív csoport hozzárendelése a a **kérdőívek** lap **felhasználói jogok**. A kérdőív aktívként mentése után a kérdőív csoport tagjai is ki a kérdőívet. Ez a funkció akkor hasznos, ha azt szeretné, hogy a személyek egy csoportjának kérdőívet tesztelése előtt forgassa azt egy nagyobb csoporthoz, vagy ha meg szeretne célozni nagyon adott célközönségre egy kérdőívet.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Tervezett válaszmunkamenet egy kérdőívenben
A tervezett válaszmunkamenetek olyan kérdőívek, amelyek megtervezettek és a kijelölt válaszadóknak szólnak. 

**Megjegyzés:** Egy tervezett válaszadási munkamenet beállítása előtt meg kell terveznie a kérdőívet. 

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

Használja a **Hivatkozástípusok** lapot a kérdőívekhez tartozó hivatkozási típusok beállításához. Minden hivatkozás típusa tábla a Microsoft Dynamics 365 műveletek felel meg. Kérdőív-ütemezések létrehozásakor meg lehet adni bizonyos rekordokat vagy tartományokat a táblázatban, amelyhez a kérdőívet társítani szeretné. 

Például ha a Tanfolyamok táblázatoz választja, megadhatja, hogy melyik tanfolyam résztvevőinek számára jelenjen meg a kérdőív. Miután beállított egy hivatkozást a Tanfolyamok táblázathoz, bizonyos mezők és gombok elérhetővé válnak a **Tanfolyamok** lapon.

### <a name="questionnaire-schedules"></a>Kérdőív-ütemezések

Kérdőív-ütemezés segítségével egy csoport számára, a hivatkozás típusa alapján több tervezett válaszadási munkamenetek létrehozása. Az ütemezés létrehozása a **Kérdőív-ütemezések** oldalon. Jelölje be az ütemezés kategorizálni a tervezési típus, és is jelölje be a hivatkozás típusa, amellyel lekérdezést a rendszer az adott felhasználó számára. Például ha a hivatkozás típusa a tanfolyamok tábla, választhat egy adott tanfolyam, a **referencia** mezőben. 

Kattintson a **Beállítás részletei** lehetőségre egy kérdőív és más feltételek kijelöléséhez. Például adja meg az oktató nevét feltételként a kérdőív esetén az oktató értékelését. Miután befejezte a telepítő részletek megadásával, a rendszer létrehozza a felhasználók a lekérdezésben szereplő tervezett válaszmunkamenetek. 

Kattintson a **Tervezett válaszadási munkamenetek** lehetőségre, hogy megtekinthesse a válaszadási munkameneteket egy adott ütemezéshez. Ezt követően manuálisan további tervezett válaszadási munkameneteket is létrehozása, illetve kitörölheti azon tervezett válaszadási munkameneteket, amelyre még nem érkezett válasz. 

Kattintson a **funkciók**&gt;**Start** a kérdőív számára elérhetővé szeretné tenni a felhasználók a kapcsolódó tervezett válaszmunkamenetek. Kattintson a **Válaszok** lehetőségre, hogy megtekinthesse a kitöltött kérdőíveket. Opcionálisan át is másolhatja egy kérdőív-ütemezés beállításait, a tervezett válaszmunkamenetek és válaszokat egy új kérdőív-ütemezésekbe.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Válaszadók értesítése a számukra elérhető kérdőívekről
Kérdőív terjesztésekor értesítést kell küldeni a válaszadóknak arról, hogy a kérdőív elérhető számukra. 

**Megjegyzés:** a válaszadók kell lennie a felhasználók Microsoft Dynamics 365 kérdőívet műveletekhez.

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Válaszadók értesítése egy tervezett válaszmunkamenetről

Ha tervezett válaszmunkamenetet használ, akkor közvetlenül kell értesítenie az adott személyt, például telefonon vagy e-mail üzenetben.

### <a name="notifying-respondents-about-a-scheduling"></a>Válaszadók értesítése egy ütemezésről

A **Kérdívek ütemezése** képernyőn e-mail üzenetet írhat a kérdőívhez társított válaszadóknak. Írja be az e-mail üzenet szövegét az **E-mail üzenet az alkalmazotti önkiszolgáló szolgáltatás számára** lapon. Kattintson az ütemezés megkezdése után **funkciók**&gt;**e-mailt** hozhat létre és küldhet e-mailt a válaszadók. A válaszadók ezután jelentkezzen be a webhely és a kérdőív kitöltésére. 

**Megjegyzés:** Az e-mail funkció használata előtt a rendszergazdának meg kell adnia az e-mail beállításokat az **E-mail paraméterek** oldalon.

## <a name="ending-a-scheduled-questionnaire"></a>Ütemezett kérdőív lezárása
Ha az összes válaszadó befejezte a kiadott válaszmunkamenetet, akkor be lehet fejezni az ütemezett kérdőívet. Az ütemezett kérdőív befejezése után annak beállításait már nem lehet az új ütemezésekbe másolni. 

**Megjegyzés:** Ha annak ellenére szeretné befejezni az ütemezést, hogy egy vagy több válaszadó még nem töltötte ki a kérdőívet, először törölje a szóban forgó válaszadókat a **Tervezett válaszmunkamanet** képernyő listájáról. Ezután befejezhető az ütemezés.

## <a name="completing-questionnaires"></a>Kérdőív kitöltése
Miután megtervezte és kiosztotta a kérdőívet, az csak a kijelölt válaszadók számára lesz elérhető. A rendelkezésre álló kérdőíveket két helyen töltheti ki:

-   Kattintson a navigációs ablak **kérdőívek**&gt;**elosztás**&gt;**kérdőív kitöltése**.
-   Kattintson az Alkalmazotti önkiszolgáló rendszer **Kitöltendő kérdőívek** lehetőségére.

A kérdőívek közzétehetők csak adott felhasználók vagy felhasználócsoportok számára is, illetve a hálózat minden tagja számára.

<a name="see-also"></a>Lásd még
--------

[Kérdőívek tervezése](design-questionnaires.md)

[Kérdőívek használata](questionnaires.md)

[Megtekintés, és a kérdőív eredményeinek értékelése](evaluate-questionnaire-results.md)


