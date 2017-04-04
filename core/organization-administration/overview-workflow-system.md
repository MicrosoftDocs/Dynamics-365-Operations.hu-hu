---
title: "A munkafolyamat-rendszer áttekintése"
description: "A cikk ismerteti a Microsoft Dynamics 365 műveletek a munkafolyamat-rendszer."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 08c36f02f88fef7508730b6c01a1c99a0f77fb0c
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-system-overview"></a>A munkafolyamat-rendszer áttekintése

A cikk ismerteti a Microsoft Dynamics 365 műveletek a munkafolyamat-rendszer.

<a name="what-is-workflow"></a>Mi az a munkafolyamat?
-----------------

A *munkafolyamat* kifejezést kétféle módon lehet meghatározni: rendszerként és üzleti folyamatként.
### <a name="workflow-is-a-system"></a>A munkafolyamat egy rendszer

A munkafolyamat egy olyan rendszer, amely telepítve van Dynamics 365 műveletekhez és az Application Object Server (AOS) futó. A munkafolyamat rendszer egy olyan funkciót biztosít, amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat.

### <a name="workflow-is-a-business-process"></a>A munkafolyamat egy üzleti eljárás

A munkafolyamat egy üzleti folyamatot jelent. Azt határozza meg, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása. Az alábbi ábra szemlélteti a költségjelentések munkafolyamatát. ![Munkafolyamatok felhasználókhoz rendelt elemekkel](./media/workflow_user.gif) Ezen munkafolyamat könnyebb megsimeréséhez tegyük fel, hogy Sam elküld egy költségjelentést 7000 USD értékben. Ebben az esetben Ivánnak ellenőriznie kell a számlákat, amelyeket Sam irányított hozzá. Ezt követően Ferencnek és Zsuzsannának jóvá kell hagynia a költségjelentést. Ezután tegyük fel, hogy Sam benyújt egy újabb költségjelentést, ezúttal 11 000 dollárról. Ebben az esetben Ivánnak ellenőriznie kell a nyugtákat, majd Ferencnek, Zsuzsannának és Annának is jóvá kell hagynia a költségjelentést.
 A munkafolyamat rendszer használatának előnyei
-------------------------------------

A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:
-   **Egységes folyamatok** — Meghatározhatja az egyes dokumentumok, például a beszerzési igénylések és költségjelentések feldolgozását. A munkafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.
-   **A folyamat láthatósága** – Nyomon követheti a munkafolyamat-példányok állapotát, előzményeit és teljesítmény metrikáit. Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.
-   **Központi munkalista** – a felhasználók centralizált munkalistát tekinthetnek meg, amely megjeleníti a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.




