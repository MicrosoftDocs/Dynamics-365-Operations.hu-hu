---
title: Kérdőívek terjesztése ütemezés segítségével
description: A Kérdőív-ütemezés lehetővé teszi a kérdőívek tervezését és több válaszadónak történő terjesztését.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4885c11f0cb508edb8ebf3aef14748e819113264
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067402"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Kérdőívek terjesztése ütemezés segítségével


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Kérdőív-ütemezés lehetővé teszi a kérdőívek tervezését és több válaszadónak történő terjesztését. Ez az eljárás az USMF bemutatócéget használja.

## <a name="create-a-questionnaire-schedule"></a>Hozzon létre egy kérdőív-ütemezést

1. Menj **Kérdőív** > **Terjeszteni** > **Kérdőívek ütemezése**.

2. Kattintson az **Új** elemre.

3. Ban,-ben **Ütemezés** mezőbe írjon be egy értéket.

4. Írjon egy értéket a **Leírás** mezőbe.
    * Állítsa be az ütemezést **Névtelen** ha a válaszokat a válaszhoz társított nevek nélkül kell rögzíteni.  
    * A névtelen eredmények engedélyezését először be kell állítani a HR-paraméterek között.  

5. Ban,-ben **típus** mezőben válassza ki a tervezés típusát.  Ebben a példában a **Elégedettség** típus.

6. Keresse meg és jelölje ki a kívánt rekordot a listán.

7. A listában kattintson a kijelölt sorban lévő hivatkozásra.

8. Adja meg a dátumot a **Dátum** mezőben.

9. Bontsa ki a **E-mail az alkalmazotti önkiszolgáló számára** szakasz.

10. Írjon be egy értéket a **Tárgy** mezőbe.

    * Példa: Kérdőív elérhető  

11. Ban,-ben **Szöveg** mezőbe írja be az e-mail üzenet törzsét. Ne feledje, a változó felhasználható értékek behelyettesítésére a rendszerben.

    * Példa: Kedves %P%! Kérjük, jelentkezzen be az Alkalmazotti önkiszolgáló rendszerbe a munkaerő-egészségügyi kérdőív kitöltéséhez.  Contoso  

12. Kattintson a **Mentés** gombra.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>A Beállítás részletei segítségével válassza ki a megválaszolandó kérdőívet, valamint a válaszadók kiválasztásához használt lekérdezést.

1. Kattintson **Beállítás részletei**.

2. A listában válassza ki a kérdőívhez tartozó válaszadók megkereséséhez használni kívánt lekérdezést.

    * Példa: munkavállalók  

3. Kattintson **Lekérdezés megtekintése vagy módosítása** konkrét személyek kiválasztásához vagy a lekérdezés módosításához, hogy megtalálja azokat, akik megfelelnek bizonyos feltételeknek.

    * Vegye figyelembe, hogy az összes válaszadónak a rendszerben is felhasználónak kell lennie.  

4. A listában jelölje be a Személy sort.

5. A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.

    * Válassza ki Julia Funderburkot  

6. A listában válassza ki Julia Funderburkot

7. Kattintson az **OK** gombra.

8. Kattints a **Kérdőívek** lapon.

9. A fában bontsa ki a kérdőívtípus csomópontját **Elégedettségi felmérés**.

10. A fastruktúrában jelölje be a „Munkaerő-egészségügyi vizsgálat” lehetőséget.

11. Kattintson az **OK** gombra.

12. Kattintson **Tervezett válaszmenet**.

    * Vegye figyelembe, hogy **Tervezett válaszmenetek** minden kiválasztott/lekérdezett felhasználóhoz létrejöttek.  

13. Zárja be a lapot.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Annak érdekében, hogy a kérdőív a teljesítéshez szükséges válaszadók számára elérhető legyen, indítsa el a kérdőív-ütemezést.

1. Kattintson a **Funkciók** elemre.

2. Kattintson a **Start** parancsra.

3. Kattintson az **OK** gombra.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Küldje el az e-mailt az elérhető kérdőívek válaszadóinak tájékoztatására.

1. Kattintson a **Funkciók** elemre.

2. Kattintson **Küldjön e-mailt**.

3. Kattintson a **Mégse** gombra.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Használjon Tervezett válaszmunkameneteket annak megfigyelésére, hogy kinek kell kitöltenie a kérdőívet.

1. Kattintson **Tervezett válaszmenet**.

    * Törölje a fennmaradó tervezett munkamenet bármelyikét, amikor készen áll az ütemezett munka befejezésére.  

2. Kattintson a **Törlés** gombra.

3. Kattintson az **Igen** gombra.

4. Zárja be a lapot.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Ha az összes válaszadó kitöltötte a kérdőívet és/vagy az összes fennmaradó Tervezett válaszmunkamenet törlésre került, zárja le az ütemezést.

1. Kattintson a **Funkciók** elemre.
2. Kattintson **Vége**.
3. Kattintson az **OK** gombra.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
