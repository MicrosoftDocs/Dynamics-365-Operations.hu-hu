---
title: A keresztárfolyam meghatározása
description: Ez a cikk a Microsoft Dynamics Pénzügy 365 rendszer keresztmértékeit tartalmazza.
author: abruer
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efb01948af2bcba9ca740e8bd0e12584cf021fce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889961"
---
# <a name="specify-the-cross-rate"></a>A keresztárfolyam meghatározása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a keresztárfolyamok célját, valamint azt, hogy hogyan adható meg a keresztárfolyam egy számlával történő kifizetéskor. Keresztárfolyam használata a következő feltételek alkalmazásakor: 
-   A kifizetési számlát egyenlít ki. 
-   A számlasor és a számlasor használja a különféle pénznemekben. 
-   Sem pénzneme nem az alapértelmezett pénznemben. 

A keresztárfolyam nem használatos a fizetési tranzakció devizaátváltásának kiszámítására a kifizetés könyvelési pénznemhez. Az árfolyamok beolvasására az árfolyamtáblákból azért kerül sor, hogy kiszámítsák a fizetési tranzakció pénznemének összegét és a fizetés könyvelési pénznemének összegét. 

Például a könyvelési pénznemben USD, számla pénzneme CAD, pedig a kifizetés pénznemében EUR. A keresztárfolyam segítségével fordításához CAD és euró közötti közvetlen átváltási árfolyam megadása, és nem kell lefordítani USD keresztül. Amikor kiválaszt egy számlát és egy elsődleges kifizetést, a számla sorához keresztárfolyamot adhat meg. A keresztárfolyam az ilyen tranzakciók pénznemeinek a kiegyenlítés napján érvényes átváltási árfolyama.

1.  Lépjen az alábbiak közül valamelyik lapra:
- **Kinnlevőségek > Közös > Vevők > Minden vevő** 
- **Kötelezettségek > Közös > Szállítók > Minden szállító** 
- **Beszerzés és forrás > Közös > Szállítók > Minden szállító**
2.  Válassza ki a vevőt vagy szállítót, amelynek nyitott tranzakcióit elszámolja. 
3.  Egy adott vevő esetében a **Minden vevő** listaoldalon lépjen ide: **Beszedés > Nyitott tranzakciók kiegyenlítése**. Egy adott szállító esetében a **Minden szállító** listaoldalon lépjen ide: **Számla > Nyitott tranzakciók kiegyenlítése**. 
4.  Válassza ki az elsődleges kifizetést jelentő tranzakciót, majd kattintson a **Kifizetés megjelölése** gombra. A **Megjelölés** oszlopban található jelölőnégyzet be lesz jelölve, és egy információs ikon jelenik meg az **Elsődleges kifizetés** oszlopban. 
5.  A **Keresztárfolyam** mezőbe írja be a számla és a kifizetés pénzneme közötti átváltási árfolyam szorzóját a kifizetés napján érvényes értékkel. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
