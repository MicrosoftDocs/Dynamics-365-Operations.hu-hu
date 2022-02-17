---
title: Módosítások arányának feldolgozása
description: Ez a téma elmagyarázza, hogyan kell feldolgozni a juttatási mértékek módosítását a Microsoft Dynamics 365 Human Resources rendszerben.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e0dfbdde8ee950a0341fffb1e268fff05434953
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070375"
---
# <a name="process-rate-changes"></a>Módosítások arányának feldolgozása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör elmagyarázza, hogyan kell feldolgozni a Microsoft Dynamics 365 Human Resources rendszerben a juttatási díjak módosítását, amikor egy új vagy meglévő juttatási terv jogosultsági szabályainak beállításai megváltoznak. Ha új jogosultsági szabályt létre, majd hozzárendeli a tervhez, akkor a rendszer újból lefuttatja az ellenőrzést arra vonatkozóan, hogy a dolgozó jogosult-e a tervre az új jogosultsági lehetőségek alapján. 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
