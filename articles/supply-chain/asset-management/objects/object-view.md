---
title: Eszköznézet
description: Ez a témakör az Eszközkezelés modul eszköznézetet ismerteti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0256cc86dc306c8addb37d2c8f335470b19177a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019404"
---
# <a name="asset-view"></a>Eszköznézet

[!include [banner](../../includes/banner.md)]

 

Ez a témakör az Eszközkezelés modul eszköznézetet ismerteti. Az **Eszköznézet** oldal az aktív eszközöket és a munkavégzési helyeket fastruktúrában jeleníti meg. Ezért könnyen áttekintést kaphat az eszközök és munkavégzési helyek kapcsolatairól. Ezenkívül részletes információkat is megtekinhet a munkavégzési helyszínekről, az eszközökről és a kapcsolódó anyagjegyzékről. Ezenkívül gyorsan áttekintheti az eszközhöz kapcsolódó aktív karbantartási kéréseket és munkrendeléseket.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Eszköznézet** lehetőséget.
2. A lapon megjelenő nézet megváltoztatásához jelöljön ki egy új értéket a **Nézet** mezőben.

    > [!NOTE]
    > Az **Eszköznézet** oldal megnyitásakor látható nézet az **Eszközkezelési paraméterek** oldal **Eszközök** lapjának **Nézet** mezőjében kiválasztott értéktől függ (**Eszközkezelés** \> **Beállítás** \> **Eszközkezelési paraméterek**).

A lap jobb oldalán a Gyorslapok a kijelölt nézet részleteit mutatják.

A fastruktúra felett megjelenő navigációs útvonal mutatja a fastruktúra aktuális kiválasztását. Ez a navigációs útvonal a következő formátumot használja:

Munkavégzési helyszín azonosítója / Munkavégzési helyszín azonosítja (ha egynél több munkavégzési helyszín létezik) \> Eszközazonosító / Eszközazonosító (ha egynél több eszköz van) – Cikkszám.

Ha a fanézetben kiválasztott egy eszközt, az **Aktív kérések** vagy az **Aktív munkarendelések** kiválasztásával megtekintheti az eszközhöz kapcsolódó karbantartási kéréseket vagy munkarendeléseket. A kapcsolódó nézet megnyitásához válassza a **Megnyitás** \> **Munkavégzési helyszín**, **Eszköz** vagy **Eszköz DBJ** pontot.

Az **Eszköz munkavégzési helyszínei** beállítás, amelyet a **Nézet** mezőből is kiválaszthat, bármely eszközkeresőben elérhető, ahol eszközt lehet választani. A fastruktúra megjelenik az **Eszköznézet** lapon, például ahol [létrehoz egy eszközt](../objects/create-an-object.md), létrehoz egy karbantartási kérést vagy egy munkarendelést.
