---
title: "Munkafolyamat – áttekintés"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operationsben használható munkafolyamat-rendszert írja le."
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6622f0e5ed6c38bb8131d13aa02061968862678b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-overview"></a>Munkafolyamat – áttekintés

[!include[banner](../includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 for Finance and Operationsben használható munkafolyamat-rendszert írja le.

<a name="what-is-workflow"></a>Mi az a munkafolyamat?
-----------------

A *munkafolyamat* kifejezést kétféle módon lehet meghatározni: rendszerként és üzleti folyamatként.
### <a name="workflow-is-a-system"></a>A munkafolyamat egy rendszer

A munkafolyamat egy, a Finance and Operations rendszerben telepített rendszer, amely az Application Object Server (AOS) alatt fut. A munkafolyamat rendszer egy olyan funkciót biztosít, amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat.

### <a name="workflow-is-a-business-process"></a>A munkafolyamat egy üzleti eljárás

A munkafolyamat egy üzleti folyamatot jelent. Azt határozza meg, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása. Az alábbi illusztráció szemlélteti a költségjelentések munkafolyamatát. 

![Munkafolyamat felhasználókhoz rendelt elemekkel](./media/workflow_user.gif) 

A munkafolyamat könnyebb megértésének érdekében tegyük fel, hogy Balázs benyújt egy 7000 dolláros költségjelentést. Ebben az esetben Ivánnak ellenőriznie kell a számlákat, amelyeket Sam irányított hozzá. Ezt követően Ferencnek és Zsuzsannának jóvá kell hagynia a költségjelentést. Ezután tegyük fel, hogy Sam benyújt egy újabb költségjelentést, ezúttal 11 000 dollárról. Ebben az esetben Ivánnak ellenőriznie kell a nyugtákat, majd Ferencnek, Zsuzsannának és Annának is jóvá kell hagynia a költségjelentést.

## <a name="benefits-of-using-the-workflow-system"></a> A munkafolyamat rendszer használatának előnyei

A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:
-   **Egységes folyamatok** — Meghatározhatja az egyes dokumentumok, például a beszerzési igénylések és költségjelentések feldolgozását. A munkafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.
-   **A folyamat láthatósága** – Nyomon követheti a munkafolyamat-példányok állapotát, előzményeit és teljesítmény metrikáit. Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.
-   **Központi munkalista** – a felhasználók centralizált munkalistát tekinthetnek meg, amely megjeleníti a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.


## <a name="workflow-content"></a>Munkafolyamat-tartalom

+ [Munkafolyamat felépítése](workflow-system-architecture.md)
+ [Munkafolyamat-elemek](workflow-elements.md)
+ [Munkafolyamat-műveletek](workflow-actions.md)
+ [Munkafolyamat létrehozása](create-workflow.md)
+ [Munkafolyamat-tulajdonságok konfigurálása](configure-workflow-properties.md)
+ [Manuális feladat konfigurálása munkafolyamatban](configure-manual-task-workflow.md)
+ [Automatikus feladat konfigurálása munkafolyamatban](configure-automated-task-workflow.md)
+ [Jóváhagyási folyamat konfigurálása munkafolyamatban](configure-approval-process-workflow.md)
+ [Jóváhagyási lépés konfigurálása munkafolyamatban](configure-approval-step-workflow.md)
+ [Manuális döntés konfigurálása munkafolyamatban](configure-manual-decision-workflow.md)
+ [Feltételes döntés konfigurálása munkafolyamatban](configure-conditional-decision-workflow.md)
+ [Párhuzamos tevékenység beállítása munkafolyamatban](configure-parallel-activity-workflow.md)
+ [Párhuzamos ágának konfigurálása munkafolyamatban](configure-parallel-branch-workflow.md)
+ [Sortétel munkafolyamatának konfigurálása](configure-line-item-workflow.md)

