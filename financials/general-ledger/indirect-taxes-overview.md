---
title: "Áfa áttekintése"
description: "Ez a cikk a forgalmiadó-rendszerről nyújt áttekintést. Bemutatja az áfa beállításának az elemeit, és azt, hogy ezek hogyan kapcsolódnak egymáshoz."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 69947558e66c9a719259b34ee920b7a5e822c5e1
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="sales-tax-overview"></a>Áfa áttekintése

[!include[banner](../includes/banner.md)]


Ez a cikk a forgalmiadó-rendszerről nyújt áttekintést. Bemutatja az áfa beállításának az elemeit, és azt, hogy ezek hogyan kapcsolódnak egymáshoz.

<a name="overview"></a>Áttekintés
--------

A forgalmiadó-keretrendszer számos különböző típusú közvetett adót támogat, mint például a forgalmi adót, általános forgalmi adót (áfa), az áruk és szolgáltatások adóját (GST), darabszám szerinti díjakat és adóelőleget. Ezen adók kiszámítása és dokumentálása beszerzési és értékesítési tranzakciók során történik. Rendszeres időközönként be kell vallani és be kell fizetni őket az adóhatóságoknak. 

A következő ábra az adóbeállítás entitásait és azok viszonyait szemlélteti.

[![TaxOverview](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Minden forgalmi adóhoz, amit a vállalatnak könyvelnie kell, áfakódot kell megadni. Az áfakód tartalmazza az adókulcsokat és a forgalmi adó számítási szabályait. 

Minden forgalmi adót hozzá kell rendelni egy áfakifizetési időszakhoz. Az áfakifizetési időszakok határozzák meg, mely időszakokban kell bevallani és kifizetni a forgalmi adókat az adóhatóságnak. Minden áfakifizetési időszakot hozzá kell rendelni egy adóhatósághoz. Az adóhatóság azt az entitást képviseli, ahova a forgalmi adót be kell vallani és ki kell fizetni. A forgalmi adó bevallásának elrendezését is az adóhatóság határozza meg. Az adóhatóságok kapcsolódhatnak a szállítói fiókokhoz. 

Minden áfakódot hozzá kell rendelni egy főkönyvi feladási csoporthoz. A főkönyvi feladási csoport határozza meg az áfakódok fő számláit, amely összegek bevallásra kerülnek. 

Nem kötelező forgalmiadó-jelentési kódok megadására is van lehetőség. Ezek hozzárendelhetők az áfakódokhoz számított különböző összegtípusok áfakódjaihoz. Az **Áfakifizetés kód szerint** jelentés a végösszegeket hatáskör szerint mutatja egy bizonyos áfakifizetési időszakra és intervallumra. 

Minden forgalmi adó számítását és bevallását igénylő tranzakcióhoz tartoznia kell egy áfacsoportnak és egy cikkáfacsoportnak. Az áfacsoportok kapcsolódnak a tranzakciót végző félhez (például a vevő vagy a szállító), mivel a cikkáfacsoportok a tranzakció erőforrásához kapcsolódnak (például cikk vagy beszerzési kategória). Az adócsoportok az adókódok listáját tartalmazzák. A tranzakció áfacsoportjában és cikkáfacsoportjában jelenlévő adókódok azok az adókódok, amelyek az adott tranzakcióra érvényesek. 

A következő táblázat az adó beállításához szükséges entitásokat és a sorrendet mutatja.

| Beállítási tevékenység                                                  | Szükséges/Nem kötelező; leírás                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fő számla létrehozása.                                           | Kötelező. A forgalmi adókkal kapcsolatos funkciók beállítása előtt létre kell hozni a vállalat által adók fizetésére és rögzítésére használt fő számlákat.                                                                                                                                                                             |
| Állítson be főkönyvi feladási csoportokat az áfához.                     | Kötelező. A főkönyvi feladási csoportok határozzák meg a forgalmi adó bevallására és befizetésére szolgáló fő számlákat.                                                                                                                                                                                                                            |
| Állítsa be az adóhatóságokat.                                   | Kötelező. Az adóhatóságok azok az entitások, ahova az adót be kell vallani és ki kell fizetni.                                                                                                                                                                                                                                   |
| Áfakifizetési időszakok beállítása.                            | Kötelező. Az áfakiegyenlítési időszakok tartalmazzák azt az információt, hogy mikor és milyen gyakran kell a forgalmi adót bevallani és kifizetni. Kapcsolódnak az adóhatósághoz.                                                                                                                                                       |
| Áfajelentési kódok beállítása.                               | Nem kötelező megadni. Az áfajelentési kódok hozzárendelhetők áfakódokhoz, ezáltal egy áfajelentési kód alatt több áfakódot is lejelenthet.                                                                                                                                                                 |
| Áfakódok beállítása.                                         | Kötelező. Az áfakódok tartalmazzák az adókulcsokat és az egyes forgalmi adók számítási szabályait. Az áfakódok kapcsolódnak egy áfakifizetési időszakhoz és egy főkönyvi feladási csoporthoz.                                                                                                                                        |
| Áfacsoportok beállítása.                                        | Kötelező. Az áfacsoportok tartalmazzák az eladási kódok listáját, amely a tranzakciót végző félre (vevő vagy szállító) érvényesek. Egy adott tranzakció esetében az áfacsoportban és a cikkáfacsoportban szereplő áfakódok metszete határozza meg azokat az áfakódokat, amelyek érvényesek a tranzakcióra.                  |
| Cikkáfacsoportok beállítása.                                   | Kötelező. A cikkáfacsoportok értékesítési kódok listáját tartalmazzák, amelyek a tranzakció erőforrására (termék, szolgáltatás stb.) érvényesek. Egy adott tranzakció esetében az áfacsoportban és a cikkáfacsoportban szereplő áfakódok metszete határozza meg azokat az áfakódokat, amelyek érvényesek a tranzakcióra. |
| Forgalmi adó paramétereinek beállítása az alkalmazás paraméter oldalán. | Kötelező. A különböző modulokban, például a Főkönyvben, a Kinnlevőségekben, és a Kötelezettségekben paramétereket kell beállítani a közvetett adók megfelelő számításához. Habár a legtöbb paraméter az alapértelmezett értékkel rendelkezik, a vállalat igényeinek megfelelően módosítani lehet ezeket.                                          |

## <a name="sales-tax-on-transactions"></a>Tranzakciók forgalmi adója
Minden tranzakcióhoz (értékesítési vagy beszerzési bizonylatsorok, naplók stb.) meg kell adnia egy áfacsoportot és egy cikkáfacsoportot a forgalmi adó számításához. A mesteradatok között alapértelmezett csoportok találhatók (például vevő, szállító, cikk és beszerzés kategóriák), de manuálisan is módosíthatja a tranzakciós csoportokat szükség esetén. Mindkét csoport tartalmazza az áfakódok listáját, és az áfakódok két listájának metszete határozza meg a tranzakcióhoz megfelelő áfakódokat. 

Minden tranzakcióhoz megtekintheti a számított forgalmi adót a **Forgalmi adó tranzakció** oldalon. Megtekintheti a forgalmi adót egy dokumentumsorra vagy a teljes dokumentumra. Bizonyos dokumentumok esetében (például a szállítói számla és a főkönyvi naplók) módosíthatja a számított forgalmi adót, ha az eredeti dokumentum eltérő összegeket tartalmaz.

## <a name="sales-tax-settlement-and-reporting"></a>Áfakiegyenlítés és -bevallás
A forgalmi adót be kell vallani és kifizetni az adóhatóságoknak szabályozott időközönként (havi, negyedéves stb.). A Microsoft Dynamics 365 for Operations tartalmaz egy funkciót, amely lehetővé teszi az adószámlák kiegyenlítését egy intervallumra és az egyenlegek kiegyenlítési számláján az egyenlegek kiegyenlítését a főkönyvi feladási csoportokban meghatározottak szerint. Ez a funkció elérhető a **Forgalmi adó kiegyenlítése és feladása** oldalon. Meg kell adnia az áfakiegyenlítési időszakot, amelyben a forgalmi adót ki kell egyenlíteni. 

A forgalmi adó kifizetése után az áfakiegyenlítési számlán az egyenleget a bankszámlával szemben kell meghatározni. Ha az áfakifizetési időszakhoz megadott adóhatóság egy szállítói számlához kapcsolódik, akkor az áfaegyenleg nyitott szállítói számlaként lesz feladva, és szerepeltethető a rendszeres kifizetési javaslatban.

## <a name="conditional-sales-tax"></a>Feltételes áfa
A feltételes forgalmi adó azt jelzi, hogy a számlán szereplő tényleges összegre megállapított áfának csak egy részét kell kifizetni. A rendes áfát ellenben a számlázás időpontjában számítjuk ki. A feltételes áfát a kifizetés, nem pedig a számla feladásakor kell megfizetni az adóhatóságnak. A számla könyvelésekor a tranzakciót jelenteni kell az áfakönyv-jelentésben. Az áfakifizetési jelentésből azonban a tranzakciót ki kell zárni. 

Ha a feltételes forgalmi adó jelölőnégyzetet bejelöli a főkönyvi paraméterek képernyőn, forgalmi adót nem kell levonni mindaddig, amíg ki nem fizeti a számlát. Ez egy jogi előírás néhány országban/régióban.

> [!NOTE]
> A Feltételes áfa jelölőnégyzet bejelölése esetén be kell állítani a funkciókat támogató áfakódokat, áfacsoportokat, és létre kell hozni a szükséges főkönyvi feladási csoportokat. |

###  <a name="example"></a>Példa

Az áfát havonta kell befizetni. Június 15-én kiállít egy 10 000 összegű számlát, plusz áfa.
-   Az áfa 25 százalékos, vagyis 2500.
-   Az számla fizetési határideje július 30.

Normál esetben akkor rendezne és fizetne be 2500-at az adóhatóságnak, amikor júniusban sor kerül a számla feladására - akkor is, ha a fizetést a vevőtől még nem kapta meg. 

Ha viszont feltételes áfát használ, akkor rendezi az adót az adóhatósággal szemben, amikor július 30-án megérkezik a kifizetés a vevőtől.




