---
title: beszerzési igénylési munkafolyamat
description: A munkafolyamat folyamata végigviszi a beszerzési igénylést az ellenőrzési folyamaton a kiinduló Tervezet állapottól a végső Jóváhagyva állapotig . A beszerzési igénylés ellenőrzésre való elküldésekor, elindul a munkafolyamat. A beszerzési igénylés jóváhagyása után, a beszerzési igénylés soraiban létrehozható egy beszerzési rendelés, amely elküldésre kerül a szállítónak, a rendelés teljesítése céljából.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a9dceb3f9e71163dcaf8b8763317110ef019844
ms.sourcegitcommit: 9c694772e1484df10afd72ea1a717fda0861627e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2020
ms.locfileid: "3813888"
---
# <a name="purchase-requisition-workflow"></a>beszerzési igénylési munkafolyamat

[!include [banner](../includes/banner.md)]

A munkafolyamat folyamata végigviszi a beszerzési igénylést az ellenőrzési folyamaton a kiinduló Tervezet állapottól a végső Jóváhagyva állapotig . A beszerzési igénylés ellenőrzésre való elküldésekor, elindul a munkafolyamat. A beszerzési igénylés jóváhagyása után, a beszerzési igénylés soraiban létrehozható egy beszerzési rendelés, amely elküldésre kerül a szállítónak, a rendelés teljesítése céljából.

Beszerzési igénylés, ellenőrzésre történő benyújtása előtt konfigurálnia kell a munkafolyamatot. A munkafolyamat egy vagy több ellenőrzési lépést tartalmazhat, bármilyen sorrendben. A munkafolyamat úgy is konfigurálható, hogy az ellenőrzési feladatokat kihagyva, a beszerzési igénylés automatikusan jóváhagyásra kerül. Beállíthatja, hogy a munkafolyamat egyetlen dokumentumként továbbítsa a beszerzési igénylést, vagy hogy az egyes beszerzési igénylési sorok a megfelelő ellenőrök részére kerüljön-e továbbításra. Létrehozhat olyan változatot is, amelyben a beszerzési igénylés egyetlen dokumentumként kerül továbbításra egyes ellenőrök részére, míg mások a kiválasztott beszerzési igénylési sorokat kapják meg.  

Ha a beszerzési igénylési sorok ellenőrzése egyenként történik, az ellenőrzést mindegyik beszerzési igénylési sornál el kell végezni, mielőtt a munkafolyamat a következő lépést megteszi, és mielőtt a beszerzési igénylés teljes ellenőrzési folyamata el nem készül. Amikor lezárult a beszerzési igénylés, annak minden egyes sorára kiterjedő ellenőrzési folyamata, a beszerzési igénylés átfogó állapota a következőre vált: **Jóváhagyva**.  

A munkafolyamatot úgy tudja konfigurálni, hogy az bemutassa a beszerzési igénylési folyamatot a szervezeten belül. Ha a beszerzési igénylés munkafolyamatát állítja be, vegye figyelembe az alábbi kérdéseket:

-   Milyen kiadásokat kell vizsgálni?
-   Milyen kiadások hagyhatók jóvá automatikusan?
-   Kinek kell ellenőriznie és jóváhagynia a kiadási kérelmeket? Milyen szerepkörrel rendelkeznek ezek a felhasználók?
-   Milyen folyamatot kell követni, ha ellenőr nem áll rendelkezésre?

Az alábbi példák a beszerzési igénylések munkafolyamatának két lehetséges konfigurálási módját mutatják be.

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>1. példa: Kezeljen egyetlen dokumentumként egy beszerzési igénylést ellenőrzésre
A következő ábra bemutatja, hogy egy beszerzési igénylés hogyan halad keresztül a munkafolyamat ellenőrzési folyamatán egyetlen dokumentumként kezelve. A beszerzési igénylés sorai nem egyesével kerülnek elküldésre. A következő szerepkörök szerepelnek a munkafolyamatban ebben a példában:

