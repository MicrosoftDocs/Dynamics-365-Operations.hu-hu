---
title: "Degresszív értékcsökkenés"
description: "Ez a cikk az értékcsökkenés egyenleg csökkentő módszeréről nyújt tájékoztatást."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 29bc8cd02d98479197d7e5f5664b9859c03893b3
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="reduce-balance-depreciation"></a>Degresszív értékcsökkenés

[!include[banner](../includes/banner.md)]


Ez a cikk az értékcsökkenés egyenleg csökkentő módszeréről nyújt tájékoztatást.

Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és a Degresszív értéket választja a Mód mezőben az Értékcsökkenési profilok lapon, akkor az ehhez az értékcsökkenési profilhoz hozzárendelt tárgyi eszközök értékcsökkenése minden időszakban ugyanakkora százalékkal megy végbe.

A degresszív értékcsökkenés beállítása esetén az Értékcsökkenési profilok képernyő Általános gyorslapján rendelkezésre álló beállításokat is meg kell adni. Először válasszon egy évet az Értékcsökkenés éve mezőben. A választástól függően az Időszak gyakorisága mezőben különböző lehetőségek közül lehet választani, ahogy az az alábbiakban egy külön szakaszban részletesen le van írva. 

A Százalék mezőben meg kell adni az értékcsökkenési profil értékét. Ha a Teljes értékcsökkenés beállítást választja, akkor a program az utolsó értékcsökkenési időszakban a hátralevő értékcsökkenési alapot veszi, amely nagy összeg lehet. Bizonyos országokban/régiókban nem alkalmaznak lineáris értékcsökkenést alternatív módszerként. Alternatív értékcsökkenés olyankor lép fel, ha az alternatív értékcsökkenési módszer összege nagyobb, mint az elsődleges értékcsökkenési profil összege, akkor a rendszer az alternatív módszer összegét veszi értékcsökkenési összegnek. 

Mivel az eszköz értékcsökkenése a százalékos számítás alapján soha nem lesz teljes, ezért csak a Teljes értékcsökkenés beállítás alkalmazásával lehet elérni, hogy az eszköz értékcsökkenése teljes legyen.

## <a name="select-a-depreciation-year"></a>Az értékcsökkenési év kiválasztása
Kiválaszthatja a Naptár vagy Pénzügyi elemeket az Értékcsökkenési év mezőben az Értékcsökkenési profilok lapon. A kiválasztás függvényében változnak az Időszak gyakorisága mezőben elérhető beállítások. Az alapértelmezett beállítás a Naptár.

### <a name="calendar"></a>Naptár

A Naptár beállítás használata esetén a rendszer minden évben január elsején frissíti az értékcsökkenés alapját, amely jellemzően a nettó könyv szerinti érték csökkentve a maradványértékkel. A fejezet későbbi részében bemutatott degresszív értékcsökkenési példában az értékcsökkenés alapja a számítási oszlopban szereplő első szám. 

A Naptár lehetőség választása esetén a következő beállítások állnak rendelkezésre az Időszak gyakorisága mezőben, amelyek egész évben meghatározzák az értékcsökkenés feladási időpontját és összegét:

-   Évente: feladás december 31-én.
-   Havonta: felad egy havi összeget minden naptári hó végén.
-   Negyedévente: Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).
-   Félévente: féléves összeget ad fel minden naptári félév végén (június 30. és december 31.).
-   A Naponta lehetőséget választva minden nap feladható egy tranzakció a napi értékcsökkenés módszerrel számolt értékcsökkenés összegével.

Ha például az Évente beállítást választja, az éves értékcsökkenés csak egyszer, minden év december 31-én kerül feladásra. Ha a Havonta beállítást választja, a havi értékcsökkenés feladása havonta történik, az éves értékcsökkenési összeg egy-tizenkettedeként.

### <a name="fiscal"></a>Pénzügyi

Ha a Pénzügyi beállítást választja az Értékcsökkenés éve mezőben, akkor a lineáris értékcsökkenési módszert alkalmazza a rendszer. Ezt a pénzügyi év alapján számítja ki a rendszer, amelyet a Pénzügyi naptárak lapon állíthat be a Főkönyv lapon kiválasztott pénzügyi naptárhoz. Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik. Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet. Az értékcsökkenés minden egyes pénzügyi időszak végén módosul. A következő pénzügyi év hossza az új pénzügyi évnek a Pénzügyi naptárak lapon való létrehozásakor beállított pénzügyi időszakoktól függ.


Ha a Pénzügyi beállítást választja, az alábbi opciók lesznek elérhetőek az az Időszak gyakorisága mezőben:

-   Évente: az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján, egy összegként lesz feladva.
-   A Pénzügyi időszak a pénzügyi évre számított értékcsökkenés teljes összegét feladja, amelyet a Főkönyv oldalon kiválasztott pénzügyi évhez tartozó pénzügyi időszakokra összegyűjtött a rendszer, vagy egy tárgyi eszköz könyvéhez kiválasztott pénzügyi naptárra vonatkozóan.

## <a name="example-of-reducing-balance-depreciation"></a>Példa degresszív értékcsökkenésre

Tegyük fel, hogy a tárgyi eszköz beszerzési ára 11 000, a maradványértéke 1 000 és az értékcsökkenés százalékos tényezője 30. 

A Degresszív módszerrel az értékcsökkenés alapjának (nettó könyv szerinti érték csökkentve a maradványértékkel) a 30 százalékát számítja ki a rendszer az előző értékcsökkenési időszak végén. Az alábbi tábla bemutatja az első három év értékcsökkenését.

| Időszak | Az éves értékcsökkenési összeg számítása | Nettó könyv szerinti érték az év végén |
|--------|-------------------------------------------|---------------------------------------|
| 1. év | (11 000-1000) \* 30% = 3000           | (11 000 - 1000) - 3000 = 7000      |
| 2. év | (7000-1000) \* 30% = 1800            | (7000 -1800) = 5200                |
| 3. év | (5200-1000) \* 30% = 1260            | (5200 - 1260) = 3940               |

 
-






