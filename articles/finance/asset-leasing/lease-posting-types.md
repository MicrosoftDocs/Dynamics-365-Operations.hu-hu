---
title: Lízingfeladási típusok
description: Ez a témakör az eszközlízing-tranzakciókhoz használt feladási típusokat ismerteti.
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
ms.openlocfilehash: 9b7d8c545c1addaa570d54855bbad6c576783007
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229502"
---
# <a name="lease-posting-types"></a>Lízingfeladási típusok

[!include [banner](../includes/banner.md)]

Ez a témakör az eszközlízing-tranzakciókhoz használt feladási típusokat ismerteti.

## <a name="lease-asset"></a>Lízingeszköz

A számla a használatijog-eszközhöz (ROU) van társítva. Ezt a számlát akkor terhelik meg, ha a lízinget először az új lízingszámviteli standardok, a könyvelési standardok kodifikációs témakör 842 (ASC 842) és a nemzetközi Financial Reporting Standard 16 (IFRS 16). Módosított lízing esetén ez a számla megterhelhető vagy jóváírható, attól függően, hogy a módosítás növeli vagy csökkenti a lízingkötelezettséget.

**Példa naplóbejegyzések:** Kezdeti elszámolás<br>
**Terhelés:** XXX lízingeszköz<br>
**Jóváírás:** XXX lízingkötelezettség

## <a name="lease-liability"></a>Lízingkötelezettség

A számla a lízingkötelezettséghez kapcsolódik, amely akkor jelentkezik, amikor a kifizetéseket az új IFRS 16 és ASC 842 szabványok szerint árazzák le. Ez a számla akkor kerül jóváírásra, ha a lízinget először az új standardok szerint ismerik el. Megterhelik a lízingfizetésekkel, és jóváírják a kamatelhatárolások miatt.

**Példa naplóbejegyzések:** Kezdeti elszámolás<br>
**Terhelés:** XXX lízingeszköz<br>
**Jóváírás:** XXX lízingkötelezettség

**Példa naplóbejegyzések:** Kamatelhatárolás<br>
**Terhelés:** XXX kamatköltség<br>
**Jóváírás:** XXX lízingkötelezettség

**Példa naplóbejegyzések:** Lízingdíjfizetés<br>
**Terhelés:** XXX lízingkötelezettség<br>
**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés

## <a name="short-term-lease-liability"></a>Rövid lejáratú lízingkötelezettség

A számla a rövid távú lízingkötelezettséghez kapcsolódik a rövid távú lízingkötelezettség átsorolás naplóbejegyzésének feladásakor. Ezt a számlát a hónap utolsó napján az amortizációs ütemezésből származó rövid távú kötelezettségjóváírásból írják jóvá. Ugyanezt az összeget azonban a következő hónap első napján vonják le.

**Példa naplóbejegyzésekre:** Rövid távú lízingkötelezettség átsorlása<br>
**Terhelés:** XXX lízingkötelezettség<br>
**Terhelés:** XXX rövid távú lízingkötelezettség<br>
**Jóváírás:** XXX rövid távú lízingkötelezettség<br>
**Jóváírás:** XXX lízingkötelezettség

## <a name="depreciation-expense"></a>Értékcsökkenés költsége

A számla az IFRS 16 és ASC 842 szerinti ROU-eszköz értékcsökkenéséhez kapcsolódó ráfordításhoz, és a IFRS 17 és az ASC 840 szabványok alatti pénzügyi lízinghez kapcsolódik. Ez a számla akkor kerül megterhelésre, ha egy ROU-eszköz havi értékcsökkenéssen esik át.

**Példa naplóbejegyzések:** Értékcsökkenés-elhatárolás<br>
**Terhelés:** XXX értékcsökkenési költség<br>
**Jóváírás:** XXX halmozott értékcsökkenés

## <a name="gainloss-on-lease-modification"></a>Nyereség/veszteség a lízing módosításakor

A számla a lízingmódosításából származó nyereséghez vagy veszteséghez kapcsolódik. Nyereség keletkezhet a lízing módosítása során, ha a módosítás a lízingkötelezettséget olyan összeggel csökkenti, amely meghaladja a ROU-eszköz szerinti értékét.

Például a lízingnek 150.000 dollár a lízingkötelezettségének könyv szerinti értéke és a ROU-eszköznek 100.000 dollár a könyv szerinti értéke. A lízing módosult, és ez a módosítás a jövőbeli minimális lízingfizetések (PVFMLP) új, 40.000 dolláros jelen értékét hozza létre elő. Ezért a lízingkötelezettséget 110.000 dollárral (150.000 dollár – 40.000 dollár) terhelik meg. Mivel a ROU.eszköz csak 100.000 dollár, ezért a 110.000 dollár 0 (nulla) alá csökkenti az eszközt. Ezért a könyvelési útmutató kimondja, hogy a fennmaradó részt egy nyereségszámlára kell könyvelni. Ebben az esetben a záró naplóbejegyzés a 110.000 dollár lízingkötelezettségének terhelési értéke, a 100.000 dollár lízingeszközhöz történő jóváírása, és a 10.000 dollár nyereségszámláján történő jóváírás.

**Példa naplóbejegyzések:** Lízingmódosítás<br>
**Terhelés:** XXX lízingkötelezettség<br>
**Jóváírás:** XXX lízingeszköz<br>
**Terhelés:** XXX nyereség

