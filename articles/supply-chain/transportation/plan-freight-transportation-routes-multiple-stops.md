---
title: "Többmegállós szállítási útvonal tervezése"
description: "Ez a cikk a Microsoft Dynamics 365 for Finance and Operations szállítási útvonalak tervezéséhez használt különböző elemeit ismerteti."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 16255e812773ed35c0e34ec26a8a689ea09632bd
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>Többmegállós szállítási útvonal tervezése

[!include [banner](../includes/banner.md)]

Ez a cikk a Microsoft Dynamics 365 for Finance and Operations szállítási útvonalak tervezéséhez használt különböző elemeit ismerteti.

Többmegállós, összetett szállítási útvonalaknál használható útvonaltervek és az útvonalmutatók. Ha rendszeresen azonos útvonalat fog használni, beállíthat egy ütemezett útvonalat.

## <a name="route-plans"></a>Útvonaltervek
Az útvonalterv útvonalszegmenseket tartalmaz, amely az útvonal során használt megállókról és a szegmensekhez használt szállítókról tartalmaz információkat. Az útvonalon található megállókat központokként kell definiálnia. A központ lehet egy szállító, egy raktár, egy vevő vagy egy átrakodási hely. Mindegyik szegmensnél megadhat „azonnali díjakat” a különféle költségekhez. Íme néhány példa:

-   Az adott szegmensekhez utazási költségei
-   Az árufelvétel költségei
-   Az árulerakás költségei

Minden egyes útvonaltervet az útvonalmutatóval kell társítani.

## <a name="route-guides"></a>Útvonalmutatók
Az útvonalmutató meghatározza az rakományegyeztetés feltételeit az útvonaltervvel. Például megadhatja a kiindulási és célközpontokat, a tároló térfogatára, súlyára vonatkozó korlátozásokat, a szállítmányozót, a szolgáltatásokat vagy a csoportot. Útvonalmutatók érhetők el a **Díj és útvonal munkaterület** oldalon, ahol rakományok rendelhetők hozzá az útvonalakhoz manuálisan vagy automatikusan. Ha egy útvonalmutató egy ütemezett útvonalra vonatkozik, szintén elérhető a **Rakomány-összeállítási munkaterület** oldalon.

## <a name="scheduled-routes"></a>Ütemezett útvonalak
Az ütemezett út egy előre meghatározott útvonalterv, mely ütemezett szállítási dátumokkal rendelkezik. Az ütemezett útvonalak és nem ütemezett útvonalak a hozzárendelt rakományban különböznek. Ha az Útvonal–díj munkaterület használatával egy nem ütemezett útvonalhoz végez hozzárendelést, csak a rakomány és az útvonalmutató kerül érvényesítésre. Ha egy ütemezett útvonalat társít, a megrendelések és központok dátumai és címei illetve az útvonalterv dátuma is beleszámítanak. A Útvonal-díj munkaterület oldal használata nem szükséges a rakomány ütemezett útvonalhoz való manuális hozzárendeléséhez. A Rakomány-összeállítási munkaterület használatával javaslatot tehet rakomány-összeállításra egy adott ütemezett útvonal vevői rendeléseihez tartozó vevők címei és a szállítási dátumok alapján. Ütemezett útvonalak esetén az útvonalterv rögzített kiindulási és célközpontokkal fog rendelkezni. Általában a szállítmányozó és a szolgáltatás ugyanaz lesz az összes szegmensnél, de különbözhetnek is ettől. A célközpontok az útvonalon meglátogatott vevők irányítószámainak használatával jönnek létre. Egy útvonaltervnél több útvonal-ütemezés adható meg. Az útvonaltervet az útvonalmutatóval kell társítani. Azonban az ütemezett útvonalak esetén a terv csak egy útvonalmutatóval társítható. Az útvonal-ütemezés csak tényleges útvonalak létrehozására használatos az **Útvonal-ütemezés** oldalon. Használhatja az alapértelmezett rakománysablont amikor rakományt javasol a Rakomány-összeállítási munkaterületen.

## <a name="load-building-workbench"></a>Rakomány-összeállítási munkaterület
A Rakomány-összeállítási munkaterület rakományjavaslat készítésekor vevői rendelésekhez tartozó vevők címeit és szállítási dátumokat, valamint az elérhető ütemezett útvonalakat használja. Az útvonal értékei a munkaterületre kerülnek az alapértelmezés szerint. Ugyanakkor az útvonal kezdő dátumánál korábbi kezdő dátum is választható. Rakományjavaslat esetén minden nyitott értékesítési rendelés szállítási címe és a szállítási dátuma ellenőrzésre kerül. Ha a szállítási cím irányítószáma és a központ irányítószáma egyezik az útvonaltervben, és ha a szállítási dátum a feltételekben a kijelölt tartományon belül van, a értékesítési rendelés javasolt lesz rakománynak. A rakománysablon-kapacitás szintén mérlegelésre kerül. Egyszerre csak rakományjavaslat lehetséges. Ha egy értékesítési rendelése nincs feltüntetve, más rakománysablont kell használnia (például egy rakománysablont nagyobb teherautó vagy tároló számára) vagy extra kiszállítást kell terveznie.




