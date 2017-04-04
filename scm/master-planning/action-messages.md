---
title: "Nem dokumentált"
description: "A műveletkérő üzenet olyan, a rendszer által létrehozott üzenet, amely javaslatot tesz egy létező tervezett vagy megerősített rendelés módosítására."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-07 09 - 21 - 54
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f2ac69ddf485139b057dafa20e5f1a961fc32067
ms.lasthandoff: 03/29/2017


---

# <a name="undocumented"></a>Nem dokumentált

A műveletkérő üzenet olyan, a rendszer által létrehozott üzenet, amely javaslatot tesz egy létező tervezett vagy megerősített rendelés módosítására.

### <a name="introduction"></a>Bevezetés

Az alaptervezés számítása által művelet üzenetek jönnek létre a módosult szükségletekre válaszul. Ha például a szállítási dátum vagy a mennyiség megváltozott egy értékesítési rendelésben, amelyhez már létrehozta a beszerzési rendelést az igény kielégítésére. Ebben az esetben egy vagy több műveletkérő üzenetet hoz létre az alaptervezés számítás azért, hogy a beszerzési rendelést módosítsa. Eldöntheti, hogy megtörténjenek-e a javasolt módosítások.

Beállíthatja, hogy hogyan számítsák ki a műveleti üzeneteket ahhoz a fedezeti csoporthoz, amelyhez egy cikket csatol.

 <a name="selecting-action-messages"></a> Művelet üzenetek kijelölése
==========================

A **Fedezeti csoportok **lapon kiválaszthatja azokat a művelet üzeneteket, amelyeket szeretné ha a rendszer létrehozna, és azokat a fedezeti csoportokat vagy elemeket, amelyek az üzenetekre vonatkoznak. A következő műveleti üzenetek közül lehet választani.

| Üzenet             | Leírás                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Előleg**         | Ha bejelöli ezt az üzenetet, a rendszer létrehozza a szükséges műveleti üzeneteket annak érdeében, hogy áthelyezhesse a megrendeléseket egy korábbi dátumra. Az **Előleg árrés** mezőben megadhatja a bevételezés és kiadás közötti napok maximális számát előlegművelet nélkül. |
| **Halasztás**        | Ha bejelöli ezt az üzenetet, a rendszer létrehozza a szükséges műveleti üzeneteket annak érdekében, hogy áthelyezhesse a megrendeléseket egy későbbi dátumra. Az **Árrés halasztás** mezőben megadhatja a bevételezés és kiadás közötti napok maximális számát halasztás művelet nélkül.       |
| **Csökkentés**        | Ha bejelöli ezt az üzenetet, a termelési rendeléseket, a beszerzési rendeléseket és már bevételezési tranzakciókat csökkenteni kell a készlet szintek túllépésének megakadályozása érdekében.                                                                                                   |
| **Növelés**        | Ha bejelöli ezt az üzenetet, a termelési rendeléseket, a beszerzési rendeléseket és már bevételezési tranzakciókat növelni kell a készletben fellépő esetleges hiány megakadályozása érdekében.                                                                                                    |
| **Származtatott műveletek** | Ha bejelöli ezt az üzenetet, műveleti üzenetek jönnek létre a származtatott szükségletekhez, például a termelés teljesítő összetevő rendelések műveleteihez.                                                                                                   |