## <a name="accumulated-depreciation"></a>Halmozott értékcsökkenés

A számla a ROU-eszköz elleneszköz-számlájához van társítva. Ezen a számlán az értékcsökkenési költség feladásakor egy követel tétel jelenik meg.

**Példa naplóbejegyzések:** Értékcsökkenés-elhatárolás<br>
**Terhelés:** XXX értékcsökkenési költség<br>
**Jóváírás:** XXX halmozott értékcsökkenés

## <a name="retained-earnings"></a>Mérleg szerinti eredmény

A számlához társított visszatartott keresetek. Ezt a számlát megterhelik vagy jóváírják egy átmeneti helyesbítési naplóbejegyzésben a teljes visszamenőleges módszerrel vagy az A kumulatív felzárkózási lehetőség módszerrel. Az eredeti ROU-eszköz és a lízingkötelezettség közötti különbözetet a halmozott értékcsökkenésre könyvelték el. Ritka esetekben a fenntartott bevételeket a lízing módosítása is érintheti, ha a lízing besorolása finanszírozásról működésire változik, hogy a ROU-eszközt felfelé vagy lefelé írja, hogy az egyenlő legyen a lízingkötelezettséggel.

**Példa naplóbejegyzések:** Átmeneti kiigazítás (teljes visszamenőleges vagy kumulatív felzárkózási lehetőség A módszer)<br>
**Terhelés:** XXX lízingkötelezettség<br>
**Jóváírás:** XXX lízingeszköz<br>
**Jóváírás:** XXX fenntartott bevételek

## <a name="variable-payment"></a>Változó fizetés

A számla olyan változó lízingfizetésekhez kapcsolódik, amelyeket az ASC 842, ASC 840 és IAS 17 lízingek indexátértékelése alapján állítanak elő. A lízingfizetési ütemezésben a változó fizetések a **Változó fizetés** oszlopban szerepelnek. Ez a számla terhelt, ha számlát hoz létre egy változó kifizetést tartalmazó fizetési ütemezési sorral szemben.

**Példa naplóbejegyzések:** Lízingdíjfizetés<br>
**Terhelés:** XXX lízingkötelezettség<br>
**Terhelés:** XXX változó fizetés<br>
**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés

## <a name="deferred-rent-asset-liability"></a>Halasztott bérleti díjjal rendelkező eszköz (kötelezettség)

A számla a halasztott bérleti díj eszközhöz vagy kötelezettséghez kapcsolódik, amelyet egy halasztott bérleti díjkezelési lízing állít elő. Ez a számla akkor lesz megterhelve, ha a számlát halasztott bérleti díjkezelési lízinggel szemben adják fel, ha a lízing kifizetésének összege meghaladja az időszak egyenes körű bérleti költségeit. Jóváírásra kerül, ha a lízingfizetés kisebb, mint az időszak lineáris bérleti költsége.

**Példa naplóbejegyzésekre:** Lízingfizetés (halasztott bérleti díjkezelési lízing)<br>
**Terhelés:** XXX bérleti költség<br>
**Jóváírás:** Halasztott bérleti díj kötelezettség XXX<br>
**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés

## <a name="lease-expense"></a>Lízingköltség

A számla akkor kapcsolódik a lízingköltséghez, ha a lízing halasztott bérleti díjkezelési lízingként van besorolva. Ez a számla akkor kerül megterhelésre, ha egy számlát halasztott bérleti díjkezelési lízingbe adnak fel.

**Példa naplóbejegyzésekre:** Lízingfizetés (halasztott bérleti díjkezelési lízing)<br>
**Terhelés:** XXX bérleti költség<br>
**Jóváírás:** Halasztott bérleti díj kötelezettség XXX<br>
**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés

## <a name="impairment-expense"></a>Értékvesztési költség

A fiók fel lesz adva, ha a lízing értékvesztett. Ez a számla megterhelve, míg a ROU-eszközszámla közvetlenül jóváírásra kerül.

**Példa naplóbejegyzések:** Lízingdíjfizetés<br>
**Terhelés:** Értékvesztési költség XXX<br>
**Jóváírás:** ROU-eszköz XXX

## <a name="lease-payment"></a>Lízingdíjfizetés

A számla fel lesz adva, ha a **Fizetés a szállítónak** paraméter ki van kapcsolva. Ez a számla jóváírásra kerül a fizetendő szállító helyett, ha a paraméter ki van kapcsolva.

**Példa naplóbejegyzések:** Lízingdíjfizetés<br>
**Terhelés:** XXX lízingkötelezettség<br>
**Jóváírás:** Lízingfizetés XXX

## <a name="expense-type-postings"></a>Költségtípus feladásai

Az egyes költségtípusokhoz kiválasztott számla terhelve van, amikor az adott költségtípushoz kifizetés jön létre. Például a **Biztosítás** költségtípusához megadott számla meg lesz terhelve, amikor számla vagy kifizetési naplóbejegyzés jön létre a biztosítási költségek végrehajtási költségütemezéséből.

**Példa naplóbejegyzések:** Biztosításfizetés<br>
**Terhelés:** Biztosítási költség típusú számla XXX<br>
**Jóváírás:** Ellenszámla XXX

> [!NOTE]
> Az ellenszámla a végrehajtási költségfizetési ütemezés soraiban a lízing szintjén van kiválasztva. Ez az ellenszámla társítható a szállítóhoz vagy egy főkönyvi számlához.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]