---
title: "Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok"
description: "Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó. A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 27c211e6ded17e085559add916c28a48c40e5b8e
ms.lasthandoff: 03/31/2017


---

# <a name="procurement-and-sourcing-workflows"></a>Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok

[!include[banner](../includes/banner.md)]


Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó. A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.

A munkafolyamat egy üzleti folyamatot jelent. Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot. A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:
-   **Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét. A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.
-   **A folyamat láthatósága** – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit. Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.
-   **Központi munkalista** – A felhasználók megtekinthetik a központi munkalistát, hogy lássák a munkafolyamat-feladatokat és jóváhagyásokat, amelyek hozzájuk vannak rendelve, minden olyan munkafolyamat során, amelyben részt vesznek. Ez a Munkatételek lapon érhető el.

## <a name="the-types-of-workflows-that-you-can-create"></a> A létrehozható munkafolyamat-típusok
A következő munkafolyamat-típusok elérhetőek a Beszerzés és forrás modulhoz.

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **Típus**                         | **Típus**                                          |
| Beszerzési igénylés ellenőrzése      | Ellenőrzési munkafolyamatok létrehozása beszerzési igényekhez.            |
| Beszerzési igénylési sor ellenőrzése | Ellenőrzési munkafolyamatok létrehozása beszerzésiigény-sorokhoz.       |
| Beszerzési rendelés munkafolyamata          | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési rendelésekhez.     |
| Beszerzésirendelés-sor munkafolyamata     | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésirendelés-sorokhoz. |

## <a name="creating-a-workflow"></a>Munkafolyamat létrehozása
Hogy létrehozzon egy munkafolyamatot lépjen a Beszerzés és forrás &gt; Beállítás &gt; Beszerzés és forrás munkafolyamatok elemre és hozzon létre egy új munkafolyamatot a készíteni kívánt munkafolyamat-típus kiválasztásával.  

A munkafolyamat vásznon behúzhatja a munkafolyamat elemeket a szerkesztőbe és bekapcsolhatja az elemeket egy folyamatba. A munkafolyamat-elemeket tanácsos konfigurálni. Jóváhagyás– és feladat munkafolyamat-elemekhez konfigurálhatja, hogy melyik résztvevőknek ajánlott cselekedniük.
Résztvevőtípusok
----------------------

Jóváhagyási lépéseket rendelhet a következő résztvevőcsoportokhoz.

| Felhasználócsoport    | Leírás                                                               |
|---------------|---------------------------------------------------------------------------|
| Résztvevő   | A jóváhagyási lépés hozzárendelése egy csoport vagy szerepkör tagjaihoz.                   |
| Hierarchia     | A jóváhagyási lépés hozzárendelése egy meghatározott szervezeti hierarchiában lévő felhasználókhoz. |
| Munkafolyamat felhasználója | A jóváhagyási lépés hozzárendelése a munkafolyamatban lévő felhasználókhoz.                       |
| Várakozási sor         | Rendelje hozzá a jóváhagyási lépést egy munkatétel-várólistához.                            |
| Felhasználó          | Jóváhagyási lépés hozzárendelése adott felhasználókhoz.                               |



<a name="see-also"></a>Lásd még
--------

[Üzleti folyamatok munkafolyamatainak meghatározása beszerzési igénylések számára](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Beszerzési igénylési munkafolyamat](purchase-requisitions-workflow.md)




