---
title: Beszerzési szerződések
description: A cikk beszerzési szerződésekkel kapcsolatos információkról nyújt tájékoztatást. A beszerzési szerződést olyan megállapodás, amely egy szevezetet arra kötelez, hogy több beszerzési rendelés használatával egy adott mennyiségnek vagy összegnek megfelelő terméket vásároljon. Ezen kötelezettségvállalás ellenében a vevő különleges árakat és engedményeket kaphat.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3f90e963341efe854270134988cfc51b5280bf4
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813362"
---
# <a name="purchase-agreements"></a>Beszerzési szerződések

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A cikk beszerzési szerződésekkel kapcsolatos információkról nyújt tájékoztatást. A beszerzési szerződést olyan megállapodás, amely egy szevezetet arra kötelez, hogy több beszerzési rendelés használatával egy adott mennyiségnek vagy összegnek megfelelő terméket vásároljon. Ezen kötelezettségvállalás ellenében a vevő különleges árakat és engedményeket kaphat. 

A beszerzési szerződések vonatkozhatnak egy meghatározott termékmennyiségre, egy termék meghatározott pénznemösszegére vagy egy beszerzési kategória termékeinek meghatározott pénznemösszegére. A beszerzési szerződésben foglalt árak és engedmények felülírják a többi létező kereskedelmi megállapodásokban beállított árak és engedmények mértékét.  

A **Beszerzési szerződések** lapon létrehozhat, alkalmazhat és nyomon követhet beszerzési szerződéseket, amelyek az Ön szervezete és beszállítói között léteznek. Például egy beszerzési szerződés létrehozása után azonnal rendelhet is belőle. Minden beszerzési szerződés érvényességi időtartammal rendelkezik, amelyet az azt létrehozó személy határoz meg. Egy beszerzés kézbesítési dátuma a beszerzési szerződés ezen érvényességi időszakába kell essen.  

Miután létrehozott egy beszerzési szerződést, aktiválni kell mielőtt érvényessé válik. Beszerzési szerződés aktiválásához állítsa a **Szerződés megjelölése érvényesként** beállítást **Igen** pozícióba.

## <a name="commitment-types"></a>Kötelezettségtípusok
A beszerzési szerződés minden sora egy-egy kötelezettségvállalás bizonyos vásárlásra. A kötelezettségvállalás kielégítésére több különböző beszerzési rendelés sorait is használhatja. A kötelezettségeknek négy típusa van:

-   **Termékmennyiségi kötelezettség** – Bizonyos mennyiséget kell beszereznie egy termékből.
-   **Termék értékére vonatkozó kötelezettség** – Bizonyos pénzmennyiségnek megfelelő mennyiséget kell beszereznie egy termékből.
-   **Termékkategória értékére vonatkozó kötelezettség** – Bizonyos pénzmennyiségnek megfelelő rendelést kell beszereznie egy beszerzési kategóriából. Az összeg vonatkozhat katalóguscikkre vagy a katalóguson kívüli cikkre is.
-   **Értékre vonatkozó kötelezettség** – Egy adott pénzmennyiségnek megfelelő rendelést kell beszereznie bármely termékből vagy tetszőleges beszerzési kategóriában lévő termékekből.

## <a name="pricing-terms-for-purchase-agreements"></a>Beszerzési szerződések árképzési feltételei
Az árképzési feltételek a kötelezettségvállalás típusától függően többfélék lehetnek. A beszerzési szerződések árképzési feltételei felülírnak minden egyéb más, kereskedelmi megállapodásokhoz beállított fizetési feltételt. A következő táblázat leírja az egyes kötelezettségtípusoktól függő árspecifikus mezőket. Az olyan mezők, amelynél van **Yes** beállítás, frissíthetők a rendeléssorban.

| Kötelezettség típusa                   | Egységár | Áregység | Engedményszázalék | Készpénzfizetési engedmény összege |
|-----------------------------------|------------|------------|------------------|----------------------|
| Termékmennyiségi kötelezettség       | Igen        | Igen        | Igen              | Igen                  |
| Termék értékére vonatkozó kötelezettség          |            |            | Igen              |                      |
| Termékkategória értékére vonatkozó kötelezettség |            |            | Igen              |                      |
| Értékre vonatkozó kötelezettség                  |            |            | Igen              |                      |

## <a name="policies-for-purchase-agreements"></a>Beszerzési szerződések irányelvei
A következő irányelvek határozzák meg a módot, ahogy a beszerzési szerződés kötelezettsége és a megfelelő beszerzésirendelés-sorok közötti kapcsolat működik:

-   **Maximum betartása** – Az összes rendelési sor összes mennyisége vagy összege nem haladhatja meg azt a mennyiséget vagy összeget, amely a kapcsolódó kötelezettségben van megadva.
-   **Rögzített ár és engedmény** – A rendeléssorban található ár és a hozzá kapcsolódó kötelezettségvállalásban megadott ár nem lehet eltérő. Ha a rendelési sorban módosítja az árat, akkor a kapcsolat a kötelezettségvállaláshoz megszakad. Ha a kapcsolat megszakad, akkor a rendeléssor nem számít bele a kötelezettségvállalás teljesítésébe.
-   **Kiadás minimális összege és kiadás maximális összege** – +Ha itt szerepel összeg, akkor egy üzenet jelenik meg, valahányszor úgy próbálja módosítani a rendeléssort, hogy az eltér a hozzá kapcsolódó kötelezettségvállalástól.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Beszerzési szerződések teljesítésének kiszámítása
A teljesítési mennyiségek és összegek a **Teljesítés** lapon, az **Értékesítési szerződések** lap **Soradatok** gyorslapján belül láthatóak.  

