---
title: Vegyes valóság útmutató a termelésben dolgozók számára
description: Ez a témakör azt mutatja be, hogyan lehet integrálni a Microsoft Dynamics 365 Supply Chain Management modulját a Dynamics 365 Guides alkalmazással.
author: cabeln
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 727a3bc50ea55259c7260a9d060dac59473ee3c1
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645144"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Vegyes valóság útmutató a termelésben dolgozók számára

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A termelésben dolgozók számára hasznos, ha a megfelelő időben rendelkezésre állnak a munkájukra vonatkozó megfelelő utasítások. Az *Utasítások* számos területen használhatók, ilyenek többek között: összeállítás, szerviz, műveletek, minősítés és munkavédelem. Ezeknél az alapvető vállalati funkcióknál a folyamatos betanító utasítások segítséget jelentenek a dolgozóknak a jobb teljesítményhez és a pontosabb munkavégzéshez.

## <a name="introduction"></a>Bevezetés

Különféle módokon lehet utasításokat megadni. A [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) alkalmazást használó, azonnal használatba vehető hatékony rendszer.

A Dynamics 365 Guides a gyakorlati oktatással nyújt a segítséget a vállalat dolgozóinak. Szabványosított folyamatok adhatók meg, olyan részletes utasításokkal, amelyek az alkalmazottakat a szükséges eszközökhöz és alkatrészekhez irányítják, és bemutatják, hogyan kell ezeket az eszközöket valódi munkakörülmények között használni.

Útmutatók csatolhatók a termelés-ellenőrzés különböző területeihez, például a következőkhöz:

