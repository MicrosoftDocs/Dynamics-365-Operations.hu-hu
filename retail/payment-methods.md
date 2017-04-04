---
title: "Kifizetési módok"
description: "Minden egyes fizetéstípust, amely a kiskereskedő fogad el a rendszer beállításakor a kiskereskedelmi és kereskedelmi műveletek a Microsoft Dynamics 365 kell konfigurálni. Ez a cikk a beállítható fizetéstípusokat mutatja be, valamint azok beállításának folyamatát."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b887fc5d03ea8982515e92725ce98cc416e56f9e
ms.openlocfilehash: 011beec07bf1ab858892ab1c374f1acf3839e877
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods"></a>Kifizetési módok

Minden egyes fizetéstípust, amely a kiskereskedő fogad el a rendszer beállításakor a kiskereskedelmi és kereskedelmi műveletek a Microsoft Dynamics 365 kell konfigurálni. Ez a cikk a beállítható fizetéstípusokat mutatja be, valamint azok beállításának folyamatát.

A kiskereskedők fogadhat különböző típusú fizetés ellenében a termékek és szolgáltatások, amelyek értékesítik. Bár a leggyakrabban használt fizetési eszköz a készpénz, a kiskereskedők is csekken, bankkártyán, utalványon, és egyéb eszközökön is elfogadhatnak kifizetést. Minden egyes fizetéstípust, amely elfogadja a kiskereskedő Dynamics 365 műveletek - kereskedelmi rendszer beállításakor meg kell adni. Az alábbi lista minden egyes fizetéstípust Dynamics 365 műveletek - kiskereskedelmi beállíthatja:

-   **Készpénz** – a pénznem fizikai formában megjelenő eszköze, amely érme és bankjegy lehet. Ez a pénznem lehet a vállalati pénznem, vagy az üzlet helyi pénzneme.
-   **Csekk** – forgatható értékpapír, amely meghatározott összeg meghatározott pénznemben történő kifizetésére kötelezi a megadott bankot. Csekk általában határozatlan ideig vagy a kiadás napjától számított hat hónapig érvényes, hacsak nincs megadva egy másik érvényességi dátum. Ez az időszak változhat, a csekket kiállító banktól függően. A csekkeknek többféle típusa létezik, van például névre szóló, bemutatóra szóló és pénzfelvételi csekk is. Minden üzlethez beállíthat csekket fizetési módnak. A csekkek a vállalat szintjén vagy az üzlet szintjén meghatározott pénznemben fogadhatóak el. Előbb be kell állítania a csekket elfogadható fizetési módként, mielőtt elfogadhatná őket fizetésként az üzletben.
-   **Pénznem** – a vállalat alapértelmezett pénznemétől eltérő elsődleges fizeti formája. A pénznem érme és papírpénz formájában jelenhet meg. A pénznem kifizetési módja a Kiskereskedelem és kereskedelem modulban használt valamennyi pénznemet jelenti. Mielőtt ezt a fizetési módot használhatná, be kell állítania a pénznemeket, és meg kell határoznia a pénznemek kiskereskedelmi árfolyamait.
-   **Kártya** – A Kiskereskedelem és kereskedelem modulban használt minden kártyatípus, például bankkártyák és hitelkártyák. Érdemes egy kártyás fizetési módot beállítani a szervezet szintjén, amely minden kártyafajtát képvisel. Ezután az egyes üzletek szintjén minden olyan kártyához, illetve kártyacsoporthoz beállítható egy fizetési mód, amelyeket ugyanazokkal a beállításokkal kell feldolgozni. A kártya fizetőeszköz-típus használata előtt be kell állítania a piacon elérhető gyártók bank- és hitelkártyáit, hogy az üzlethez társíthassa azokat.
-   **Jóváírás** – A pénztárnál kiadott és beváltott jóváírások. A jóváírás lehet visszáru-jóváírás is, amelyet visszáruértékesítésre adnak ki. Ha egy jóváírást csak részben váltanak be, akkor a program új jóváírást állít ki az új egyenlegre. Az új jóváírás új számot is kap. A jóváírásiok csak egyszer használhatók fel, és a program minden felhasznált jóváírás számát nyilvántartja. A rekord a **Jóváírások tábla** oldalon tekinthető meg. A vevők nem válthatnak be a jóváírás értékénél nagyobb összeget.
-   **Ajándékutalvány** – a pénztárnál kiállított és beváltott ajándékutalványok. Az ajándékutalványoknál nem engedélyezett a túlfizetés.
-   **Vevőszámla** – Olyan fizetések, melyeket az értékesítés időpontjában a pénztáran levonnak a vevőszámláról. Ezzel a fizetési móddal emellett értékesítési információkat is gyűjthet, vagy nyilván tarthat vevőspecifikus engedményeket, amikor a vevő egy másik fizetési módon fizet. Ebben az esetben be kell állítania a vevőre jellemző információkat.
-   **A hűségpontok** – a vevők során hűségprogramok pontok. Hűségprogramok hoz létre, ha a felhasználók után pontot, majd beváltani különböző módokon. Példa: egyes hűségprogramoknál a vevők engedmény formájában válthatják be a hűségpontokat, de akári fizetési módként is használhatják.

A Kiskereskedelem és kereskedelem modulban a fizetési módok beállításához az alábbi lépéseket kell elvégeznie.

1.  A szervezet fizetési módjainak beállítása. A teljes szervezet által elfogadott fizetési módok létrehozása.
2.  Szervezeti szinten elfogadott kártyatípusok és kártyaszámok létrehozása. Hitelkártyák vagy betéti bankkártyák elfogadása esetén hozzon létre egy fizetési módot kártyák, és az majd a szervezeti szinten elfogadott kártyatípusok és kártyaszámok létrehozása.
3.  Üzlet fizetési mód beállítása. Fizetési módok társítása az egyes üzletekben, és írja be az egyes fizetési módokhoz adott üzletben jellemző beállításait.
4.  Üzletek kártyás fizetési módok beállítása. Minden karton Fizetési módok, amely az üzlet fogad el a kártya telepítésének befejezésére.



