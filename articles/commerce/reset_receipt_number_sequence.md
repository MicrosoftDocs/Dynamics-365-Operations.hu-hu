---
title: Nyugtaszámok visszaállítása
description: Ez a témakör azt mutatja be, hogyan lehet alaphelyzetbe állítani a különböző műveletekhez használt nyugtaszámokat (például a pénzügyi évet vagy naptári évet).
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail, Commerce
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: fc719348f94ff4a1fb7b4ac96f6f617872c9af92
ms.sourcegitcommit: 437170338c49b61bba58f822f8494095ea1308c2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2020
ms.locfileid: "3123946"
---
# <a name="reset-receipt-numbers"></a>Nyugtaszámok visszaállítása 

[!include [banner](includes/banner.md)]


A kiskereskedők az üzletben különböző műveletekhez, például készpénz- és szállítási tranzakciókat, visszáru-tranzakciókat, vevői rendeléseket, árajánlatokat és kifizetéseket generálnak. Bár a kiskereskedők saját nyugtaformátumokat határoznak meg, egyes országokban vagy régiókban vannak olyan rendeletek, amelyek megszabják a nyugta formátumának korlátozását. Például ezek a rendeletek korlátozhatják a nyugtán szereplő karakterek számát, megkövetelhetik az egymást követő nyugták számát, korlátozhatnak néhány speciális karaktert, illetve előírhatják, hogy a nyugta számait az év elejére kell állítani. A Microsoft Dynamics 365 Commerce nagyon rugalmasan kezeli a nyugtaszámok feldolgozását, így segít a kiskereskedőknek megfelelni a szabályozási követelményeknek. Ez a témakör azt mutatja be, hogyan kell használni a funkciókat a nyugtaszámok visszaállításához.

A Commerce-ben a nyugta formátuma alfanumerikus lehet. A statikus tartalmat és a dinamikus tartalmat egyszerre is be lehet állítani. A statikus tartalom alfabetikus karaktereket, számokat és speciális karaktereket tartalmaz. A dinamikus tartalom egy vagy több olyan karaktert tartalmaz, amely olyan információkat jelenít meg, mint például az üzlet száma, a terminál száma, a dátum, a hónap, az év és a számsorozat, amely automatikusan megnő. A formátumokat a funkció profiljának **Nyugtaszámozási** szakasza határozza meg. A következő táblázat leírja a dinamikus tartalmat megjelenítő karaktereket.

| Karakterek | Leírás |
|------------|-------------|
| V          | Az **S** karakter az üzlet számához használatos. Ha például egy üzlet HOUSTON1 számmal van ellátva, akkor az **SSS** formátum „ON1” kódként jelenik meg a nyugtán. Az **SSSSS** formátuma „STON1”-ként jelenik meg a nyugtán. |
| T          | A **T** karakter a terminál számához használatos. Ha például egy terminál 0001 számmal van ellátva, akkor a **TTTT** formátum „0001” kódként jelenik meg a nyugtán. |
| K          | A **C** karakter munkatárs azonosítójához használatos. Ha például a munkatárs azonosítója 000160, a **CCCC** formátum „0160”-ként jelenik meg a nyugtán. |
| ddd        | A **ddd** karakter megfelel az év napjának, 1-től 366-ig. Például január 15-én a **ddd** formátum „015”-ként jelenik meg a nyugtán. |
| MM         | Az **MM** karakterek a hónapokat jelölik két számjeggyel. Például januárban az **MM** formátum „01”-ként jelenik meg a nyugtán. |
| DD         | A **DD** karakterek a hónapok napjait jelölik két számjeggyel. Például január 15-én a **DD** formátum „15”-ként jelenik meg a nyugtán. |
| YY         | Az **YY** karakterek az évet jelölik két számjeggyel. Például 2020 bármelyik hónapjánál az **YY** formátum „20”-ként jelenik meg a nyugtán. |
| \#         | A kettőskereszt (**\#**) egymást követő számoknál használatos. Például a **####** „0001”, „0002”, „0003” stb. számsort jelöl a nyugtán.  |