- [Erőforrások](#resources)
- [Erőforráscsoportok](#resource-groups)
- [Kiadott termékek](#released-products)
- [Receptúrák](#formulas)
- [Receptúraverziók](#formula-versions)
- [Anyagjegyzékek (AJ-k)](#bom)
- [Anyagjegyzék-verziók](#bom-versions)
- [Útvonalak](#routes)
- [Útvonalverziók](#route-versions)
- [Útvonalműveleti kapcsolatok](#route-operation-relations)

> [!NOTE]
> Az Eszközkezelőhöz is csatolható útmutató. További információ: [Dynamics 365 Supply Chain Management (Eszközkezelés) integrálása a Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md) alkalmazással.

Amikor egy első vonalbeli dolgozó a Supply Chain Managementen keresztül kiválaszt egy üzemi feladatot, [a releváns útmutató](#logic) megjelenik a feladatkártyán. Ha a dolgozó kiválaszt egy adott utasítást, annak QR-kódja megjelenik a képernyőn. A dolgozó ezt követően a HoloLens használatával beolvassa a QR-kódot, amely behívja az útmutatókat, és megjelennek a szükséges utasítások.

A következő alszakaszok néhány olyan esetet írnak le, amikor különféle iparágakban tevékenykedő, az útmutatókat gyártási utasításokra használó vállalatok a legjobb teljesítményt érik el.

### <a name="assembly"></a>Szerelvény

![Útmutató használata összeszerelési feladatoknál](media/instruction-guides-hero-assembly.png "Útmutató használata szervizfeladatoknál")

Az összeszerelési műveletekre vonatkozó utasítások megmutatják a dolgozóknak a szükséges szerszámokat és alkatrészeket, valamint használatukat valódi munkakörülmények között.

A termelésvezető útmutatókat hozhat létre és rendelhet hozzá, például [termelési útvonalakhoz](routes-operations.md), [műveleti kapcsolatokhoz](routes-operations.md#operation-relations), vagy [anyagjegyzékekhez](bill-of-material-bom.md). A dolgozók számára így rendelkezésre állnak az adott tevékenységre vonatkozó utasítások.

### <a name="service"></a>Szerviz

![Útmutató használata szervizfeladatoknál](media/instruction-guides-hero-service.png "Útmutató használata szervizfeladatoknál")

A technikusokat irányított utasításokkal látja el a munkahelyükön, hogy feleslegessé váljanak további látogatások.

A szervizvezetők hozzárendelhetnek útmutatót például adott [termékekhez](../../commerce/product.md), amelyek minőség-ellenőrzésen esnek át.

### <a name="quality"></a>Minőség

![Útmutató használata minőségbiztosítási feladatoknál](media/instruction-guides-hero-quality.png "Útmutató használata minőségbiztosítási feladatoknál")

Új folyamatok bevezetése és a következetesség növelése az alkalmazottak tudásának megismételhető eszközzé alakításával.

A minőségbiztosítási vezetők hozzárendelhetnek útmutatót például [termékekhez](../../commerce/product.md), amelyek minőség-ellenőrzésen esnek át.

### <a name="certifications"></a>Tanúsítványok

![Útmutató használata tanúsítással kapcsolatos feladatoknál](media/instruction-guides-hero-certification.png "Útmutató használata tanúsítással kapcsolatos feladatoknál")

Fontos, hogy az alkalmazottak képesek legyenek magas elvárások teljesítésére, és gyorsan észleljék, kinek és hol van szüksége segítségre.

### <a name="safety"></a>Biztonság

![Útmutató használata munkavédelemmel kapcsolatos feladatoknál](media/instruction-guides-hero-safety.png "Útmutató használata munkavédelemmel kapcsolatos feladatoknál")

Utasításokat ad, amelyek virtuálisan áttekintik a veszélyes eljárásokat, mielőtt azokat fizikai környezetben alkalmaznák. A vegyes valóság megközelítésével a dolgozók virtuálisan gyakorolhatják a veszélyes eljárásokat.

A termelésvezetők külön kezelési utasításokat adhatnak meg a veszélyes anyagok kezelésére, illetve a kényes kezelési eljárásokra, utasítások hozzárendelésével a [termékelemekhez](../../commerce/product.md), [útvonalakhoz](routes-operations.md) és [műveletekhez](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Első lépések az utasítások és az útmutatók használatához

Az utasítások engedélyezéséhez a termelési folyamatokban a Supply Chain Management biztosítja a kulcsrakész integrációt a Dynamics 365 Guides alkalmazással. A gyártási eszközök és a munka vegyes valóságra vonatkozó utasításainak összeállításához, karbantartásához és hozzárendeléséhez engedélyezett és telepített Guides-alkalmazáspéldány szükséges.

### <a name="prerequisites"></a>Előfeltételek

A funkció használatához a rendszernek tartalmaznia kell a következőket:

- Dynamics 365 Supply Chain Management 10.0.15 vagy újabb verziója
- [Kettős írás](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) funkció a Supply Chain Management alkalmazásokhoz.
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 400.0.1.48 vagy újabb verziója

### <a name="turn-on-the-feature"></a>A funkció bekapcsolása

A szolgáltatás elérhetővé tételéhez a rendszerén engedélyeznie kell a konfigurációs kulcsokat. Ezt csak egyszer kell elvégeznie. Ehhez a rendszergazdának a következőket kell tennie:

1. Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
1. Bontsa ki a **Vegyes valóság** szakaszt, és jelölje be a **Vegyes valóság útmutató** jelölőnégyzetet.
1. Bontsa ki a **Termelésirányítás** szakaszt, és jelölje be a **Termelési utasítások** jelölőnégyzetet.
1. Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Az Útmutatók üzemben használt felületének konfigurálása

Az Útmutatók üzemben használt felületének konfigurálásához folytassa itt: **Mixed Reality \> Dynamics 365 Guides \> Útmutatók integrálásának konfigurálása**.

![Útmutató integrálásának konfigurálása a gyártáshoz](media/instruction-guides-configure-integration.png "Útmutató integrálásának konfigurálása a gyártáshoz")

Állítsa be a következő mezőket:

- **Microsoft Dataverse URL-cím** – A Microsoft Dataverse környezet URL-címének megadása, ahol létrehozza a Guides elemet. A formátum „contoso.crm4.dynamics.com”, ahol az URL-cím első fele általában a szervezet neve (pl. „contoso”), a második rész a környezet adatrégiójára vonatkozik (pl. „crm4.”), az utolsó rész pedig a tartomány (pl. „dynamics.com”). A helyes URL-cím megkeresésének egyik módja a [home.dynamics.com](https://home.dynamics.com/) megnyitása, majd a Guides alkalmazás megnyitása. Amikor a Guides megnyílik, megtekintheti az URL-címet a böngésző címsorában (csak az alap URL-cím, amely az előző példához hasonlít). Ez az érték használatos az útmutatók címeinek összeállításához, és beleíródik a QR-kódba."
- **QR-kód mérete** – Beállítja a megjelenített QR-kód méretét. Olyan méret választása ajánlott, amely kitölti a képernyő nagy részét, de nem nagyobb. Általában a *15* a megfelelő méret.
- **QR-kód hibajavító szintje** – Beállítja a QR-kód részletességét. A magasabb részletességgel növelheti a kód megbízhatóságát, de a **QR-kódnak** elég nagynak kell lennie ahhoz, hogy támogassa a kiválasztott korrekciós szinthez szükséges részletességi szintet.

> [!TIP]
> - A túl nagy méretű QR-kódok megjelenítése egy kicsit hosszabb időt igényel, majd le kell kicsinyíteni, hogy ráférjen a képernyőre. Ezek miatt nem előnyös.
> - A túl kis méretű QR-kód csökkentheti a HoloLens kódolvasó képességét bizonyos környezetekben.
> - Ajánlott a HoloLens-felhasználók által használt összes, QR-kódot megjelenítő eszköz beállításainak előzetes tesztelése. Válasszon olyan beállításokat, amelyek üzemi környezetben is kielégítő olvashatóságot biztosítanak.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Az összes útmutató-hozzárendelés áttekintése

Az **Összes útmutató** lapon megtekintheti a szervezet összes elérhető útmutatóját, valamint azok összes hozzárendelését a termelési folyamatokhoz és erőforrásokhoz. Megnyitásához válassza a **Vegyes valóság \> Útmutató \> Összes útmutató** elemeket. A felső lista az összes rendelkezésre álló útmutatót jeleníti meg; a lista az itt található mezővel szűrhető. A lenti lista az összes útmutató-hozzárendelést jeleníti meg, és egy eszköztárat tartalmaz a kezeléshez.

![Útmutatók kezelése](media/instruction-guides-allguides.png "Útmutatók kezelése")

A következő szakaszok az útmutatókhoz társítható objektumok típusait mutatják be. Minden hozzárendelt útmutató olyan utasításokat tartalmaz, amelyek automatikusan a megfelelő gyártási feladatokhoz vannak csatolva, és amelyek elérhetők az üzemben.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Útmutató társítása erőforrással

Adjon hozzá útmutatót egy [erőforráshoz](operations-resources.md), megfelelő termelési feladatokkal kapcsolatos útmutató létrehozásához.

### <a name="typical-scenario-using-resources"></a>Jellemző példa erőforrások használatára

Például csatolhat egy általános gépbiztonsági vagy kezelési utasításokat tartalmazó útmutatót az adott típusú gép egy erőforrásához. Ezután az útmutató elérhető lesz minden feladathoz, amelyet a gépen végeznek.

### <a name="add-a-guide-to-a-resource"></a>Útmutató hozzáadása erőforráshoz

Útmutató hozzáadása egy erőforráshoz:

1. Válassza a **Gyártásvezérlés \> Beállítás \> Erőforrások \> Erőforrások** menüpontot.
1. A lista ablaktáblán válassza ki azt az erőforrást, amelyhez útmutatót szeretne rendelni.
1. Bontsa ki a **Társított útmutatók** gyorslapot.
1. Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból. A program új sort ad hozzá a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót. Ha számos útmutatója van, akkor szűrheti a listát, hogy megtalálja azt, amit keres.
    ![Útmutatók kezelése](media/instruction-guides-allguides.png "Útmutatók kezelése")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Útmutató társítása erőforráscsoporttal

Hozzáadhat útmutatót [erőforráscsoportokhoz](tasks/define-discrete-manufacturing-resource-group.md), ha gépcsoportok, gyártósorok vagy munkacellák kezelésére használja őket.

### <a name="typical-scenarios-using-resource-groups"></a>Jellemző példa erőforráscsoportok használata esetén

**1. példa:** Meghatározott egy erőforráscsoportot több azonos típusú géphez. Ahelyett, hogy minden releváns erőforráshoz hozzárendelné a géptípus megfelelő kezelési útmutatóját, az útmutatót hozzárendelheti a géptípus erőforráscsoportjához.

**2. példa:** Meghatározott egy erőforráscsoportot egy különféle gépeket tartalmazó munkacella számára, és van egy útmutatója, amely általános utasításokat tartalmaz a munkacella karbantartására vonatkozóan. Az útmutató a munkacella minden gyártási tevékenységére vonatkozik.

### <a name="add-a-guide-to-a-resource-group"></a>Útmutató hozzáadása erőforráscsoporthoz

Útmutató hozzáadása egy erőforráscsoporthoz:

1. Válassza a **Gyártásvezérlés \> Beállítás \> Erőforrások \> Erőforráscsoportok** menüpontot.
1. A lista ablaktáblán válassza ki azt az erőforráscsoportot, amelyhez útmutatót szeretne rendelni.
1. Bontsa ki a **Társított útmutatók** gyorslapot.
1. Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból. A program új sort ad hozzá a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót. Ha számos útmutatója van, akkor szűrheti a listát, hogy megtalálja azt, amit keres.
    ![Útmutató hozzáadása erőforráscsoporthoz](media/instruction-guides-resourcegroup.png "Útmutató hozzáadása erőforráscsoporthoz")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Útmutató társítása kiadott termékkel

Minden [kiadott termékhez](../pim/tasks/create-released-product-single-company.md) hozzáadhat útmutatót.

### <a name="typical-scenario-using-released-products"></a>Jellemző példa kiadott termékek használata esetén

Termékszintű útmutatók segítenek az üzemben dolgozóknak egy adott kiadott termék vagy egy cikk kezelésével vagy mozgatásával kapcsolatos utasításokkal.

### <a name="add-a-guide-to-a-released-product"></a>Útmutató hozzáadása kiadott termékhez

Útmutató hozzáadása egy kiadott termékhez:

1. Válassza a **Termelési adatok kezelése \> Termékek \> Kiadott termékek** lehetőséget.
1. Nyissa meg a terméket, amelyhez útmutatót szeretne hozzárendelni.
1. A Művelet panelen nyissa meg a **Mérnöki feladatok** lapot, és a **Nézet** csoportban válassza a **Társított útmutatók** elemet.
1. Megjelenik a kiválasztott termék **Társított útmutatók** lapja.
1. A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. 
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása kiadott termékhez](media/instruction-guides-ReleasedProduct-AddGuides.png "Útmutató hozzáadása kiadott termékhez")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Útmutató társítása receptúrával

Minden [receptúrához](bill-of-material-bom.md#formulas-co-products-and-by-products) hozzáadhat útmutatót.

### <a name="typical-scenario-using-formulas"></a>Jellemző példa receptúrák használata esetén
  
A receptúraszintű útmutatók irányított kezelési utasításokat adnak az üzemi dolgozóknak egy formula vagy receptúra vonatkozásában. Útmutató receptúraverzióhoz is hozzárendelhető.

> [!NOTE]
> A gyártási folyamatok szempontjából releváns útmutatást rendelhet receptúra alapján egy útvonalhoz, útvonalváltozathoz vagy útvonalműveleti kapcsolatokhoz.  

> Útmutató jelenleg nem csatolható a receptúra egyes soraihoz.

### <a name="add-a-guide-to-a-formula"></a>Útmutató hozzáadása receptúrához

Útmutató hozzáadása egy receptúrához:

1. Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** menüpontot.
1. Nyissa meg a receptúrát, amelyhez útmutatót szeretne hozzárendelni.
1. Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.
1. Bontsa ki a **Társított útmutatók** gyorslapot.
1. Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból. A program új sort ad hozzá a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása receptúrához](media/instruction-guides-Formula.png "Útmutató hozzáadása receptúrához")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Útmutató társítása receptúraverzióval

Minden [receptúraverzióhoz](bill-of-material-bom.md#bom-and-formula-versions) hozzáadhat útmutatót.

### <a name="typical-scenario-using-formula-versions"></a>Jellemző példa receptúraverziók használata esetén

A receptúrák egyedi verzióihoz csatolt útmutatók az üzemi dolgozóknak olyan utasításokat adnak, amelyek végigvezetnek a receptúra ezen verziójának elkészítésén.

> [!TIP]
> A gyártási folyamatok szempontjából releváns útmutatást rendelhet ezen receptúraverzió alapján egy útvonalhoz, útvonalváltozathoz vagy útvonalműveleti kapcsolatokhoz.  

> [!NOTE]
> Útmutató jelenleg nem csatolható a receptúra egyes soraihoz.

### <a name="add-a-guide-to-a-formula-version"></a>Útmutató hozzáadása receptúraverzióhoz

Útmutató hozzáadása egy receptúraverzióhoz:

1. Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** menüpontot.
1. Nyissa meg azt a receptúrát, amely tartalmazza azt a verziót, amelyhez útmutatót szeretne rendelni.
1. Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.
1. Válassza ki a **Receptúraverziók** gyorslapján azt a verziót, amelyhez útmutatót szeretne társítani.
1. A **Receptúraverziók** eszköztáron válassza a **Társított útmutatók** lehetőséget.
    ![Kiválasztott receptúraverzióhoz társított útmutatók megnyitása](media/instruction-guides-FormulaVersion.png "Kiválasztott receptúraverzióhoz társított útmutatók megnyitása")
1. Megjelenik a receptúraverzió **Társított útmutatók** lapja.
1. A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. 
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása receptúraverzióhoz](media/instruction-guides-FormulaVersionAddGuide.png "Útmutató hozzáadása receptúraverzióhoz")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Útmutató társítása anyagjegyzékhez

Minden [anyagjegyzékhez](bill-of-material-bom.md) (AJ) hozzáadható útmutató.

### <a name="typical-scenario-using-bills-of-materials"></a>Jellemző példa anyagjegyzékek használatára

Az anyagjegyzékhez csatolt útmutatók az üzemi dolgozóknak utasításokat adnak, amelyek elmagyarázzák, hogyan kell az anyagjegyzék anyagait előkészíteni és kezelni. Útmutató anyagjegyzékhez is hozzárendelhető.

> [!NOTE]
> Útmutató jelenleg nem csatolható az anyagjegyzék egyes soraihoz.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Útmutató hozzáadása anyagjegyzékhez

Útmutató hozzáadása egy anyagjegyzékhez:

1. Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Anyagjegyzékek**.
1. Nyissa meg az anyagjegyzéket, amelyhez útmutatót szeretne hozzárendelni.
1. Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.
1. Bontsa ki a **Társított útmutatók** gyorslapot.
1. Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból. A program új sort ad hozzá a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása anyagjegyzékhez](media/instruction-guides-BOM.png "Útmutató hozzáadása anyagjegyzékhez")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Útmutató társítása anyagjegyzék-verzióhoz

Minden [anyagjegyzék-verzióhoz](bill-of-material-bom.md#bom-and-formula-versions) hozzáadható útmutató.

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Jellemző példa anyagjegyzék-verziók használatára

Az egyes anyagjegyzék-verziókhoz csatolt útmutatók az üzemi dolgozóknak utasításokat adnak, amelyek elmagyarázzák, hogyan kell az általános anyagjegyzéktől vagy más verzióktól eltérő anyagjegyzék-verzió anyagait előkészíteni és kezelni.

> [!NOTE]
> Útmutató jelenleg nem csatolható az anyagjegyzék egyes soraihoz.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Útmutató hozzáadása anyagjegyzék-verzióhoz

Útmutató hozzáadása egy anyagjegyzék-verzióhoz:

1. Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Anyagjegyzékek**.
1. Nyissa meg azt az anyagjegyzéket, amely tartalmazza azt a verziót, amelyhez útmutatót szeretne rendelni.
1. Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.
1. Válassza ki az **Anyagjegyzék-verziók** gyorslapján azt a verziót, amelyhez útmutatót szeretne társítani.
1. Az **Anyagjegyzék-verziók** eszköztáron válassza a **Társított útmutatók** lehetőséget.
    ![Kiválasztott anyagjegyzék-verzióhoz társított útmutatók megnyitása](media/instruction-guides-BOMVersion.png "Kiválasztott anyagjegyzék-verzióhoz társított útmutatók megnyitása")
1. Megjelenik az anyagjegyzék-verzió **Társított útmutatók** lapja.
1. A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása anyagjegyzék-verzióhoz](media/instruction-guides-BOMVersionAddGuide.png "Útmutató hozzáadása anyagjegyzék-verzióhoz")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Útmutató társítása útvonallal

Minden [útvonalhoz](routes-operations.md) hozzáadhat útmutatót.

### <a name="typical-scenario-using-routes"></a>Jellemző példa útvonalak használatára

Az útvonalak általában annak meghatározására szolgálnak, hogy egy adott kiadott termék hogyan készül egy anyagjegyzék vagy anyagjegyzék-verzió alapján, és milyen erőforrások vagy erőforráscsoportok szükségesek a gyártáshoz.

Rendeljen hozzá útmutatót egy útvonalhoz, hogy részletes utasításokat adhasson az adott gyártási folyamathoz.

### <a name="add-a-guide-to-a-route"></a>Útmutató hozzáadása útvonalhoz

Útmutató hozzáadása egy útvonalhoz:

1. Válassza a **Gyártásvezérlés \> Minden útvonal** lehetőséget.
1. Nyissa meg az útvonalat, amelyhez útmutatót szeretne hozzárendelni.
1. Bontsa ki a **Társított útmutatók** gyorslapot.
1. Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból. A program új sort ad hozzá a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása útvonalhoz](media/instruction-guides-Route.png "Útmutató hozzáadása útvonalhoz")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Útmutató társítása útvonalverzióval

Minden [útvonalverzióhoz](routes-operations.md#route-versions) hozzáadhat útmutatót.

### <a name="typical-scenario-using-route-versions"></a>Jellemző példa útvonalverziók használatára

Az útvonalverziók általában meglévő útvonalon alapuló termelési folyamatok változatainak meghatározására szolgálnak. Minden útvonalverzióhoz különböző útmutatók rendelhetők hozzá.

### <a name="add-a-guide-to-a-route-version"></a>Útmutató hozzáadása útvonalverzióhoz

Útmutató hozzáadása egy útvonalverzióhoz:

1. Válassza a **Gyártásvezérlés \> Minden útvonal** lehetőséget.
1. Nyissa meg az útvonalat, amelyhez útmutatót szeretne hozzárendelni.
1. Válassza ki a **Verziók** gyorslapján azt a verziót, amelyhez útmutatót szeretne társítani.
1. A **Verziók** eszköztáron válassza a **Társított útmutatók** lehetőséget.
    ![Kiválasztott útvonalverzióhoz társított útmutatók megnyitása](media/instruction-guides-RouteVersion.png "Kiválasztott útvonalverzióhoz társított útmutatók megnyitása")
1. Megjelenik az anyagjegyzék-verzió **Társított útmutatók** lapja.
1. A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.
    ![Útmutató hozzáadása útvonalverzióhoz](media/instruction-guides-RouteVersionAddGuide.png "Útmutató hozzáadása útvonalverzióhoz")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Útmutató társítása útvonalműveleti kapcsolattal

Minden [útvonalműveleti kapcsolathoz](routes-operations.md#operation-relations) hozzáadhat útmutatót.

### <a name="typical-scenario-using-route-operation-relations"></a>Jellemző példa útvonalműveleti kapcsolatok használatára

A műveleti kapcsolatok a legspecifikusabb módja annak, hogy útmutatást adjunk a termékfolyamathoz és a kapcsolódó műveletekhez. Megadhat útmutatást az útvonal minden egyes műveletéhez, és különböző útmutatást adhat meg az útvonalhoz megadott bármilyen típusú objektumkapcsolat-kontextushoz, például adott cikkekhez, konfigurációkhoz és egyebekhez. Meghatározhatja azt is, hogy a művelet mely szakaszaira vonatkozzon az útmutató (például beállítás, várakozás, feldolgozás vagy szállítás).

> [!NOTE]
> Ha egy útvonal több működési relációjához ad meg útmutatót, akkor ezek között az útmutatók között csak a létrehozott munkához tartozó legspecifikusabb kapcsolat útmutatója jelenik meg az üzemben.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Útmutató hozzáadása útvonalműveleti kapcsolathoz

Útmutató hozzáadása egy útvonalműveleti kapcsolathoz:

1. Válassza a **Gyártásvezérlés \> Minden útvonal** lehetőséget.
1. Nyissa meg az útvonalat, amelyhez útmutatót szeretne hozzárendelni.
1. A Művelet panelen nyissa meg az **Útvonal** lapot, és a **Karbantartás** csoportban válassza az **Útvonal részletei** elemet.
1. A kiválasztott útvonalhoz megnyílik az **Útvonal részletei** oldal.
1. A felső rácsban válassza ki azt a műveletet, amelyhez útmutatást szeretne megadni.
1. Az alsó rácsban válasszon egy adott kapcsolatot (vagy az általános **Minden** kapcsolatot).
    ![Válasszon egy műveletet, majd egy kapcsolatot.](media/instruction-guides-RouteOperationRelation.png "Művelet, majd egy kapcsolat kiválasztása")
1. Az alsó rács fölött nyissa meg a **Társított útmutatók** lapot.  ![A Társított útmutatók lap](media/instruction-guides-RouteOperationRelation-AddGuide.png "Társított útmutatók lap")
1. Válassza az alsó rács tetején látható eszköztár **Hozzáadás** elemét, ha új sort szeretne hozzáadni a rácshoz.
1. Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót. A sor többi részén jelölje be a megfelelő jelölőnégyzetet, ha a kiválasztott útmutatónak elérhetőnek kell lennie.

> [!NOTE]
> A műveletek mindegyik szakaszához hozzáadhat egy vagy több útmutatót.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Útmutatók kiválasztása az üzemi végrehajtási felületen

Amikor egy dolgozó megnyit egy feladatlistát az üzemi végrehajtási felületen, a Supply Chain Management megkeresi az adott feladathoz tartozó útmutatókat. Az **Útmutatók** gomb megnyomása kilistázza a megfelelő útmutatókat.

![Útmutatók gomb az üzemi végrehajtási felületen](media/instruction-guides-Shopfloor1.png "Útmutatók gomb az üzemi végrehajtási felületen")

Ezután tegyen fel egy HoloLens-t, majd pillantson a QR-kódra, és aktiválja a megfelelő útmutatót, és elérhetővé válik a megfelelő útmutató.

![QR-kód az útmutató eléréséhez HoloLens](media/instruction-guides-Shopfloor2.png "QR-kód az útmutatók HoloLens segítségével való eléréséhez") segítségével

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Az útmutatók kiválasztásánál alkalmazott logika meghatározása

Útmutatókat hozzáadhat a következő gyártási adatokhoz:

- [Erőforrások](#resources)
- [Erőforráscsoportok](#resource-groups)
- [Kiadott termékek](#released-products)
- [Receptúrák](#formulas)
- [Receptúraverziók](#formula-versions)
- [Anyagjegyzékek (AJ-k)](#bom)
- [Anyagjegyzék-verziók](#bom-versions)
- [Útvonalak](#routes)
- [Útvonalverziók](#route-versions)
- [Útvonalműveleti kapcsolatok](#route-operation-relations)

Amikor a Supply Chain Management létrehozza a termelés számára a feladatokat, akkor ezekből a forrásokból összegyűjti a vonatkozó útmutatókat. Vegye figyelembe a következő fontos szabályokat.

- Ha anyagjegyzék-verziót vagy receptúraverziót csatol útvonalhoz vagy termelési rendeléshez, akkor az ehhez a verzióhoz kapcsolódó útmutatók, valamint a verzió szülő anyagjegyzékéhez vagy receptúrájához csatolt útmutatók is megjelennek a feladaton.
- Ha útvonalverziót csatol termelési rendeléshez, akkor az ehhez a verzióhoz kapcsolódó útmutatók, valamint a verzió szülő útvonalhoz csatolt útmutatói is megjelennek a feladaton.
- Ha több útvonalműveleti kapcsolatot határoz meg, amelyek tartalmazzák az *összes* kapcsolatot, és útmutatókat rendelnek hozzájuk, akkor csak munkához tartozó legspecifikusabb kapcsolat útmutatói jelennek meg a feladaton.  

![Diagram a vonatkozó útmutatók feloldásához](media/instruction-guides-Resolve.png "Diagram a vonatkozó útmutatók feloldásához")
