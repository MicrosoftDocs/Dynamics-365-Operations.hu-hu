---
title: Mértékváltozások feldolgozása
description: A juttatási mérték változásainak feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben, ha egy új vagy meglévő juttatási terv módosult a jogosultsági szabály beállításaiban.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: da42ef6ea91b95903316e35b551b222b8ff3b946
ms.sourcegitcommit: 9723b5ff40c84677316d71e185cf862556b32cf9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2020
ms.locfileid: "3741459"
---
# <a name="process-rate-changes"></a>Mértékváltozások feldolgozása

A juttatási mérték változásainak feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben, ha egy új vagy meglévő juttatási terv módosult a jogosultsági szabály beállításaiban. Ha új jogosultsági szabályt létre, majd hozzárendeli a tervhez, akkor a rendszer újból lefuttatja az ellenőrzést arra vonatkozóan, hogy a dolgozó jogosult-e a tervre az új jogosultsági lehetőségek alapján. 

1. A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza a **Mértékváltozásra vonatkozó frissítés feldolgozása** lehetőséget.

2. A **Juttatásra vonatkozó mértékfrissítés futtatása** párbeszédpanelben adja meg a következő mezők értékeit:

   | Mező | Leírás |
   | --- | --- |
   | **Regisztrációs időszak** | Beléptetési időszak, amelyhez a mértékben történt változtatás feldolgozása szükséges. |

3. Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása a folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. A folyamat a megadott paraméterekkel fog futni.

4. Válassza ki az **OK** lehetőséget.