A **Teljesítés** terület mutatja a hátralévő összeget vagy mennyiséget, amely szükséges a kötelezettség teljesítéséhez.  

A **Megállapodás** terület mutatja az összes mennyiséget vagy összeget, amelyhez érvényes az értékesítési szerződés sora.  

A beszerzésirendelés-sorok és a számlasorok, amelyek hozzájárulnak a számítás teljesítéséhez hozzáférhetőek a **Kapcsolódó információk** művelet kijelölésével a sorokban vagy a beszerzési megállapodás fejlécében.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Beszerzési szerződés visszaigazolási és verzióelőzményeinek megtekintése
Miután a beszerzési szerződést megerősítették, aktuális verziója bekerül az előzményeket tároló táblába. Ha módosítja a beszerzési szerződést, akkor is újra megerősítheti, ezzel új verziót tárol el az előzményekben. Ha nem erősíti meg a beszerzési szerződést, akkor is használhatja beszerzési rendelések létrehozásához. Ilyenkor azonban a beszerzési szerződés előzményadatait nem tárolja. A megállapodás minden verzióját kinyomtathatja, vagy megtekintheti az előnézetét. Ezután megoszthatja a revíziókat szállítójával, hogy jóváhagyását kérje rájuk.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Beszerzési szerződések használata a rendelési folyamatban
Amikor beszerzési rendelést hoz létre alkalmazhat hozzá egy beszerzési megállapodást. A megállapodás feltételeinek információja, úgy mint fizetési feltételek, szállítási feltételek és szállítási cím ezután a beszerzési rendelés fejlécébe másolódik. Ha a beszerzési rendelés tartalmaz egy vagy több sort olyan termékekhez, vagy kategóriákhoz, amelyek szerepelnek a megállapodásnak, akkor az árak és engedmények a beszerzési megállapodásból azokra a sorokra lesznek alkalmazva. Az összeg vagy mennyiség a rendelési soron hozzájárul a beszerzési megállapodás kötelezettségének teljesítéséhez. Ugyanaz a beszerzési rendelés tartalmazhat sorokat, amelyek nincsenek kapcsolatban egy beszerzési szerződéssel és sorokat, amelyek rendelkeznek kötelezettséggel egy beszerzési szerződéshez.  

Csak egy beszerzési rendelés létrehozásakor jelölhető ki a beszerzési szerződés. A beszerzési rendelés létrejötte után ki nem jelölhet ki beszerzési szerződést.  
Bizonyos esetekben, amikor a beszerzési rendelést közvetetten hozza létre beállíthatja, hogy a Supply Chain Management automatikusan rákeressen-e az alkalmazható beszerzési szerződésekre. Ez a funkció például akkor hasznos, ha automatikusan erősít meg tervezett beszerzési rendeléseket, vagy értékesítési rendelésen alapuló beszerzési rendeléseket hoz létre.

## <a name="matching-policy-on-purchase-agreements"></a>Egyeztetési irányelv beszerzési szerződéseknél
A beszerzési szerződés fejlécében definiálni lehet egy soregyeztetési szabályt. Ez a soregyeztetési irányelv figyelembe veszi a kötelezettségek paramétereinek soregyeztetési irányelvét, ha a **Kötelezettségek paraméterei** oldal **Egyeztetési irányelv felülbírálásának engedélyezése** mezőjének (az **Ár és mennyiség egyeztetése** gyorslapon) értéke **Vállalati irányelvnél magasabb**. A beszerzési szerződésre hivatkozó dokumentumok a beszerzési szerződés fejlécében megadott soregyeztetési irányelvet fogják használni, hacsak a kapcsolódó cikk, cikk és szállító vagy kategória beszerzési irányelvében máshogy nem határoztak.

## <a name="purchase-agreements-and-intercompany-trade"></a>Beszerzési szerződések és vállalatközi kereskedelem
Vállalatközi kereskedelmi kapcsolat hozható létre például különböző jogi személyeknél található szállítói és vevői számlák között. Ha az egyik félhez beszerzési vagy értékesítési rendelés készül, vállalatközi rendelési lánc jön létre. A rendelési láncban a rendszer a megfelelő jogi személyben hozza létre a beszerzési rendelést és az értékesítési rendelést.  

A vállalatközi kereskedelmi felekhez beszerzési szerződést vagy értékesítési szerződést is létrehozhat. Ezt követően könnyen generálhat egy ehhez kapcsolódó értékesítési vagy beszerzési szerződést a másik vállalatközi kereskedelmi félnek számító másik jogi személy számára.  

Ha vállalatközi beszerzési rendelést hoz létre, amely az egyik jogi személy vállalatközi beszerzési szerződését használja, akkor a megfelelő vállalatközi értékesítési rendelés a másik jogi személy megfelelő értékesítési szerződését fogja használni. Az értékesítési szerződések és a beszerzési szerződések kötelezettségeinek teljesítése egymással szinkronizálva van, épp úgy, ahogyan a vállalatközi értékesítési rendelés és a vállalatközi beszerzési rendelés is összhangban van egymással.

## <a name="financial-dimensions-on-purchase-agreements"></a>Beszerzési szerződés pénzügyi dimenziói
Pénzügyi dimenziókat átmásolhat beszerzési szerződések fejlécébe vagy egyedi soraiba is. Ha módosítja a dimenziókat a szerződés-fejlécben, vagy szerződéssorokban, akkor a módosítás nem lesz hatással egy kiadott rendelésre sem, de hatással lesz az új rendelésekre.

<a name="additional-resources"></a>További erőforrások
--------

[Beszerzési szerződés létrehozása](tasks/create-purchase-agreement.md)

[Beszerzésirendelés-kiadás létrehozása beszerzési szerződésből](tasks/create-purchase-release-order-purchase-agreement.md)



