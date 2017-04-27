---
title: "Hitelkártya-beállítás, engedélyezés és rögzítés"
description: "Ez a cikk a Microsoft Dynamics AX rendszer hitelkártya-engedélyezéséről nyújt tájékoztatást. A fizetési szolgáltatás beállításának módjáról, az értékesítési rendeléshez történő hitelkártya hozzáadásáról és az engedélyezés érvénytelenítéséről nyújt tájékoztatást."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40d950b04511e85d05106c274d1580a3daac7af7
ms.lasthandoff: 03/31/2017


---

# <a name="credit-card-setup-authorization-and-capture"></a>Hitelkártya-beállítás, engedélyezés és rögzítés

[!include[banner](../includes/banner.md)]


Ez a cikk a Microsoft Dynamics AX rendszer hitelkártya-engedélyezéséről nyújt tájékoztatást. A fizetési szolgáltatás beállításának módjáról, az értékesítési rendeléshez történő hitelkártya hozzáadásáról és az engedélyezés érvénytelenítéséről nyújt tájékoztatást.

<a name="setting-up-the-credit-card-payment-service"></a>A hitelkártyás fizetési szolgáltatás beállítása
------------------------------------------

Hitelkártyák használatához állítson be és aktiváljon egy fizetési szolgáltatást a Fizetési szolgáltatások lapon. A fizetési szolgáltatás a jogi személy és a vevő hitelkártya-terheléseit feldolgozó bank közötti kapcsolatként működik. Olyan hitelkártya-szolgáltatóval kell együttműködnie, amely szerepel a Fizetési csatlakoztató mezőben, és ennél a szolgáltatónál kell egy számlát létrehoznia. Ezután további opciókat kell majd beállítania a Fizetési szolgáltatások oldalon, hitelkártyatípusokat kell beállítania az American Express, Discover, MasterCard és Discover számára a hitelkártya-típusok oldalon, és a szolgáltatót alapértelmezett szolgáltatóként kell beállítania. A beállítás befejezéséhez ezeket a lépéseket is be kell tartania:
-   A Kinnlevőségek paraméteroldalon adja meg a paramétereket a hitelkártya-engedélyezések használatához.
-   A Fizetési feltételek oldalon lehet beállítani a hitelkártyák fizetési feltételeit. A Fizetés típusa mezőben válassza ki a Hitelkártyát.
-   A Vásárlói hitelkártyák oldalon adja meg a vevők számára a hitelkártya-adatokat.

## <a name="adding-a-new-credit-card"></a>Új hitelkártya hozzáadása
Új hitelkártya-rekordokat a Vevők lapon a Vevő, Beállítás, Hitelkártya használatával hozhat létre. Hitelkártya-rekordokat értékesítési rendelések beírásakor is létrehozhat az Értékesítési rendelés oldalon, a Kezelés, Vevő, Hitelkártya, Jegyzék segítségével.
Hitelkártya hozzáadása egy értékesítési rendeléshez
-------------------------------------

Hitelkártyát hozzáadhat egy értékesítési rendeléshez egy hitelkártya kiválasztásával a hitelkártya-keresőben az Ár és engedmények gyorslapon, az Értékesítési rendelés lapon. Az engedélyezési folyamat elindításához a Műveleti ablakban a Kezelés fülön válassza ki a Hitelkártyát és az Engedélyezést.
Hitelkártya engedélyezése
-------------------------

Amikor megtörténik a hitelkártya engedélyezése, a kártyaszám és a kártyabirtokos nevének ellenőrzése megy végbe, valamint megerősítést nyer a rendelkezésre álló hitelegyenleg. Másik lehetőségként a kártyaellenőrző kód és a kártyatulajdonos címének ellenőrzése megy végbe. Ezt követően a vevő rendelkezésre álló hitelegyenlege a számla összegével csökken. A fizetési szolgáltatás információt küld arról, hogy a hitelkártyát elfogadja-e, vagy elutasítja. Az értékesítési rendelés számlázásakor a hitelkártyán végbemegy a számlaösszeg terhelése (rögzítése).

### <a name="card-verification-value"></a>Kártyaellenőrző kód

Igényelheti a kártyaellenőrző kódot, amelyre néha a kártya biztonsági kódjaként utalnak. Az American Express esetében ez egy négyjegyű érték. A Discover, MasterCard és Visa esetében ez egy háromjegyű érték.

### <a name="address-verification"></a>Cím ellenőrzése

A kifizetési szolgáltatóhoz mindig beérkezik a címadatok ellenőrzése. Megadhatja, hogy mennyi információra szükség egy tranzakció elfogadásához. Ügyeljen arra, hogy egyeztesse a szolgáltatóval, hogy elfogadja-e ezt az információt. Az alábbiakban láthatók a címellenőrzés lehetőségei:
-   **Tranzakció mindenkori elfogadása** – Elfogadja a tranzakciót, függetlenül a címellenőrzés eredményétől.
-   **Számlatulajdonos** – A tranzakcióból a kártyatulajdonos nevének összehasonlítása a hitelkártyát feldolgozó vállalat adataival.
-   **Számlázási cím** – A tranzakcióból a kártyatulajdonos nevének és számlázási címének összehasonlítása a hitelkártyát feldolgozó vállalat adataival.
-   **Számlázási cím irányítószáma** – A tranzakcióból a kártyatulajdonos nevének, számlázási címének és számlázási címe irányítószámának összehasonlítása a hitelkártyát feldolgozó vállalat adataival.

## <a name="data-support"></a>Adattámogatás
Minden egyes támogatott hitelkártyatípushoz be lehet állítani az adattámogatás szintjét. A szint szabályozza, hogy mennyi, a tranzakcióval kapcsolatos információ kerül át a fizetési szolgáltatáshoz. Ügyeljen arra, hogy egyeztesse a szolgáltatóval, hogy meg tudja-e adni ezt az információt. Az adattámogatás szintjének lehetőségei a következők:
-   **1. szint** – A tranzakció dátumnak, összegének és leírásának átadása.
-   **2. szint** – Az összes 1. szintű információ, valamint a szállítási és kereskedői címek, és az adóval kapcsolatos adatok átadása.
-   **3. szint** – Az összes 2. szintű információ, valamint a rendelési sor információinak átadása.

## <a name="partial-payments"></a>Részfizetések
Ha egy rendelés egy részét szállítja ki, a rendelés részleges összege kerül rögzítésre, és az engedélyezés, amely a teljes rendelés összegére vonatkozott, lezárul. A fennmaradó összeghez a még nem szállított rendelésről egy új engedély lesz leadva.

## <a name="voiding-an-authorization"></a>Engedélyezés érvénytelenítése 
A hitelkártya-engedélyezés érvénytelenítéséhez módosíthatja a fizetési módot egy másik módra, amelyhez nem tartozik Hitelkártya-típus.






