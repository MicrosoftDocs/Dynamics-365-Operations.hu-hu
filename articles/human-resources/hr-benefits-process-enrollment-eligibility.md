---
title: Felvételi jogosultság feldolgozása
description: Ez a témakör a beiratkozási jogosultsági folyamat futtatását ismerteti.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8997cf24bf24097e46a05acffef8b3839056c57
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067629"
---
# <a name="process-enrollment-eligibility"></a>Felvételi jogosultság feldolgozása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a beiratkozási jogosultsági folyamat futtatását ismerteti.

1. A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza a **Felvételi jogosultság feldolgozása** lehetőséget.

2. A **Juttatásra vonatkozó felvételi jogosultságok futtatása** párbeszédpanelben adja meg a következő mezők értékeit:

   | Mező | Leírás |
   | --- | --- |
   | **Regisztrációs időszak** | A beléptetési jogosultságok feldolgozására szolgáló beléptetési időszak. |
   | **Jogi személy** | Az a jogi személy, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot. |
   | **Dolgozó** | Az a dolgozó, akihez kapcsolódóan fel kell dolgozni a felvételi jogosultságot. Ha ezt a mezőt üresen hagyja, a program minden dolgozónál feldolgozza a felvételi jogosultságot. |
   | **Juttatási terv** | Az a juttatási terv, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.

3. Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása a folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. A folyamat a megadott paraméterekkel fog futni.

4. Válassza ki az **OK** lehetőséget.

## <a name="view-process-results"></a>Folyamateredmények megtekintése

Ez a témakör a jogosultsági folyamatok eredményeinek megtekintését ismerteti.

1.  A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Eredmények feldolgozása** lehetőséget.

2.  A **Folyamat eredményei** lapon a következő mezők vannak megadva:

   | Mező | Leírás |
   | --- | --- |
   | **Folyamatazonosító** | A dolgozó, a jogi személy és a feldolgozás futtatása kombinációjának egyedi azonosítója. |
   | **Folyamat típusa** | Ez azonosítja a futtatott folyamatot. Például: Regisztráció. |
   | **Időbélyeg** | A jogosultsági folyamat futtatásának ideje. |
   | **Jogi személy** | A regisztrációs folyamat során megadott jogi személy. |
   | **Dolgozó** | A feldolgozott dolgozó. |
   | **Konstrukció | Az a juttatási konstrukció amelyre a regisztrációt megkísérelték. |
   | **Jogosultsági szabály** | A feldolgozott jogosultsági szabály. Ha hiba történt a jogosultság futtatása előtt, akkor ez a mező üresen marad. Például: Ha nincs beállítva kompenzáció egy dolgozóhoz, akkor a jogosultsági folyamat nem fog lefutni, és a mező üresen marad. |
   | **Eredményállapot** | Ez jogosult vagy nem jogosult lesz. Ha a dolgozó nem teljesítette a jogosultsági szabály feltételeit, akkor az eredmény állapota nem jogosult lesz, ha a dolgozó nem rendelkezik a szükséges adatokkal, például a fizetési gyakorisággal vagy a fix kompenzációval, vagy ha a juttatási konstrukcióban hiányzik egy olyan adat, amely megakadályozza a dolgozó regisztrációját. |
   | **Eredményüzenet** | Azt jelzi, hogy a dolgozó miért nem jogosult a juttatási konstrukcióra, vagy ha a jogosultsági szabály teljesült. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
