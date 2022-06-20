---
title: Fogyasztói árindex ütemezése
description: Ez a cikk bemutatja, hogy hogyan lehet létrehozni a felhasználói árindex (CPI) interneten keresztüli ütemezését, amely segít megállapítani az előfizetéses számlázásban az eszkalációs díjat.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f08b79ee00baab3713d9ccc24a7595b1de7a7768
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904873"
---
# <a name="consumer-price-index-schedule"></a>Fogyasztói árindex ütemezése

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet a felhasználói árindex-ütemezéseket létrehozni, törölni, áttekinteni és feldolgozni. A CPI-ütemezés a számlázási ütemezés soraiként megadott fogyasztási javak és szolgáltatások árainak meghatározására használható. A CPI-ütemezés felhasználható a számlázási ütemezésben az eszkaláció és az engedmény árképzése során, illetve manuálisan is feldolgozható a számlázási ütemezések számlázási összegének frissítéséhez. A CPI-ütemezések manuálisan is beírhatók, illetve a CPI-ütemezés összetett entitásával is importálni lehet őket.

A CPI-ütemezések hozzáadásához kövesse ezeket a lépéseket.

1. Válassza az **Új lehetőséget a Felhasználói árindex ütemezése** **lapon**.
2. A Felhasználói árindex **ütemezése** mezőbe írjon be egy egyedi nevet.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. Válassza a **Hozzáadás lehetőséget a Felhasználói árindex ütemezése** lapon **·**.
5. Adja meg **a felhasználóiár-index dátummezőben** azt a dátumot, amikor az új CPI-ütemezés aktívvá válik.
6. A Felhasználói árindex **ütemezése** mezőbe írja be a 2. lépésben megadott nevet.
7. Válassza a **Mentés** lehetőséget.

A CPI-ütemezési dátumok törléséhez kövesse az alábbi lépéseket.

1. Jelölje ki **a törölni kívánt sorokat a felhasználóiár-index** ütemezési lapján, majd válassza az Eltávolítás **lehetőséget**.
2. Ha a teljes CPI-ütemezést törölni szeretné, a munkaablakban válassza a Törlés **lehetőséget**. A kiválasztott CPI-ütemezés nem törölhető, ha számlázási ütemezéshez van társítva.
3. A munkaablakban válassza **a Folyamat** lehetőséget a kiválasztott CPI-ütemezést tartalmazó számlázási ütemezések frissítéséhez. A számlázási ütemezésben használt árak frissítésére a legutóbbi CPI-dátumok és ütemezési összegek lesznek használva.
4. A felhasználóiár-index folyamat gyorscsoportján ellenőrizze a frissített számlázási ütemezés számát, a cikkszámot, **·** **a számlázás kezdő** dátumát, **a számlázás záró** dátumát, **az eszkaláció** **dátumát és az eszkaláció gyakoriságát jelző mezőket.** **·** **·**

A CPI-ütemezések beállítása után felhasználhatók a számlázási ütemezések eszkalációs és engedményes árának változásaihoz.

## <a name="cpi-calculation"></a>CPI-számítás

Ilyen példákban az időszak 2020. január 1-től 2022. december 31-ig tart. Az alap CPI-árfolyam (a szerződés indításakor a CPI-érték) 105,65. 2021. január 1-jén az aktuális CPI 110,5. 2022. január 1-jén az aktuális CPI 114,25. A kezdeti összeg már $1,000.

**1. példa**

Az Ismétlődő szerződés **számlázási paraméterei** oldalon a felhasználói árindex-számítás **·** **mezője az Alap felhasználói árindex beállítását adja meg**.

2021. január 1-jén az első eszkalációs összeg számítása a kezdeti összeg alapján történik:

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

2022. január 1-jén az eszkalációs összeg számítása a következőképpen történik:

1 000 + (114,25 – 105,65) &divide; 105,65 &times; 1 000 = 1 081,40

**2. példa**

Az Ismétlődő szerződés **számlázási paraméterei** oldalon a Felhasználói **árindex** **számítása mezőt korábbi felhasználói árindexre állíthatja**.

2021. január 1-jén az első eszkalációs összeg számítása a kezdeti összeg alapján történik:

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

2022. január 1-jén az eszkalációs összeg számítása a következőképpen történik az első eszkalációs összeg alapján:

1 045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1 045,91 = 1 081,40

> [!NOTE]
> Az eszkalációs folyamat mindig a legutóbbi CPI-értéket használja, az index dátumától függetlenül. Ha például az eszkaláció szeptemberben van, de a legutóbbi CPI-érték júliusra, a rendszer a júliusi indexet használja. A szeptemberi index bevitele után nem készül korrekció.

## <a name="prorated-escalation"></a>Nem minősített eszkaláció

Ha az eszkaláció a számlázási időszak közepére fordul elő, az összeg újraszámít. A számlázási időszak például 2020. augusztus 1-től 2021. július 31-ig tart. A CPI 2019. szeptember 1-ján a CPI értéke 244. Ez a CPI-érték 2020. szeptember 1-ján 250. Ha az előző díj 1000, az időszak számlázási összegének kiszámítására a következő képletek használhatók:

* *CPI-változások* = (250 – 244) &divide; 244 = 2,459%
* *Jelenlegi árfolyam* = 1 000 &times; 2,459% = 1 024,59
* *Napok száma az aktuális* árfolyamon = 2021. július 31. – 2020. szeptember 1. = 334
* *Előző árfolyam* = 1000
* *Napok száma az előző* árfolyamon = 2020. augusztus 31. – 2020. augusztus 1. = 31
* *A számlázási időszak napjainak* száma összesen = 2021. július 31. – 2020. augusztus 1. + 1 = 365
* *Számlázási összeg* ehhez az időszakhoz = (1 000 &times; 31 &divide; 365) + (1 024,59 &times; 334 &divide; 365) = 1 022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Eszkaláció, amely a CPI-t és a százalékot használja

Az eszkalációkat a CPI használatával lehet. A CPI és a 3 százalékos eszkaláció 2020. január 1-én kezdődik, és éves gyakorisággal indul.

- A 2019. január 1-jén 2020. december 31-ig kiszámlázott összeg 4000.
- Az eszkalált számlázási időszak 2020. január 1-től 2020. december 31-ig tart.
- A CPI 2018. december 1-i dátumán a CPI értéke 205,3. A CPI 2019. december 1-i dátumán a CPI értéke 219,6.

Ha az előző díj 4000, akkor ennek az időszaknak a számlázási összege a következőképpen számítható ki:

- *CPI-változások* = (219,6 – 205,3) &divide; 205,3 = 6,965%
- *Aktuális árfolyam* = (4000 &times; 6,965%) – 4000 = 278,60
- *Százalékos változás* = (4000 &times; 1,03) – 4000 = 120
- *Számlázási összeg* = 4 000 + 278,6 + 120 = 4398,6
