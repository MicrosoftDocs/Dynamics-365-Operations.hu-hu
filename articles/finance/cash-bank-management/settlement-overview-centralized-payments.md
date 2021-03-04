---
title: Kiegyenlítés áttekintése (központosított kifizetések)
description: Ez a témakör leírja a központosított kifizetések kiegyenlítését a Microsoft Dynamics 365 Finance alkalmazásban.
author: abruer
manager: AnnBe
ms.date: 08/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 222414
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea661441c6c810d144d423b054c1bef058cdd9d6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443966"
---
# <a name="settlement-overview-for-centralized-payments"></a>Kiegyenlítés áttekintése központosított kifizetésekre vonatkozóan

[!include [banner](../includes/banner.md)]

Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egy jogi személy használatával, amely minden kifizetést kezel. Így nem szükséges ugyanazt a tranzakciót több jogi személyhez bevinni, valamint a fizetési javaslat folyamatának, a kiegyenlítés folyamatának, a nyitott tranzakciók szerkesztésének és a lezárt tranzakciók szerkesztésének leegyszerűsítésével időt takarít meg a központosított kifizetéseknél. 

Amikor egy vevői vagy szállítói kifizetést az egyik jogi személynél visznek be, és egy másik jogi személynél bevitt számlával egyenlítenek ki, mindegyik jogi személyhez automatikusan létrejön a megfelelő kiegyenlítés, valamint a mindkét irányú esedékességet kifejező tranzakciók. A tranzakcióban érintett mindegyik számla-kifizetés kombinációhoz kiegyenlítési rekord jön létre. Minden egyes kiegyenlítési rekord új bizonylatszámot kap, amelynek alapja a kifizetési bizonylat számlaszáma, amely a **Kinnlevőségek paraméterei** lapon található a vevők esetén, illetve a **Kötelezettségek paraméterei** lapon a szállítók esetén. 

Ha készpénzfizetési engedményekhez, devizaátértékelésekhez, fillérkülönbözetekhez, túlfizetésekhez vagy alulfizetésekhez további kiegyenlítési rekordok jönnek létre, ezeket a kifizetési vagy számlatranzakció későbbi dátumához rendeli a rendszer hozzá. Ha a kiegyenlítésre a kifizetés feladása után kerül sor, a kiegyenlítési rekordok a **Nyitott tranzakciók kiegyenlítése** lapon megadott dátumot használják a kiegyenlítés feladásaként.

## <a name="posting-types-transaction-types-and-default-descriptions"></a>Feladási típusok, tranzakciótípusok és alapértelmezett leírások

A vállalatközi kiegyenlítési bizonylatok tranzakciói a vállalatközi kiegyenlítés feladási típust, a vállalatközi vevői kiegyenlítési és a vállalatközi szállítói kiegyenlítési tranzakciótípusokat használják. A tranzakciótípusra vonatkozó adatokat az **Alapértelmezett leírások** lapon állíthatja be. 

Egyvállalatos és vállalatközi kiegyenlítéseknél a következő típusú tranzakciók használhatók:

-   Kiegyenlítés
-   Készpénzfizetési engedmény
-   Devizaátértékelések (a realizált és nem realizált devizaátértékeléseket tartalmazza)
-   Fillérkülönbözet
-   Túlfizetés/alulfizetés

A vállalatközi kiegyenlítési bizonylatokhoz alapértelmezett leírásokat is meghatározhat.

## <a name="currency-exchange-gains-or-losses"></a>Árfolyamnyereségek vagy -veszteségek

A vevői vagy szállítói tranzakciókhoz használt árfolyamot a tranzakcióval együtt tárolja a rendszer. A realizált árfolyamveszteség- vagy nyereség feladása a számlázó vagy a kifizető jogi személynek történik attól függően, hogy a kifizető jogi személynél a **Vállalatközi könyvelés** lapon az **Árfolyamnyereség- vagy -veszteség feladása** mezőjében milyen beállítás van megadva. Az alábbi példákban a következő pénznemek szerepelnek:
-   Fizetés könyvelési pénzneme: EUR
-   Számla könyvelési pénzneme: USD
-   A kifizetési tranzakció pénzneme: DKK
-   A számlatranzakció pénzneme: CAD

