---
title: A munkafolyamat-rendszer áttekintése
description: Ez a témakör bemutatja a munkafolyamat rendszert.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eef77a5d81d12ec92eea86b1dd9902d9e3d80b33
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812363"
---
# <a name="workflow-system-overview"></a>A munkafolyamat-rendszer áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a munkafolyamat rendszert.

## <a name="what-is-workflow"></a>Mi az a munkafolyamat?

A *munkafolyamat* kifejezést kétféle módon lehet meghatározni: rendszerként és üzleti folyamatként.

### <a name="workflow-is-a-system"></a>A munkafolyamat egy rendszer

A munkafolyamat olyan rendszer, amely az Application Object Server (AOS) kiszolgálón fut. A munkafolyamat rendszer egy olyan funkciót biztosít, amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat.

### <a name="workflow-is-a-business-process"></a>A munkafolyamat egy üzleti eljárás

A munkafolyamat egy üzleti folyamatot jelent. Azt határozza meg, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása. Az alábbi illusztráció szemlélteti a költségjelentések munkafolyamatát.

![Munkafolyamat felhasználókhoz rendelt elemekkel](./media/workflow_user.gif)

A munkafolyamat könnyebb megértésének érdekében tegyük fel, hogy Balázs benyújt egy 7000 dolláros költségjelentést. Ebben az esetben Ivánnak ellenőriznie kell a számlákat, amelyeket Sam irányított hozzá. Ezt követően Ferencnek és Zsuzsannának jóvá kell hagynia a költségjelentést. Ezután tegyük fel, hogy Sam benyújt egy újabb költségjelentést, ezúttal 11 000 dollárról. Ebben az esetben Ivánnak ellenőriznie kell a nyugtákat, majd Ferencnek, Zsuzsannának és Annának is jóvá kell hagynia a költségjelentést.

## <a name="benefits-of-using-the-workflow-system"></a> A munkafolyamat rendszer használatának előnyei

A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:

- **Egységes folyamatok** — Meghatározhatja az egyes dokumentumok, például a beszerzési igénylések és költségjelentések feldolgozását. A munkafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.
- **A folyamat láthatósága** – Nyomon követheti a munkafolyamat-példányok állapotát, előzményeit és teljesítmény metrikáit. Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.
- **Központi munkalista** – a felhasználók centralizált munkalistát tekinthetnek meg, amely megjeleníti a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat.


## <a name="workflow-content"></a>Munkafolyamat-tartalom

+ [A munkafolyamat-rendszer felépítése](workflow-system-architecture.md)
+ [Munkafolyamat-elemek](workflow-elements.md)
+ [Munkafolyamat-jóváhagyási folyamatok műveletei](workflow-actions.md)
+ [Munkafolyamatok létrehozása – áttekintés](create-workflow.md)
+ [Munkafolyamat-tulajdonságok konfigurálása](configure-workflow-properties.md)
+ [Manuális feladatok konfigurálása munkafolyamatban](configure-manual-task-workflow.md)
+ [Automatizált feladatok konfigurálása munkafolyamatban](configure-automated-task-workflow.md)
+ [Jóváhagyási folyamatok konfigurálása munkafolyamatban](configure-approval-process-workflow.md)
+ [Jóváhagyási lépések konfigurálása munkafolyamatban](configure-approval-step-workflow.md)
+ [Manuális döntések konfigurálása munkafolyamatban](configure-manual-decision-workflow.md)
+ [Feltételes döntések konfigurálása munkafolyamatban](configure-conditional-decision-workflow.md)
+ [Párhuzamos tevékenységek beállítása munkafolyamatban](configure-parallel-activity-workflow.md)
+ [Párhuzamos ágak konfigurálása munkafolyamatban](configure-parallel-branch-workflow.md)
+ [Sortétel munkafolyamatainak konfigurálása](configure-line-item-workflow.md)
+ [Munkafolyamat GYIK](workflow-FAQ.md)
