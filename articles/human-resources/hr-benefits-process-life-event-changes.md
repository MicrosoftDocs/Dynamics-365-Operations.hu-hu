---
title: Életesemények változásainak feldolgozása
description: Ez a téma elmagyarázza, hogyan kell feldolgozni az életesemény-változásokat a Microsoft Dynamics 365 Human Resources rendszerben.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 30834b685c535d464dbe016d92579752fac4b7fa
ms.sourcegitcommit: 4f9c889e5cf72f34dd9746a322f8c0d6b983037b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2021
ms.locfileid: "7417461"
---
# <a name="process-life-event-changes"></a>Életesemények változásainak feldolgozása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Két életeseményben végrehajtott módosítás feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben:

- Születésnapra vonatkozó változtatások
- A jogosultsági szabály felülírja a lejárati változtatásokat 

1. A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életesemény módosításának feldolgozása** lehetőséget.

2. Az **Életeseményben történt módosításra vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:

   | Mező | Leírás |
   | --- | --- |
   | Regisztrációs időszak | Az életesemények módosításainak feldolgozására szolgáló beléptetési időszak. |
   | Jogi személy | Az a jogi személy, amelyre vonatkozóan fel kell dolgozni az életeseményben történt módosításokat. |

3. Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása a folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. A folyamat a megadott paraméterekkel fog futni.

4. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
