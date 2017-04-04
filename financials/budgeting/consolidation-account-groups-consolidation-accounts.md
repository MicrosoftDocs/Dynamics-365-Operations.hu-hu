---
title: "Konszolidációs számla csoportok és további konszolidációs számlák"
description: "Ez a témakör tájékoztatást nyújt konszolidációs számlák csoportjainak és további konszolidációs számlák, és elmagyarázza, hogy azok hogyan használhatók a Microsoft Dynamics 365 műveletekhez."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Konszolidációs számla csoportok és további konszolidációs számlák

Ez a témakör tájékoztatást nyújt konszolidációs számlák csoportjainak és további konszolidációs számlák, és elmagyarázza, hogy azok hogyan használhatók a Microsoft Dynamics 365 műveletekhez.

<a name="consolidation-account-groups"></a>Konszolidációsszámla-csoportok
----------------------------

Konszolidációsszámla-csoportok segítségével hozzon létre csoportokat az adatok összesítésénél használni kívánt számlákat. Leggyakrabban a konszolidáció számlacsoport kormányzati megbízáson alapuló Számlatükör jelenti, vagy fiókokat rendel egy csoportot, amely definiálja a vállalat székhelyével. Konszolidációs számla csoportok is megtalálhatja a **a telepítő** területén a **konszolidációs** modul. Amikor hozzáad egy új csoportot, adja meg egy egyedi azonosítót a csoport és egy nevet.

## <a name="additional-consolidation-accounts"></a>További konszolidációs számlák
További konszolidációs számlák lehetővé teszik egy már meglévő számlatükörbe fiók hozzárendelése egy konszolidációsszámla-csoportot. Meghatározhatja a konszolidációs számla értékének és nevét. 

További konszolidációs számlákat is megtalálhatja a **a telepítő** területén a **konszolidáció** modul. Egy új konszolidációs számla létrehozásakor meg kell adnia a következő információkat:

-   **Fő számla** – ezt a mezőt, amely tartalmazza a fő számlák a számlatükörben kijelölt lapon alapuló keresés. Egy számla kijelölésekor a neve automatikusan bekerül a **fő fióknév** mezőben.
-   **Konszolidációs számla csoport** – a mező segítségével adja meg a fiók hozzárendelése a csoporthoz. Ha a két különböző módon, hozzá kell adnia minden négy konszolidáció számlacsoportok ugyanazt a fiókot.
-   **Konszolidációs számla** – a konszolidációs számla értékének megadása. Ez az érték nem kell egy számlát a Számlatükör. Minden olyan érték, amely szükséges lehet.
-   **Konszolidációs számla neve** – adja meg a fiók nevét, a lekérdezésekben és jelentésekben megjeleníteni kívánt.
-   **SAT szint** – ezzel a mezővel számlakivonatokat a Mexikói adóhatóságnak jelenteni. 

Ha befejezte a konszolidációsszámla-csoportok és további konszolidációs számlák létrehozása, akkor jelölje ki a csoportot a Konszolidál online folyamat.