-   **Kérelmező** – A cikket vagy szolgáltatásokat igénylő felhasználó. A kérelmező előkészítheti a beszerzési igénylést, vagy egy másik dolgozó is előkészítheti a beszerzési igénylést a kérelmező nevében. Ez a dolgozó a készítő. A készítő az ellenőrzési folyamat során a beszerzési igénylés kezeléséért felelős. Csak a beszerzési igénylés készítője módosíthatja.

**Megjegyzés:** A dolgozót fel kell ruházni a megfelelő engedélyekkel, hogy valaki más nevében hozhasson létre beszerzési igénylést. Az engedélyeket a **Beszerzési igénylési engedély** lapon tudja beállítani.

-   **Beszerző ügynök** – A felhasználó, aki beszerzési felülvizsgálatot hajt végre, és jóváhagyhatja a dokumentumot.
-   **A kérelmező felettese** – A felhasználó, aki vezetői felülvizsgálatot hajt végre, és jóváhagyhatja a dokumentumot.

![Beszerzési igénylési munkafolyamat ellenőrzésének folyamata](./media/purchreqworkflowoverview_submission.gif)  
Ebben a példában, a beszerzési igénylés munkafolyamata a következő lépéseket tartalmazza:

1.  A készítő benyújt egy beszerzési igénylést ellenőrzésre.
2.  A rendszer értesíti a beszerzési ügynököt. Az értesítés arra utasítja a beszerzési ügynököt, hogy ellenőrizze a beszerzési igénylésben szereplő adatokat. Szükséges információ hiánya esetén, a beszerzési ügynök vagy hozzáadja az információt, vagy visszaküldi a beszerzési igénylést a készítőnek hozzáadásra. Ha megtörtént az összes szükséges információ kitöltése, a beszerzési igénylés továbbléphet az ellenőrzési folyamat következő lépésére.
3.  Az igénylő felettese ellenőrzi a beszerzési igénylést. A beszerzési igénylés eljuthat a kérelmező feletteséhez, ha például a beszerzési igénylés összege meghaladja a kérelmező beszerzési igénylésekre fordítható kiadási keretét. A kérelmező felettese jóváhagyhatja vagy elutasíthatja a beszerzési igénylést, vagy visszajuttathatja a készítőnek módosításra.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>2. példa: Az egyes beszerzési igénylési sorok ellenőrzése
Az alábbi ábra bemutatja, hogyan haladnak keresztül egy munkafolyamaton az egyes beszerzési igénylési sorok. Az egyes sorokra vonatkozó folyamat általában megegyezik a beszerzési igénylések egyetlen dokumentumként való felülvizsgálatának folyamatával. Azonban az egyes soroknak egyenként kell tejesítenie a munkafolyamat folyamatát, mielőtt a beszerzési igénylés munkafolyamatának egésze teljesülne.  

Ebben a példában a dolgozó poszterekre és pólókra ad le igénylést, marketingkampány céljából. A poszterek költsége felosztásra kerül a Marketing részleg és az Értékesítési részleg között. Ha a poszterek vagy a pólók költsége meghaladja a részlegvezetők aláírási korlátját, a beszerzési igénylést a csoport vezetőjének is felül kell vizsgálnia.  

A következő szerepkörök szerepelnek a munkafolyamatban ebben a példában:

-   **Kérelmező** – A cikket vagy szolgáltatásokat igénylő felhasználó. A kérelmező előkészítheti a beszerzési igénylést, vagy egy másik dolgozó is előkészítheti a beszerzési igénylést a kérelmező nevében. Ez a dolgozó a készítő. A készítő az ellenőrzési folyamat során a beszerzési igénylés kezeléséért felelős. Csak a beszerzési igénylés készítője módosíthatja.

**Megjegyzés:** A dolgozót fel kell ruházni a megfelelő engedélyekkel, hogy valaki más nevében hozhasson létre beszerzési igénylést. Az engedélyeket a **Beszerzési igénylési engedély** lapon tudja beállítani.

