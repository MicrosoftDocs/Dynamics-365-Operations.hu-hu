---
title: Fordítva feladott lízingtranzakciók
description: Ez a témakör a feladott lízingtranzakciók sztornírozását ismerteti. Az eszközlízing útján létrehozott tranzakciók sztornírozhatók.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22d8eee22221efaf5e7a715c8b95dff261bee62f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249725"
---
# <a name="reverse-posted-lease-transactions"></a>Fordítva feladott lízingtranzakciók

[!include [banner](../includes/banner.md)]

Az eszközlízing útján létrehozott tranzakciók sztornírozhatók. Az eszközlízing-szolgáltatás által sztornírozott tranzakciók frissítik a lízingadatokat. Ezért frissítik továbbá a lízingkötelezettség és a használatijog-eszköz (ROU) könyv szerinti értékét is.

Sztornírozási tranzakció létrehozásához kövesse az alábbi lépéseket.

1. Az **Eszköztranzakciók** vagy a **Kötelezettségtranzakciók** lapon válassza ki a tranzakciót, majd válassza a **Tranzakció sztornírozása** lehetőséget.
2. A megjelenő párbeszédpanelen módosíthatja a sztornírozó bejegyzés feladásának dátumát. Alapértelmezés szerint a **Dátum mező** a kiválasztott tranzakció tranzakciófeladási dátumára van beállítva. A sztornírozó tétel nem adható fel a kijelölt tranzakció eredeti könyvelési dátumánál korábban.
3. Válassza ki az **OK** lehetőséget. A program olyan naplóbejegyzést ad fel, amely sztornírozza a kijelölt tételt. A sztornírozás az **Eszköztranzakciók** vagy a **Kötelezettségtranzakciók** oldalon jelenik meg, és frissül az oldalon megjelenő aktuális egyenleg nettó összege.

Ha a **Sztornírozott nyomkövetés** lehetőséget választja, megjelenik egy párbeszédpanel, amely az eredeti és a sztornírozott tranzakciókat is megjeleníti, valamint egy kapcsolódó számot, amelyet *nyomkövetési számnak* nevezünk. A sztornírozás megkönnyítése és a láthatóság javítása érdekében a lízingütemezések használatával is nyomon követheti a sztornírozásokat.

Az **Ütemezés** lap **Legutóbbi naplószáma** mezője a tranzakciók naplószámait mutatja. A tranzakció sztornírozása esetén ez a mező a sztornírozási tranzakció naplószámával frissül. Ezenkívül a **Sztornírozott** jelölőnégyzet be van jelölve, jelezve, hogy a tranzakció sztornírozott, és a **Feladott** mező be van jelölve.

## <a name="revoke-a-reversed-transaction"></a>Sztornírozott tranzakció visszavonása

Sztornírozott tranzakció visszavonásához kövesse az alábbi lépéseket.

1. Az **Ütemezés** vagy a **Tranzakciók** lapon jelölje ki az eredeti tranzakciót.
2. Tegye a következők egyikét:

    - Ha a tranzakciót az **Ütemezés** lapon jelölte ki, kövesse a napló létrehozásának lépéseit a [Havi naplóbejegyzések létrehozása kötegben](create-monthly-journals-batch.md) című részben. A naplót manuálisan kell feladnia.
    - Ha a tranzakciót a **Tranzakciók** lapon választotta ki, válassza a **Tranzakció sztornírozása** lehetőséget. Megjelenik egy üzenet, amely szerint ez a visszavonás egy korábbi sztornírozás visszavonása, és hogy szerkesztheti a visszavonás feladási dátumát. Az általános üzleti ellenőrzések azonban hatással vannak a **Dátum** mezőben beírható dátumokra. 

3. Válassza ki az **OK** lehetőséget. A program olyan naplóbejegyzést ad fel, amely sztornírozza a kijelölt tételt. A sztornírozás a **Tranzakciók** lapon jelenik meg, és a nettó teljes aktuális egyenleg visszaáll az első sztornírozás előtti helyre. Ezért a visszavonásnak az egyenlegre gyakorolt hatása egyértelmű.

Ha a **Sztornírozott nyomkövetés** lehetőséget választja, megjelenik egy párbeszédpanel, amely az eredeti és a sztornírozott tranzakciókat is megjeleníti egy nyomkövetési számmal együtt.

A visszavonásokat a megfelelő **Ütemezések** lapon is nyomon követheti. A **Sztornírozott** mező törlődik, míg a **Feladott napló** mező be van jelölve. Ezenkívül a **Legkésőbbi naplószám** mező frissül a visszavonási tranzakció naplószámával, és a **Naplószám** mező a sztornírozási naplószámmal frissül.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]