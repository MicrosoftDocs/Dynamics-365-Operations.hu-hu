---
title: Kifizetési módok
description: Minden egyes fizetéstípust, amelyet a kiskereskedő elfogad, konfigurálni kell a rendszer beállításakor. Ez a cikk a beállítható fizetéstípusokat mutatja be, valamint azok beállításának folyamatát.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 60f0a2e5fa2dc2bc37a04b159a4834a52117893d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559604"
---
# <a name="payment-methods"></a>Kifizetési módok

[!include [banner](includes/banner.md)]

Minden egyes fizetéstípust, amelyet a kiskereskedő elfogad, konfigurálni kell a rendszer beállításakor. Ez a cikk a beállítható fizetéstípusokat mutatja be, valamint azok beállításának folyamatát.

A kiskereskedők fogadhat különböző típusú fizetés ellenében a termékek és szolgáltatások, amelyek értékesítik. Bár a leggyakrabban használt fizetési eszköz a készpénz, a kiskereskedők is csekken, bankkártyán, utalványon, és egyéb eszközökön is elfogadhatnak kifizetést. Minden egyes fizetéstípust, amelyet a kiskereskedő elfogad, konfigurálni kell a Dynamics 365 for Retail rendszer beállításakor. Az alábbi lista leírja az egyes fizetéstípusokat, amelyeket be lehet állítani a Dynamics 365 for Retail moduljában:

- **Készpénz** – a pénznem fizikai formában megjelenő eszköze, amely érme és bankjegy lehet. Ez a pénznem lehet a vállalati pénznem, vagy az üzlet helyi pénzneme.
- **Csekk** – forgatható értékpapír, amely meghatározott összeg meghatározott pénznemben történő kifizetésére kötelezi a megadott bankot. Csekk általában határozatlan ideig vagy a kiadás napjától számított hat hónapig érvényes, hacsak nincs megadva egy másik érvényességi dátum. Ez az időszak változhat, a csekket kiállító banktól függően. A csekkeknek többféle típusa létezik, van például névre szóló, bemutatóra szóló és pénzfelvételi csekk is. Minden üzlethez beállíthat csekket fizetési módnak. A csekkek a vállalat szintjén vagy az üzlet szintjén meghatározott pénznemben fogadhatóak el. Előbb be kell állítania a csekket elfogadható fizetési módként, mielőtt elfogadhatná őket fizetésként az üzletben.
- **Pénznem** – a vállalat alapértelmezett pénznemétől eltérő elsődleges fizeti formája. A pénznem érme és papírpénz formájában jelenhet meg. A pénznem kifizetési módja a Kiskereskedelem és kereskedelem modulban használt valamennyi pénznemet jelenti. Mielőtt ezt a fizetési módot használhatná, be kell állítania a pénznemeket, és meg kell határoznia a pénznemek kiskereskedelmi árfolyamait.
- **Kártya** – Minden használt kártyatípus, például bankkártyák és hitelkártyák. Érdemes egy kártyás fizetési módot beállítani a szervezet szintjén, amely minden kártyafajtát képvisel. Ezután az egyes üzletek szintjén minden olyan kártyához, illetve kártyacsoporthoz beállítható egy fizetési mód, amelyeket ugyanazokkal a beállításokkal kell feldolgozni. A kártya fizetőeszköz-típus használata előtt be kell állítania a piacon elérhető gyártók bank- és hitelkártyáit, hogy az üzlethez társíthassa azokat.
- **Jóváírás** – A pénztárnál kiadott és beváltott jóváírások. A jóváírás lehet visszáru-jóváírás is, amelyet visszáruértékesítésre adnak ki. Ha egy jóváírást csak részben váltanak be, akkor a program új jóváírást állít ki az új egyenlegre. Az új jóváírás új számot is kap. A jóváírásiok csak egyszer használhatók fel, és a program minden felhasznált jóváírás számát nyilvántartja. A rekord a **Jóváírások tábla** oldalon tekinthető meg. A vevők nem válthatnak be a jóváírás értékénél nagyobb összeget.
- **Ajándékutalvány** – a pénztárnál kiállított és beváltott ajándékutalványok. Az ajándékutalványoknál nem engedélyezett a túlfizetés.
- **Vevőszámla** – Olyan fizetések, melyeket az értékesítés időpontjában a pénztáran levonnak a vevőszámláról. Ezzel a fizetési móddal emellett értékesítési információkat is gyűjthet, vagy nyilván tarthat vevőspecifikus engedményeket, amikor a vevő egy másik fizetési módon fizet. Ebben az esetben be kell állítania a vevőre jellemző információkat.
- **Hűségpontok** – A vevők által a hűségprogramokban összegyűjtött pontok. Ha hűségprogramot hoz létre, a felhasználók pontokat gyűjthetnek, majd válthatnak be különböző módokon. Példa: egyes hűségprogramoknál a vevők engedmény formájában válthatják be a hűségpontokat, de akári fizetési módként is használhatják.

Fizetési módok beállításához a következő feladatokat kell elvégeznie.

1. A szervezet fizetési módjainak beállítása. A teljes szervezet által elfogadott fizetési módok létrehozása.
2. Szervezeti szinten elfogadott kártyatípusok és kártyaszámok létrehozása. Ha elfogadja a hitelkártyákat és bankkártyákat, akkor létre kell hoznia egy fizetési típust a kártyákhoz, majd létre kell hoznia a szervezetnél elfogadott kártyatípusokat és azok számait.
3. Üzlethez tartozó fizetési mód beállítása. Minden egyes üzlethez fizetési módokat kell társítania, majd meg kell adnia az egyes fizetési módok adott üzletben jellemző beállításait.
4. Kártyás fizetési módok beállítása az üzletekhez. Minden kártyás fizetési módhoz, amelyet az üzlet elfogad, végezze el a kártyabeállítást.
