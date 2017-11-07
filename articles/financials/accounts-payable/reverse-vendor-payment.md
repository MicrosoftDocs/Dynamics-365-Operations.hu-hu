---
title: "Borderó kifizetés sztornózása"
description: "Ez a cikk egy kifizetés sztornírozását, törlését, érvénytelenítését és visszautasítását mutatja be. Elmagyarázza továbbá szállítói számlák sztornírozásának két módját."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 736432a7e128f6b7b0d7ed5e0156c0769407bbaa
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="reverse-a-vendor-payment"></a>Borderó kifizetés sztornózása

[!include[banner](../includes/banner.md)]


Ez a cikk egy kifizetés sztornírozását, törlését, érvénytelenítését és visszautasítását mutatja be. Elmagyarázza továbbá szállítói számlák sztornírozásának két módját. 

Bizonyos esetekben szállítói kifizetés feladása után a kifizetés sztornírozni kell. Sztornírozás eltér a törlése, érvénytelenítése vagy a kifizetés elutasítása. A kifizetés csak akkor, ha az állapota törölheti **Készült**. Azt jelzi, hogy a kifizetés létrejött, de még még nem lett létrehozva. Mindig ez a korlátozás vonatkozik, függetlenül attól, a fizetési mód. Fel nem adott csekkek lehet érvényteleníteni, azok elkészülte után, de csak akkor feladni. Ha a létrehozott fizetési az alap elektronikus átutalás (EFT) szerint történik, feladás előtt visszautasítja a kifizetés. Egy kifizetés elutasításához módosítsa a **Fizetés állapota** értéket. A kifizetés érvénytelenítve vagy elutasított újra kell generálni után a **Kifizetési állapot** beállítás **Nincs** értékre módosul. 

A kifizetés feladása után a sztornírozások használhatók. Elektronikusan végrehajtott kifizetéseket nem lehet visszavonni azok feladása után. Ehelyett új tranzakciót kell létrehozni a kifizetés összegéről, hogy visszaállítsa a kötelezettséget a szállító számlájára. A feladott csekkek sztornírozására kétféle lehetőség van. Egy metódusban sztornírozásának feladása azonnal megtörténik, amikor rákattint **Kifizetés sztornírozása** meg a **Ellenőrzése** oldalon. A másik esetben ha a **Ellenőrzés** képernyőn a **Kifizetés sztornírozása** gombra kattint, a rendszer előbb elküldi a sztornírozást a Készpénz- és bankkezelési modul naplójába, ahol egy ellenőr feladhatja vagy elutasíthatja a sztornírozást. 

Tudnivalók a szervezet által használt módszertől, megtekintheti a **Készpénz- és bankkezelési paraméterek** oldalon. Ha a **Használata ellenőrzési folyamat a kifizetések sztornírozásakor** beállítás **Igen**, sztornírozásokat ellenőrzésre sztornírozási napló ellenőrzése. A következő táblázat leírja, hogyan a csekk sztornírozása módszerek különböznek egymástól.

| Ha a szervezet nem tekintse át a feladás előtt bankcsekk-sztornírozás                                                                                                                                  | Ha a szervezet nem tekintse át a feladás előtt bankcsekk-sztornírozás                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Azonnal megtörténik, amikor rákattint a csekket sztornírozott **OK** a **Ellenőrzés** oldalon.                                                                                                                      | A csekk nem azonnal vissza. A Csekksztornírozási naplóban ellenőrzésre jön létre. Ha törli a Csekksztornírozási naplóban, a csekk újra akkor lehet sztornírozni.                                                                                                                                                                                                                                                                |
| A könyvelési tételeket, az eredeti csekk sztornírozása.                                                                                                                                         | Előfordulhat, hogy a főkönyvi számla az eredeti csekk könyvelési tétel nem lesz feladva. Az eredeti csekk naplóból származó pénzügyi dimenzióinak a Csekksztornírozási naplóban szereplő alapértelmezett pénzügyi dimenziókat. Az alapértelmezett mennyiség módosítható. A csekk sztornírozási napló feladása alkalmával a fő számlát, amelyre a kötelezettségek automatikusan kitölti a rendszer a feladási profilok, amelyek módosulhattak az. |
| A könyvelési az eredeti csekk feladásakor használt használt számlastruktúrákat sztornírozza a jelölőnégyzet, akkor is, ha a számlastruktúra módosítva lett. A kombináció nem érvényes acikkhez. | Számlastruktúra módosításakor után az eredeti csekk feladott pénzügyi dimenzió általában meg kell adni a sztornírozás a csekk. Ez a pénzügyi dimenzió előfordulhat, hogy nem lehet automatikusan beírja az eredeti kifizetési naplóból. A főkönyviszámla-kombináció érvényességét a csekk sztornírozása feladásakor.                                                                                                        |
| Rögzített dimenziók segítségével garantálható, hogy ugyanazt a főkönyvet a program sztornírozza a sztornírozás nem érvényes.                                                                                      | Rögzített dimenziók a csekk sztornírozási napló feladása során érvényesek. A pénzügyi dimenzióérték nem létezik a könyvelési tételt az eredeti csekk, attól függően, hogy ha a rögzített dimenzió meg van adva.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Feladott csekk sztornírozása megtekintés nélkül
Ha a vállalat által azonnal megtörténik, amikor rákattint a bankcsekk-sztornírozási feladandó **Kifizetés sztornírozása** az **Ellenőrzések** képernyőn, kövesse az alábbi lépéseket. A naplótípus használatához állítsa az **Ellenőrzési folyamat alkalmazása a kifizetések sztornírozásakor** lehetőséget a **Készpénz- és bankkezelési paraméterek** oldalon a **Nem** értékre. A **Csekkek** lapon kiválaszthatja a csekk visszavonására, és válassza ki **Kifizetés sztornírozása**. Adja meg a dátumot, és válassza ki a sztornírozás okát.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>A Csekksztornírozási naplóban a megtekintés után feladott csekk sztornírozása
Ha a vállalat által a feladás előtt tekintse át a bankcsekk-sztornírozási, ellenőrzésre és a csekk sztornírozási napló létrehozása a **készpénz- és bankkezelési paraméterek** oldal, állítsa be a **használata ellenőrzési folyamat a kifizetések sztornírozásakor** lehetőséggel **Igen**. A **Csekkek** lapon kiválaszthatja a csekk visszavonására, és válassza ki **Kifizetés sztornírozása**. Adja meg a dátumot, és válassza ki a sztornírozás okát. Hozzon létre egy naplót, egy naplónevet is be kell jelölnie a sztornírozás naplót.

