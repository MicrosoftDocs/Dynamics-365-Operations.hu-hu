---
title: Életesemények feldolgozása
description: A Microsoft Dynamics 365 Human Resources alkalmazotti életciklusa során minden alkalmazott találkozhat különböző életeseményekkel kapcsolatos változásokkal.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ef160af483f81b8c1e60a274029b77c3cd34f924
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324788"
---
# <a name="process-life-events"></a>Életesemények feldolgozása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources alkalmazotti életciklusa során minden alkalmazott találkozhat különböző életeseményekkel kapcsolatos változásokkal. Például a házasság, a foglalkoztatás változása vagy a függő fél/kedvezményezett változása. Az életesemények használatához engedélyeznie kell az életeseményeket a **Juttatások paraméterei** oldalon, be kell állítania az életeseménytípusokat, és be kell állítania az életesemény opciókat a tervtípusokhoz.

Az életesemények feldolgozása előtt a felvételi időkereten belül már legalább egyszer futtatni kell a nyitott jelentkezést. Az Egyesült Államokban a nyitott jelentkezés általában évente egyszer történik. Az Egyesült Államokon kívül nyitott jelentkezés a felvételkor történik. A dolgozónak nem kell kiválasztania juttatási tervet az életesemények feldolgozásához, viszont a nyitott jelentkezés feldolgozásakor szerepelniük kell. 

Az életesemény feldolgozását akkor érdemes használni, ha olyan alkalmazottai vannak, akiknél a jövőben történik életesemény. Ez az esemény feldolgozza az összes olyan életeseményt, amelyeket nem dolgoztak fel (például a jövőbeli életeseményeket, illetve olyan életeseményeket, amelyek nem egyetlen dolgozóra jellemzőek – például egy új juttatás). A valós idejű életesemények el vannak rejtve.

Ha például ma február elseje van, és február 14-én Joe Smith dolgozónak időpontja van a jogi személyiségével kapcsolatos módosításra, a február 15-én futtatott eseményfeldolgozás során a rendszer feldolgoz minden, február 15-ig történt eseményt. 

1. A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életesemény feldolgozása** lehetőséget.

2. Az **Életeseményre vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:

   | Mező | Leírás |
   | --- | --- |
   | **Regisztrációs időszak** | Az életesemények feldolgozására szolgáló beléptetési időszak. |
   | **Jogi személy** | Jogi személy, amelynek életeseményre vonatkozó feldolgozásra van szüksége. |
   | **Életesemény dátuma** | A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban. |
   | **Dolgozó** | Az a dolgozó, akivel kapcsolatban fel kell dolgozni az életeseményt. Ha ezt a mezőt üresen hagyja, a program minden dolgozónál feldolgozza az életeseményeket. |

3. Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása a folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. A folyamat a megadott paraméterekkel fog futni.

4. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
