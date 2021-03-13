---
title: Felvételi jogosultság feldolgozása
description: Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 69ea23e4051a6975a5892cd027777c5a88472509
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112845"
---
# <a name="process-enrollment-eligibility"></a>Felvételi jogosultság feldolgozása

Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.

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

Ez a cikk bemutatja, hogyan lehet megtekinteni a jogosultsági folyamat eredményeit.

1.  A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Eredmények feldolgozása** lehetőséget.

2.  A **Folyamateredmények** képernyőn a következő mezők vannak megadva:

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