-   **Beszerző ügynök** – A felhasználó, aki beszerzési felülvizsgálatot hajt végre, és jóváhagyhatja a dokumentumot.
-   **A kérelmező felettese** – A felhasználó, aki vezetői felülvizsgálatot hajt végre, és jóváhagyhatja a dokumentumot.
-   **Részlegvezető** – A felhasználó, aki kiadási felülvizsgálatot hajt végre, és jóváhagyhatja a dokumentumot.
-   **Csoportvezető** – A felhasználó, aki aláírás-felhatalmazási felülvizsgálatot hajt végre, és jóváhagyhatja a dokumentumot.

![Beszerzési igénylési sor munkafolyamat ellenőrzésének folyamata](./media/purchreqlineworkflowoverview.gif)  
Ebben a példában, a beszerzési igénylés sorainak munkafolyamata a következő lépéseket tartalmazza:

1.  A készítő benyújt egy beszerzési igénylést ellenőrzésre. Minden sor ahhoz az ellenőrhöz kerül, aki részére az a munkafolyamat folyamatában konfigurálásra kerül.
2.  A rendszer értesíti a beszerzési ügynököt. Az értesítés arra utasítja a beszerzési ügynököt, hogy ellenőrizze a beszerzési igénylésben és a beszerzési igénylés soraiban szereplő adatokat. A beszerzési igénylés beszerzési ügynök általi megnyitása esetén minden sor látható, de egy vizuális jelölés mutatja a beszerzési ügynöknek az ellenőrzésre elküldött a sorokat. Szükséges információ hiánya esetén, a beszerzési ügynök vagy hozzáadja az információt, vagy visszaküldi a beszerzési igénylési sort a készítőnek hozzáadásra. Ha megtörtént az összes szükséges információ kitöltése, a beszerzési igénylési sor továbbléphet az ellenőrzési folyamat következő lépésére. Az ellenőrzési folyamat során a beszerzési igénylési sorok egymástól függetlenül következhetnek.
3.  Az adott sor kérelmezőjének felettese ellenőrzi és jóváhagyja a beszerzési igénylési sorokat. A jóváhagyás eljuthat a kérelmező feletteséhez, ha például a beszerzési igénylési sorban szereplő összeg meghaladja a kérelmező beszerzési igénylési sorokra fordítható kiadási keretét. A vezető jóváhagyhatja vagy elutasíthatja egy vagy több sorát a beszerzési igénylésnek.
4.  A Marketing részleg vezetője ellenőrzi a beszerzési igénylés sorait mind a poszterekre, mind pedig a pólókra. Az értékesítési részleg vezetője a beszerzési igénylésnek csak a poszterekre vonatkozó sorát ellenőrzi, mivel ez az egyetlen költség, amely az értékesítési részleg költséghelyét terheli majd.
5.  A pólókra vonatkozó beszerzési igénylési sort csak abban az esetben ellenőrzi és hagyja jóvá a csoportvezető, ha ahhoz csoportvezetői jóváhagyás szükséges, például annak okán, hogy a beszerzési igénylési sor összege meghaladja a részlegvezető jóváhagyási határértékét. A csoportvezetőnek nem kell jóváhagynia a poszterekre vonatkozó beszerzési igénylési sort.

> [!NOTE]
> A rendszerpénznemet akkor kell beállítani, ha a beszerzési igénylés fejléc-munkafolyamatához az aláírási korlátokhoz kapcsolódó jóváhagyás szükséges.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Beszerzési igénylési munkafolyamat konfigurációja
Egy beszerzési igénylés ellenőrzésre való eljuttatásához, konfigurálnia kell a beszerzési igénylési munkafolyamatokat. Az Ön által definiált munkafolyamat folyamata szabályozza a cikkeket kérő felhasználó (a kérelmező) és az ellenőrző és jóváhagyó között a munkafolyamatban létrejövő interakciót. A beszerzési igénylési útvonal a munkafolyamat-konfigurációban megadott feltételektől függ. Ezeket a feltételek határozzák meg például, hogy mikor kerül sor a beszerzési igénylés útvonalának meghatározására, illetve mi a címzett felhasználó szerepköre, és melyek a felhasználók által elérhető műveletek.  

