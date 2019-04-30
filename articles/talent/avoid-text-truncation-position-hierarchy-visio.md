---
title: Szövegcsonkolás elkerülése a pozícióhierarchiában és exportálás a Visio szolgáltatásba
description: Ez a témakör ismerteti azoknak a problémáknak a megoldását, ahol a magánszemélyek nevei és a beosztások csonkolva jelennek meg, amikor a vevő megtekinti a beosztáshierarchiát a Dynamics 365 for Talent szolgáltatásban. A szöveg csonkolt megjelenítése megnehezítheti a képernyőkép készítését vagy a hierarchia nyomtatását.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 87d1c1994b14fac45fa305a9223ed45ee363a70c
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "859897"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Szövegcsonkolás elkerülése a pozícióhierarchiában és exportálás a Visio szolgáltatásba

[!include [banner](includes/banner.md)]

**Kibocsátás**

Amikor a vevő megtekinti a beosztáshierarchiát a Microsoft Dynamics 365 for Talent szolgáltatásban, a magánszemélyek nevei és a beosztások csonkolva jelennek meg. Ez megnehezítheti a képernyőkép készítését, vagy a hierarchia nyomtatását és terjesztését.

![Beosztáshierarchia](media/position-h.png)

**Ok**

Ez szándékosan van.

**Felbontás**

Azonban a felhasználók nem egyszerűen válthat a szöveg méretét. Azonban exportálni tudja a beosztáshierarchiát a Talent szolgáltatásból, majd importálhatja a Microsoft Visio szolgáltatásba. Annak ellenére, hogy a következő cikk a Microsoft Dynamics AX 2012-re vonatkozóan íródott, a folyamat a Talent szolgáltatásra is érvényes: [Beosztáshierarchia exportálása a Microsoft Visio alkalmazásba](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Kövesse ezeket a lépéseket a Visio alkalmazásba való exportáláshoz.

1. A Talent alkalmazásban nyissa meg a **Beosztások** listaoldalt.

    Ha több információt szeretne szerepeltetni a szervezetistruktúra-diagramban, adjon mezőket a **Beosztások** listához, így ezek elérhetőek lesznek, amikor később használja a varázslót az eljárás során.

2. A Művelet panelen válassza a **Megnyitás Microsoft Office programban** gombot, majd az **Exportálás Excel programba** rész alatt válassza a **Beosztások** lehetőséget. Vagy pedig nyomja meg a Ctrl+T billentyűkombinációt.

    ![A Beosztások listaoldal exportálása az Excel programba](media/org-admin.png)

3. Mentse el az exportált Excel-fájlt.

    ![Exportálás Excel-fájlba párbeszédablak](media/export-excel.png)

4. A Visio alkalmazásban válassza a **Visio - Új létrehozása** lehetőséget, majd az **Üzleti** sablonkategóriát.

    ![Új diagram](media/new.png)

5. Válassza a **Szervezeti diagram varázsló** lehetőséget, majd a **Létrehozás** elemet.

    ![Szervezeti diagram varázsló párbeszédablak](media/orgchart-wizard.png)

6. Válassza a **Fájlban vagy adatbázisban már tárolt információ** lehetőséget, majd kattintson a **Következő** gombra.

    ![Szervezeti diagram varázsló 1](media/orgchart-wizard7.png)

7. Válasszon egy **szöveget, Org Plus- (\*.txt) vagy Excel-fájlt**, majd kattintson a **Következő** gombra.

    ![Szervezeti diagram varázsló 2](media/orgchart-wizard3.png)

8. Tallózással keresse meg az exportált Excel-fájl, amely tartalmazza a beosztáshierarchiát, és nyomja meg **Következő** gombot.

    ![Szervezeti diagram varázsló 3](media/orgchart-wizard2.png)

9. Állítsa a **Név** mezőt **Beosztás** értékre, a **Közvetlen felettes** mezőt **Felettes beosztás** értékre, majd nyomja meg a **Következő** gombot.

    ![Szervezeti diagram varázsló 4](media/orgchart-wizard1.png)

10. Válassza ki a mezőket, amelyek minden csomóponton jelenjenek meg, és nyomja meg a **Következő** gombot.

    ![Szervezeti diagram varázsló 5](media/orgchart-wizard5.png)

11. Adja hozzá a **Beosztás** oszlopot az **Adatmezők formázása** listához, majd kattintson a **Következő** gombra.

    ![Szervezeti diagram varázsló 6](media/orgchart-wizard6.png)

12. A képek jelenleg nem érhető el. Emiatt a következő oldalon válassza a **Következő** gombot.
13. Válassza a **A varázsló automatikusan bontsa a szervezeti diagramot oldalakra** lehetőséget.

    ![Szervezeti diagram varázsló 7](media/orgchart-wizard4.png)

14. Válassza a **Befejezés** lehetőséget.

    Ha olyan beosztások léteznek, amelyek nem szerepelnek a szerkezetben, a rendszer megkéri, hogy ezeket is szerepeltesse a diagramban.

A Visio alkalmazásban létrehozott diagram minden vezetőt külön munkalapon jelenít meg.

A diagramban való megjelenítésre kiválasztott mezők alapján az egyes csomópontok a megfelelő információt mutatják be, amikor a Visio-fájlt létrehozza.

![Hierarchiadiagram](media/hierarchy.png)

**További lehetőség**

A Talentben lehet, hogy a **Személyek** munkaterületen is meg tudja jeleníteni a hierarchiához kapcsolódó információk egy részét.
