---
title: Ajánlatokon és ajánlatkérésen alapuló tervek
description: Ez a témakör azt ismerteti, hogyan lehet beállítani olyan alaptervezést, amely a tervezett rendelések generálása során figyelembe veszi az árajánlatokat és az ajánlatkéréseket.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690160"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Terv árajánlatok és ajánlatkérések alapján

[!include [banner](../../includes/banner.md)]

Az ajánlatkérések (ajánlatkérések) a lehetséges vagy akár várható jövőbeli rendeléseket képviselik. Ezért érdemes ezeket az alaptervezés során figyelembe venni, hogy a meglévő ajánlatkérések alapján tervezni lehet további készleteket, és hogy az egyes ajánlatok milyen valószínűséggel válnak tényleges rendeléssé. Ez a témakör azt ismerteti, hogyan lehet beállítani olyan alaptervezést, amely a tervezett rendelések generálása során figyelembe veszi az árajánlatokat és az ajánlatkéréseket.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Az alaptervezés beállítása az értékesítési ajánlatok és/vagy ajánlatkérések figyelembe vennie

A következő eljárás szerint állíthatja be, hogy az alaptervezés figyelembe vegye az értékesítési árajánlatokat és/vagy ajánlatkéréseket.

1. Ugrás az alaptervezés **beállítási \> terveihez \>\>**.
1. Válasszon ki egy meglévő tervet a listaablakban, **vagy** az Új gombra kattintva hozzon létre egy újat a munkaablakban.
1. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Értékesítési ajánlatokkal –** a jelenlegi terv *futtatásakor ezt a beállítást Igen* beállítással figyelembe lehet venni az értékesítési ajánlatokkal. Állítsa Nem *beállításra*, hogy figyelmen kívül hagyja őket.
    - **Valószínűség %** – állítsa be azt a minimális megbízhatósági szintet, amely ahhoz szükséges, hogy egy ajánlat résztvessen az alaptervezésben. Az alaptervezés számítása tartalmazni fogja az összes olyan lehetőségből létrehozott árajánlatot, amelyeknél ez a valószínűségi százalék vagy annál magasabb. Ha minden ajánlatot belevesz, beleértve azokat az árajánlatokat is, amelyekhez nincs valószínűség hozzárendelve, vagy amelyekhez nincs lehetőség társítva, *állítsa ezt a mezőt nullára*. Az árajánlatok valószínűségére vonatkozó további tudnivalókat lásd a következő szakaszban.
    - **Ajánlatkérések bekérése** – a jelenlegi *terv futtatásakor ezt a beállítást Igen* beállítással az ajánlatkérések figyelembe vehetőre állíthatja. Állítsa Nem *beállításra*, hogy figyelmen kívül hagyja őket. Ha az ajánlatkérések figyelembe vételét választja, a rendszer létrehozza a számukra a tervezett beszerzési rendeléseket, de az ajánlatkérés megoldásáig nem határozza meg a szállítót. Az ajánlatkéréshez létrehozott tervezett beszerzési rendelések hatással lehetnek az egyéb tervezett rendelések mennyiségére.

1. Folytassa az alapterv beállítását a szokásos módon.

## <a name="assign-and-view-probabilities-for-quotations"></a>Az árajánlatok valószínűségének hozzárendelése és megtekintése

Az előző szakaszban említettek szerint az alapterv csak olyan árajánlatokat fog figyelembe venni, amelyek megfelelnek vagy meghaladják a tervhez meghatározott valószínűségi küszöbértéket (amennyiben meg van adva küszöbérték). A valószínűség azonban nem minden ajánlathoz van közvetlen beállítva. Ehelyett az ajánlat előállításához használt lehetőségtől öröklődik. Ennek megfelelően a közvetlenül az Összes ajánlat lapon létrehozott ajánlatokhoz nem lesz hozzárendelve valószínűség vagy a hozzájuk társított lehetőség, és az alaptervezés nem fogja figyelembe venni őket (**hacsak a Valószínűség %** **mező nincs nullára állítva** *·*).\[\] Ahhoz, hogy hozzárendelhető legyen a valószínűség, az ajánlatot egy lehetőségből kell generálni.

### <a name="create-a-quotation-from-an-opportunity"></a>Ajánlat létrehozása lehetőségből

A következő eljárással valószínűségt rendelhet egy lehetőséghez, majd árajánlatot hozhat létre az adott lehetőségből.

1. Ugrás az Értékesítési **és marketing kapcsolatok \> minden \> lehetőséghez \>**
1. Válasszon ki egy meglévő lehetőséget, vagy **az** Új gombra kattintva hozzon létre egy újat a munkaablakban.
1. Töltse ki a lehetőség lapját, és azonosítsa a lehetőséget. Győződjön meg róla, hogy **a Valószínűség** mezőt egy megfelelő értékre állítsa. Csak azok az alaptervek, amelyek ennek az értéknek a valószínűségét keresik, csak az ebből a lehetőségből létrehozott árajánlatokat veszi figyelembe.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A munkaablak Lehetőség lapján, **·** **·** **az** Új csoportban a létrehozni kívánt ajánlat típusától függően válassza ki az Értékesítési ajánlatot vagy a Projektajánlatot.**·**
1. Az Ajánlat létrehozása **párbeszédpanelen** állítsa be a mezőket a kívánt ként, majd válassza az **OK gombra.**
1. Létrejön és megnyílik egy új ajánlat. A Sorok **gyorspultban** használja az eszköztárat, ha az ajánlat tartalmának meghatározásához szükség van értékesítési sorok vagy projektsorok hozzáadására.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget. Ezután zárja be az ajánlatot.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Az ajánlathoz rendelt valószínűség megtekintése

Az ajánlatokhoz rendelt valószínűséget úgy lehet megtekinteni, ha megnyitja az ajánlat létrehozásához használt lehetőséget, amint azt az alábbi eljárás ismerteti.

1. Ugrás az Értékesítési **és marketingajánlatok \> – \> Minden ajánlat.**
1. Ha a **Lehetőségazonosító** oszlop nem látható (az alapértelmezett telepítésben rejtett), a következő lépések szerint mutatja meg. (Másik lehetőségként a **A lehetőségazonosító** oszlop elérhető, hozzon létre egy mentett [nézetet](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json), amely tartalmazza azt.)

    1. Jelölje ki és tartsa lenyomva a rácsot (vagy kattintson rá a jobb gombbal), majd válassza az Oszlopok beszúrása **lehetőséget**.
    1. Az Oszlopok **beszúrása** párbeszédpanelen keresse meg azt a sort, **·** *ahol* a mező Lehetőség beállításra van állítva, **és jelölje be annak** a sornak a Kiválasztása jelölőnégyzetét.
    1. A **Kijelölt oszlopnak** az Összes ajánlat **laphoz való hozzáadásához válassza a** Frissítés lehetőséget.

1. A rácsban keresse meg a megfelelő ajánlat sorát. Ezután a Lehetőség azonosítója **oszlopban** válassza ki a sor értékét.

    > [!NOTE]
    > Ha projektajánlatot keres, lehet, **hogy** ki kell választania az Ajánlattípus oszlopfejlécet, és ki kell szűrni a szűrőjét. Az alapértelmezett telepítésben ez a szűrő úgy van beállítva, hogy csak az értékesítési ajánlatok jelennek meg.

1. A kapcsolódó lehetőség meg van nyitva. Most megtekintheti és szerkesztheti a **Valószínűség értékét**.