Az ebben a témakörben szereplő példák bemutatják, hogy hogyan lehet egy beszerzési igénylést egyedi dokumentumként vagy egyéni beszerzési igénylési sorokként továbbítani a munkafolyamatban. Konfigurálhatja úgy is a beszerzési igénylési munkafolyamatot, hogy láthatóvá váljon a szervezetben definiált beszerzési igénylések belső szabályozási ellenőrzése.  

Az adott munkafolyamatban egy feladathoz hozzárendelt résztvevő vagy ellenőr lehet egy adott felhasználói csoport tagja, egy konkrét biztonsági szerepkörrel rendelkező felhasználó, , egy vezetői hierarchiában a benyújtóhoz társított felhasználó, vagy megnevezett vagy konkrét költségvetési felelősséggel rendelkező felhasználó.

### <a name="purchase-requisition-expenditure-reviewers"></a>Beszerzési igénylés kiadásellenőrei

A kiadás-ellenőri konfigurációk lehetővé teszik a kiadások dinamikus ellenőrzésre küldését azon felhasználó alapján, aki hozzá van rendelve egy projektszerepkörhöz vagy egy pénzügyi dimenzióhoz, ott ahol a kiadás megjelenik. A munkafolyamat a megadott projektszerepkör vagy pénzügyi dimenzió tulajdonosa alapján határozza meg, hogy kinek kell elküldeni a kiadást.  

Definiálhat egy vagy több kiadás-ellenőri konfigurációt, majd a munkafolyamat létrehozásakor választhat egy konfigurációt. A kiadás-ellenőri értékeket beállíthatja a szervezetben található minden jogi személyhez. A kiadás-ellenőri konfigurációk definiálása után hozzárendelhet konfigurációt a munkafolyamat-feladatához.  

Nem kell megjelölnie kiadás-ellenőri konfigurációt. Ehelyett a munkafolyamat definiálásakor megadhat ellenőrként egy meghatározott felhasználót vagy felhasználócsoportot. Ha azonban a szervezet eléggé összetett, kiadásellenőrök segítségével növelheti a jóváhagyási folyamat hatékonyságát. Emellett, ha kiadásellenőröket állít be, akkor nem szükséges frissítenie a munkafolyamat ellenőrök hozzárendelését minden olyan alkalommal, amikor változik egy ellenőr, a feladattal kapcsolatos szerepköre.  

Kiadásellenőröket a **Beszerzési igénylési kiadásellenőrök** oldalon tud beállítani. Hozzon létre kiadás-ellenőri konfigurációt, és adjon meg értéket a szervezetéhez tartozó összes jogi személyhez. A projekthez rendelt igénylések esetén be tudja állítani az igénylések ellenőrzéséért felelős szerepkört: Projektmenedzser, Projektfelügyelő vagy a Projekt értékesítési menedzsere. A kiadások ahhoz a felhasználóhoz lesznek irányítva, aki a meghatározott szerepkörhöz van hozzárendelve. A kiadást elküldheti a pénzügyi dimenzió tulajdonosának is a **Szervezeti felosztások** lapon található megfelelő pénzügyi dimenzió bejelölésével.  

A valamely munkafolyamatban beállított kiadásellenőrök használatához be kell állítania a **Résztvevő típusa** lehetőséget **Kiadások résztvevői** értékre kell állítania az érintett munkafolyamat összetevőre vonatkozó **Hozzárendelési** jellemzők között.

<a name="additional-resources"></a>További erőforrások
--------

[Felhasználási igénylés létrehozása](tasks/create-requisition-consumption.md)

[Üzleti folyamatok munkafolyamatainak meghatározása beszerzési igénylések számára](https://www.microsoft.com/download/details.aspx?id=101821)

[Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok](procurement-sourcing-workflows.md)

[Beszerzési igénylés áttekintése](purchase-requisitions-overview.md)