### <a name="review-a-reversal"></a>Sztornírozás ellenőrzése

Ha Önnek felhasználóként feladatai közé tartozik a sztornírozások ellenőrzése, a következő lépéseket kell végrehajtania. Választhat, hogy jóváhagyja a sztornírozást, és feladja a naplót, vagy elutasítja a sztornírozást. A **Csekksztornírozási** lapon kiválaszthatja az ellenőrzendő naplót, tekintse át, majd **Sorok**. Ellenőrizze a sztornírozást, és válasszon a következő jóváhagyási lehetőségek közül:

-   A jóváhagyáshoz és a napló feladásához kattintson a **Feladás** vagy a **Feladás és átvitel** elemre.
-   A sztornírozást úgy utasíthatja vissza, hogy törli a sztornírozás sorát.

> [!NOTE]
> A napló törlése eltávolítja a rendszerből a sztornírozást, de az eredeti csekk megmarad a **Ellenőrzés** képernyőn. Ezt követően a csekk állapota nem **Visszavonásra vár** lesz.

## <a name="results-of-posting-a-reversal"></a>Sztornírozás feladásának eredményei
Csekksztornírozás feladásakor a következők történnek:

-   A csekk állapota **Visszavonás** értékre frissítődik.
-   Ha a **Egyeztetés** beállítást választotta, a sztornírozás oldalon a sztornírozás során, a csekk egyeztetése (a **Egyeztetve** beállítás van megadva), és nem jelenik meg a **Egyeztetési számla** lap.
-   Megtörténik a sztornírozási bizonylat feladása azzal a bankszámlával szemben, ahonnan a csekk kiállítása történt, és ezzel a bankszámla egyenlege megnő.
-   Megtörténik a bizonylat feladása a főkönyvbe.
-   A rendszer frissíti a módosítás részleteit a **Ellenőrzés** oldal **Előzmények** mezőcsoportjában.

> [!NOTE] 
> Vállalatközi tranzakcióra kiadott csekk sztornírozásakor az ellentételező bejegyzések forrása a vállalati könyvelési beállítás, nem az eredeti tranzakció. Ha a sztornírozott csekk szállítói kifizetésre volt kiadva, a következő folyamatok is végbemennek:

-   Visszavonja a rendszer annak a számlának az alkalmazását az eredeti kifizetésre, amellyel szemben a kifizetés kiegyenlítése történt (sztornírozza a kiegyenlítést).
-   Tranzakciót ad fel a rendszer a szállítóval szemben a kifizetéssztornírozásra vonatkozóan, és a sztornírozott kifizetést az eredeti kifizetéssel szemben egyenlíti ki. A **Szállítói tranzakciók** oldal **Utolsó kiegyenlítés bizonylata** mezőjében az eredeti szállítói kifizetés frissítése a sztornírozott tranzakció bizonylatszámának felel meg.

Ha a sztornírozott csekk vevői kifizetésre volt kiadva, a következő folyamatok is végbemennek:

-   Tranzakciót ad fel a rendszer a kifizetéssztornírozás vevői rekordjával szemben, sztornírozza az eredeti kifizetés és a kifizetés eredeti kiegyenlítéséhez használt dokumentum közötti kiegyenlítést (negatív kifizetés jön létre).
-   Az eredeti kifizetésre kifizetéssztornírozást alkalmaz a rendszer. A **Szállítói tranzakciók** oldal **Utolsó kiegyenlítés bizonylata** mezőjében az eredeti szállítói kifizetés frissítése a sztornírozott tranzakció bizonylatszámának felel meg.





