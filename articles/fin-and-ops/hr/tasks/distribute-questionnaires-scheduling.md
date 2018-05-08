--- 
title: "Kérdőívek terjesztése ütemezés segítségével"
description: "A Kérdőív-ütemezés lehetővé teszi a kérdőívek tervezését és több válaszadónak történő terjesztését."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6795c5ed48ef1d716ddec5cca1a2f6414bb318ce
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="distribute-questionnaires-using-scheduling"></a>Kérdőívek terjesztése ütemezés segítségével

[!include [task guide banner](../../includes/task-guide-banner.md)]

A Kérdőív-ütemezés lehetővé teszi a kérdőívek tervezését és több válaszadónak történő terjesztését. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-questionnaire-schedule"></a>Hozzon létre egy kérdőív-ütemezést
1. Ugrás a Kérdőív > Elosztás > Kérdőív-ütemezések elemre.
2. Kattintson az Új lehetőségre.
3. Az Ütemezési mezőbe írjon be egy értéket.
4. A Leírás mezőben adjon meg egy értéket.
    * Állítsa be az ütemezést névtelen értékre, ha a válaszokat a válaszhoz tartozó nevek nélkül kell rögzíteni.  
    * A névtelen eredmények engedélyezését először be kell állítani a HR-paraméterek között.  
5. Válassza ki a Tervezési típust a Típus mezőben.  Ebben a példában az Elégedettség típust fogjuk használni.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Adja meg a dátumot a Dátum mezőben.
9. Bontsa ki az E-mail az alkalmazotti önkiszolgáló rendszernek szakaszt.
10. Írjon be egy értéket a Tárgy mezőbe.
    * Példa: Kérdőív elérhető  
11. A Szöveg mezőbe írja be az e-mail főszövegét. Ne feledje, a változó felhasználható értékek behelyettesítésére a rendszerben.
    * Példa: Kedves %P%! Kérjük, jelentkezzen be az Alkalmazotti önkiszolgáló rendszerbe a munkaerő-egészségügyi kérdőív kitöltéséhez.  Contoso  
12. Kattintson a Mentés gombra.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>A Beállítás részletei segítségével válassza ki a megválaszolandó kérdőívet, valamint a válaszadók kiválasztásához használt lekérdezést.
1. Kattintson a Beállítás részleteire.
2. A listában válassza ki a kérdőívhez tartozó válaszadók megkereséséhez használni kívánt lekérdezést.
    * Példa: munkavállalók  
3. Kattintson a Lekérdezés megtekintése vagy módosítására specifikus személy kiválasztához vagy a lekérdezés módosításához a megadott feltételeknek megfelelő személyek megkereséséhez.
    * Vegye figyelembe, hogy az összes válaszadónak a rendszerben is felhasználónak kell lennie.  
4. A listában jelölje meg a Személy sort
5. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki Julia Funderburkot  
6. A listában válassza ki Julia Funderburkot
7. Kattintson az OK gombra.
8. Kattintson a Kérdőívek lapra.
9. A fastruktúrában bontsa ki az „Elégedettségi felmérés típusú kérdőív csomópontját”.
10. A fastruktúrában jelölje be a „Munkaerő-egészségügyi vizsgálat” lehetőséget.
11. Kattintson az OK gombra.
12. Kattintson a Tervezett válaszmunkamenetre.
    * Vegye figyelembe, hogy a tervezett válaszadási munkameneteket kiválasztott/kérdezhető felhasználónként hozzák létre.  
13. Zárja be a lapot.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Annak érdekében, hogy a kérdőív a teljesítéshez szükséges válaszadók számára elérhető legyen, indítsa el a kérdőív-ütemezést.
1. Kattintson a Funkciók elemre.
2. Kattintson a Start elemre.
3. Kattintson az OK gombra.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Küldje el az e-mailt az elérhető kérdőívek válaszadóinak tájékoztatására.
1. Kattintson a Funkciók elemre.
2. Kattintson az E-mail küldése elemre.
3. Kattintson a Mégse gombra.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Használjon Tervezett válaszmunkameneteket annak megfigyelésére, hogy kinek kell kitöltenie a kérdőívet.
1. Kattintson a Tervezett válaszmunkamenetre.
    * Törölje a fennmaradó tervezett munkamenet bármelyikét, amikor készen áll az ütemezett munka befejezésére.  
2. Kattintson a Törlés gombra.
3. Kattintson az Igen gombra.
4. Zárja be a lapot.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Ha az összes válaszadó kitöltötte a kérdőívet és/vagy az összes fennmaradó Tervezett válaszmunkamenet törlésre került, zárja le az ütemezést.
1. Kattintson a Funkciók elemre.
2. Kattintson a Vége gombra.
3. Kattintson az OK gombra.