### <a name="currency-calculations"></a>Árfolyamszámítások

Amikor az egyik jogi személynél bevitt számla kiegyenlítése egy másik jogi személynél bevitt kifizetéssel történik, a kifizetési tranzakció pénznemének (DKK) átváltása három lépésben történik:
1.  Átváltás a kifizetés könyvelési pénznemére (EUR) a számlázó jogi személynek a kifizetés napján érvényes árfolyamának alkalmazásával.
2.  Átváltás a számla könyvelési pénznemére (USD).
3.  Átváltás a számla tranzakció pénznemére (CAD) a számlázó jogi személy árfolyamának alkalmazásával.

Az átváltási folyamat a kifizetés napján érvényes árfolyamokat használja. Ha a tranzakció pénznemében (CAD) így létrejövő kifizetési összeg egyenlő a számla összegével (CAD), a számlát teljes egészében kifizetettnek tekinti a rendszer. 

Amikor a **Nyitott tranzakciók kiegyenlítése** lapot olyan kifizetési naplóból nyitják meg, ahol nincs megadva kifizetési összeg, a kiegyenlítendő összeg a **Nyitott tranzakciók kiegyenlítése** lapon kiegyenlítésre kiválasztott számlák alapján történik. A kiegyenlítendő összeg átváltása három lépésben történik:
1.  Átváltás a számla könyvelési pénznemére (USD) a számlázó jogi személynek a kifizetés napján érvényes árfolyamának alkalmazásával
2.  Átváltás a kifizetés könyvelési pénznemére (EUR) a számlázó jogi személynek a kifizetés napján érvényes árfolyamának alkalmazásával.
3.  Átváltás a kifizetési tranzakció pénznemére (DKK).

Az így létrejövő kifizetési összeget a **Nyitott tranzakciók kiegyenlítése** lap bezárásakor a rendszer átviszi a kifizetési napló sorára.

### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Az eltérő könyvelési pénznemekből adódó nyereség vagy veszteség feladása

Amennyiben árfolyamnyereség vagy -veszteség áll fenn, a nyereség vagy a veszteség feladása ahhoz a jogi személyhez történik, amelyet az **Árfolyamnyereség- vagy -veszteség feladása** mezőben adott meg a **Vállalatközi könyvelés** lapon kifizetés szerinti jogi személyként. A nyereség vagy veszteség összegét a rendszer átalakítja a feladás célját jelentő jogi személy könyvelési pénznemére az adott jogi személyhez megadott árfolyam alkalmazásával.

## <a name="cash-discounts"></a>Készpénzfizetési engedmények

A vállalatközi kiegyenlítési folyamat során létrejövő készpénzfizetési engedmények feladása a számlázó vagy a kifizető jogi személynek történik attól függően, hogy a kifizető jogi személynél a **Vállalatközi könyvelés** lapon a **Készpénzfizetési engedmény feladása** mezőben milyen beállítás van megadva. A számlázó jogi személynél létrejön a megfelelő kiegyenlítési tranzakció.

## <a name="overpayments-and-underpayments"></a>Túlfizetések és alulfizetések

A túlfizetések, az alulfizetések és a fillérkülönbözetek tűrését a túlfizetések esetében a kifizető jogi személy, az alulfizetések esetében a számlázó jogi személy alapján határozza meg a rendszer. A feladáshoz használt számlát vevők esetében a **Kinnlevőségek paraméterei** lap **Készpénzfizetési engedmény adminisztrációja** mezőjének beállítása, szállítók esetében a **Kötelezettségek paraméterei** lap **Készpénzfizetési engedmény adminisztrációja** mezőjének beállítása határozza meg.

