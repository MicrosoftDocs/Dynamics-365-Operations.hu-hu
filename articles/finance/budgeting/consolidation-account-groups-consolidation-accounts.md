---
title: Konszolidációsszámla-csoportok és további konszolidációs számlák
description: Ez a témakör konszolidációsszámla-csoportokról és további konszolidációs számlákról nyújt tájékoztatást, és elmagyarázza, hogyan történik ezek használata a Microsoft Dynamics 365 Finance rendszerben.
author: aprilolson
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 245b61c8cb85ab1282a921ac99b9ac7c2efbadc5
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189421"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Konszolidációsszámla-csoportok és további konszolidációs számlák

[!include [banner](../includes/banner.md)]

Ez a témakör konszolidációsszámla-csoportokról és további konszolidációs számlákról nyújt tájékoztatást, és elmagyarázza, hogyan történik ezek használata a Microsoft Dynamics 365 Finance rendszerben.

## <a name="consolidation-account-groups"></a>Konszolidációsszámla-csoportok

Konszolidációsszámla-csoportok segítségével számlacsoportokat hozhat létre, amelyeket adatok összesítéséhez használhat. Leggyakrabban a konszolidációsszámla-csoport egy kormányzati megbízáson alapuló számlatükröt jelent, vagy a vállalat központja által meghatározott számlákat rendel egy csoporthoz. A konszolidációsszámla-csoportok a **Konszolidáció** modul **Beállítások** területén találhatók. Amikor hozzáad egy új csoportot, adja meg a számlacsoport egyedi azonosítóját és egy nevet.

## <a name="additional-consolidation-accounts"></a>További konszolidációs számlák
További konszolidációs számlák segítségével egy már meglévő számlatükörben található számla egy konszolidációsszámla-csoporthoz rendelhető hozzá. Ezután meghatározhatja a konszolidációs számla értékét és nevét. 

További konszolidációs számlák találhatók a **Konszolidáció** modul **Beállítások** területén. Új konszolidációs számla létrehozásakor meg kell adnia a következő információkat:

-   **Fő számla** – ezt a mező egy keresés, amely az oldalon megadott számlatükrön alapuló összes fő számlát mutatja. Egy számla kijelölésekor a neve automatikusan bekerül a **Fő számla neve** mezőbe.
-   **Konszolidációsszámla-csoport** – e mező segítségével adja meg a csoportot, amelyhez hozzá kívánja rendelni a számlát. Ha a két különböző módon összegez, ugyanazt a mind a négy konszolidációsszámla-csoporthoz hozzá kell adnia.
-   **Konszolidációs számla** – a konszolidációs számla értékének megadása. Ez az érték nem feltétlenül egy a számlatükörből származó számla. Minden olyan érték lehet, amelyre szüksége van.
-   **Konszolidációs számla neve** – a számla nevének megadása, amely meg fog jelenni a lekérdezésekben és jelentésekben.
-   **SAT-szint** – ezzel a mezővel számlakivonatokat küldhet a mexikói adóhatóságnak. 

Amikor befejezte a konszolidációsszámla-csoportok és kiegészítő konszolidációs számlák létrehozását, kiválaszthatja a csoportot az online Konszolidálás folyamat során.


További információkért lásd: [Konszolidációs csoportok és további konszolidációs számlák létrehozása](../general-ledger/tasks/create-consolidation-groups.md) 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]