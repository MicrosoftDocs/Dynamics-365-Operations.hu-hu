---
title: Konszolidációs csoportok és további konszolidációs számlák
description: Ez a cikk a konszolidációsszámla-csoportokkal és a további konszolidációs számlákkal kapcsolatban tartalmaz tájékoztatást, és bemutatja azok alkalmazását.
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9e66190fe0bab24545bf19eba59facded63ee197
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882020"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Konszolidációs csoportok és további konszolidációs számlák

[!include [banner](../includes/banner.md)]

Ez a cikk a konszolidációsszámla-csoportokkal és a további konszolidációs számlákkal kapcsolatban tartalmaz tájékoztatást, és bemutatja azok alkalmazását.

## <a name="consolidation-account-groups"></a>Konszolidációsszámla-csoportok

Konszolidációsszámla-csoportok segítségével számlacsoportokat hozhat létre, amelyeket adatok összesítéséhez használhat. A konszolidációsszámla-csoportok jellemzően egy kormányzati felhatalmazáson áteső számlatükret képviselnek. A konszolidációsszámla-csoportok olyan csoportokhoz is leképezheti a számlákat, amelyet a vállalat központi vállalata határoz meg. A konszolidációsszámla-csoportok a **Konszolidáció** modul **Beállítások** területén találhatók. Új csoport hozzáadásakor meg kell adnia a számlacsoport egyedi azonosítóját és nevét.

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