-   Ha a készpénzfizetési engedmény adminisztrációjának beállítása Meghatározott, vagy ha a beállítás Meghatározatlan, és a túlfizetésből egy másik jogi személy számára történik a vonatkozó készpénzfizetési engedmény feladása, a program a Vevő készpénzfizetési engedménye, a Szállító készpénzfizetési engedménye vagy Fillérkülönbözet automatikus számlát használja. Ezeket a számlákat a **Számlák automatikus tranzakciókhoz** lapon adhatja meg.
-   Ha a készpénzfizetési engedmény adminisztrációjának beállítása Meghatározatlan, és a készpénzfizetési engedmény feladása ugyanannál a jogi személynél történik, mint a túlfizetés (ugyanaz a kifizető és a számlázó jogi személy), a rendszer korrigálja a készpénzfizetési engedmény számláját. Ha például egy 100,00 összegű számlán 3,00 készpénzfizetési engedmény vehető igénybe, és a számla egy 98,00 összegű kifizetéssel van kiegyenlítve, a rendszer a készpénzfizetési engedmény számláját 1,00 értékkel korrigálja. A nettó engedmény értéke 2,00.
-   Ha a készpénzfizetési engedmény adminisztrációjának beállítása Meghatározatlan, a készpénzfizetési engedmény feladása ugyanannál a jogi személynél történik, mint a túlfizetés, és a túl- vagy alulfizetés kiegyenlítése több, árengedményt tartalmazó számlával történik, a rendszer a legutolsó számla készpénzfizetési engedményét korrigálja.

Ha a készpénzfizetési engedmény adminisztrációjának beállítása Meghatározatlan, kizárólag a következő helyzetekben érvényesülnek a nem specifikus kifizetéselszámolási szabályok:
-   Túlfizetés van.
-   A túlfizetés kiegyenlítése egy vagy több olyan számlával történik, amely készpénzfizetési engedményt tartalmaz.
-   A készpénzfizetési engedmény feladása ugyanannál a jogi személynél történik, mint a túlfizetés.

A túl- vagy alulfizetések feladása minden egyéb helyzetben a Vevő készpénzfizetési engedménye, a Szállító készpénzfizetési engedménye vagy a Filléreltérés a könyvelési pénznemben automatikus számlára történik.

## <a name="sales-tax"></a>Forgalmi adó
Az áfatranzakciók megmaradnak azon a jogi személyen belül, ahol a feladásuk eredetileg történt. 

Ha előlegfizetéshez áfafeladás történt, a vállalatközi elszámolás az előleget fizető jogi személynél sztornírozza az előlegre jutó áfát. A számlán szereplő jogi személy adói a számlán szereplő jogi személynél maradnak.

## <a name="financial-dimensions"></a>Pénzügyi dimenziók
Vevői kifizetések esetében a kifizető jogi személy a jogi személytől és a jogi személy részére esedékes tranzakciói az éppen kiegyenlítés alatt álló kifizetés kinnlevőségek összesítő számlájához megadott pénzügyi dimenziókat használja. A számlázó jogi személynél a jogi személytől és a jogi személy részére esedékes tranzakciók az éppen kiegyenlítés alatt álló számla kinnlevőségek összesítő számlájához megadott pénzügyi dimenziókat használja. 

Szállítói kifizetések esetében a kifizető jogi személy a jogi személytől és a jogi személy részére esedékes tranzakciói az éppen kiegyenlítés alatt álló kifizetés kötelezettségek összesítő számlájához megadott pénzügyi dimenziókat használja. A számlázó jogi személynél a jogi személytől és a jogi személy részére esedékes tranzakciók az éppen kiegyenlítés alatt álló számla kötelezettségek összesítő számlájához megadott pénzügyi dimenziókat használja.

## <a name="withholding-tax"></a>Adóelőleg
A számlához társított szállítókód alapján lehet meghatározni, hogy kell-e adóelőleget számítani. Ha az adóelőleg érvényes, a számlához társított jogi személlyel együtt számítja ki a rendszer. A jogi személyek különféle pénznemeket használnak, a rendszer a használt számlához társított jogi személy árfolyamát használja.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]