A nyugta sorszámozását egy adott dátumra állíthatja vissza. Ezt követően a rendszer az első olyan tranzakciónál, amely a kiválasztott visszaállítási dátumon 12:00 után jelentkezik, a nyugta számsorozatát 1 értékre állítja vissza. Megadhatja azt is, hogy a visszaállítás csak egy alkalommal, vagy minden évben újra megtörténjen-e. Ha meg van adva az éves ismétlődés, a visszaállítás automatikusan ismétlődik, amíg a kiskereskedő úgy nem dönt, hogy leállítja. 

Ha be szeretné kapcsolni a visszaállítást, hajtsa végre az alábbi lépéseket.

1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**.
1. A **Nyugtaszámozás** gyorslapon válassza **Visszaállítási szám visszaállítási dátuma** lehetőséget.
1. Válassza ki a legördülő párbeszédpanelen a **Dátum visszaállítása** mezőben azt a jövőbeli dátumot, amikor a visszaállításnak meg kell történnie.
1. A **Nyugtatípus visszaállítása** mezőben válassza ki az **Egy alkalommal** vagy **Évente** lehetőséget.
1. Válassza ki az **OK** lehetőséget.

![Nyugta alaphelyzetbe állítási dátumának kiválasztása](media/Enable_receipt_reset.png "Nyugta alaphelyzetbe állítási dátumának kiválasztása")

Miután kiválasztott egy dátumot, megjelenik a **Következő nyugta-visszaállítási dátum** oszlopban. A visszaállítási dátum az összes nyugtatranzakció-típusra érvényes. Ennélfogva a nyugta számsorozata alaphelyzetbe kerül az összes nyugtatípus esetében.

Ha a visszaállítás dátuma esedékes, akkor a program visszaállítja a nyugta számát az egyes típusok első tranzakciójára. Ezenkívül a funkcióprofilban a **Következő nyugta-visszaállítási dátum** oszlopból az **Aktuális nyugta-visszaállítási dátum** oszlopba kerül a visszaállítás dátuma. Ez a változtatás azt jelzi, hogy ha a jegyzéket nem használja fel a rendszer a visszaállítási dátumon, akkor a program a jegyzék a következő *felhasználása alkalmával* visszaállítja a nyugta számát. Például 2019. december 3-án Ön a **2020. január 1-jét** adja megvisszaállítási dátumnak. Január 1-jén, amikor a jegyzékek elvégzik az első tranzakciót, a rendszer visszaállítja a nyugta számát. Egy jegyzéket azonban egyáltalán nem használ decemberben és januárban, de később, februárban elkezdi használni. Ebben az esetben, mivel a visszaállítási művelet be van állítva, az adott jegyzékhez tartozó nyugta értékét akkor állítja vissza a program, ha a jegyzék elvégzi az első tranzakcióját februárban.

A jövőbeli visszaállítási dátumok törléséhez használja a **Visszaállítási dátum törlése** funkciót. Ha azonban a visszaállítás dátuma korábban történt meg, akkor nem vonható vissza. Ezért a visszaállítás még mindig megtörténik minden olyan jegyzék esetében, amelyeknél még nem történt meg a visszaállítás.

> [!NOTE]
> A kiválasztott Alapbeállítási dátumtól és a nyugta formátumtól függően lehet, hogy ismétlődő nyugta-szám van. Annak ellenére, hogy a pénztárrendszer képes kezelni ezeket a helyzeteket, növeli a visszáru feldolgozásához szükséges időt, mivel az értékesítési munkatársaknak választaniuk kell a duplikált nyugták között. Az adattisztítással kapcsolatos egyéb komplikációk akkor is előfordulhatnak, ha az ismétlődő nyugták nem tervezett következmények voltak. Ezért azt ajánljuk, hogy dinamikus dátumú karaktereket (például **ddd**, **MM**, **DD** és **YY**) használjon, hogy megakadályozza az ismétlődő nyugtaszámok visszaállítását.
