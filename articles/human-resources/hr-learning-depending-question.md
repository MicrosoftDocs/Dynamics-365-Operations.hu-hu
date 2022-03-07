---
title: A kérdés függővé tétele az előző kérdésre adott választól
description: A feltételes kérdések segítségével meghatározhatja, hogy ilyen további kérdések jelennek meg a válaszadónak az előző kérdésekre adott válaszai alapján.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f28f75a902121f23c92a919b539517dbdb191447
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066725"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>A kérdés függővé tétele az előző kérdésre adott választól


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



A feltételes kérdések segítségével meghatározhatja, hogy ilyen további kérdések jelennek meg a válaszadónak az előző kérdésekre adott válaszai alapján. Például, ha megkérdezni hogy a „Kávét vagy a teát szereti-e” meghatározható egy logikus további kérdés az alapján, hogy a válaszadó a kávét vagy a teát választja-e. Ez az eljárás az USMF bemutatócéget használja.


## <a name="find-the-existing-questionnaire"></a>Meglévő kérdőív megkeresése
1. Menj **Kérdőív** > **Tervezés** > **Kérdőívek**.
2. A listában válassza ki a WorkFH kérdőívet.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Összes kérdés és alkérdés hozzáadása a Kérdőívhez
1. Kattintson **Kérdések**.
2. Kattintson az **Új** elemre.
3. Ban,-ben **Kérdés** mezőben válassza ki a 00016-os kérdést.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson a **Mentés** gombra.
7. Zárja be a lapot.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Kérdőív sorrendjének Feltételesre állítása, és a kérdés függővé tétele a megfelelő kérdéstől
1. Kattintson a **Szerkesztés** lehetőségre.
2. Bontsa ki a **Beállítások** szakaszt.
3. Ban,-ben **Kérdések sorrendje** mezőben válassza a „Feltételes” lehetőséget.
4. Kattintson **Feltételes** kérdés.
5. A fanézetben jelölje ki a „Kérdések\Magyarázza el, hogy miért válaszolt így az előző kérdésre?” lehetőséget.
6. Ban,-ben **Elsődleges kérdés** mezőben válassza ki a 00009-es kérdést.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Ban,-ben **Válasz** mezőbe írja be annak a válaszlehetőségnek a válaszsorozat azonosítóját, amelytől a kérdést függővé szeretné tenni. Például adja meg az 1 értéket az első válaszlehetőséghez.
9. Kattintson a **Mentés** gombra.
10. A fanézetben válassza ki a „Kérdések\Rendesen megfizetik a munkámat” lehetőséget.
    * Vegye figyelembe, hogy a kérdésfa frissül a függőségek jelzése érdekében.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
