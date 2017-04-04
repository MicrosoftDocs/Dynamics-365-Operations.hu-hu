---
title: "Vonalkódmaszkok beállítása"
description: "Ez a témakör leírja, hogyan állíthatja be a vonalkódmaszk-karakterek, vonalkódmaszkok, és hozzárendelése a vonalkód, vonalkód maszkok."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Vonalkódmaszkok beállítása

Ez a témakör leírja, hogyan állíthatja be a vonalkódmaszk-karakterek, vonalkódmaszkok, és hozzárendelése a vonalkód, vonalkód maszkok.

<a name="set-up-bar-code-mask-characters"></a>Vonalkódmaszk-karakterek beállítása
-------------------------------

A vonalkódmaszkok vonalkódok létrehozása és az értékesítés (POS) pontba beolvasott vonalkódok gyors azonosítását használják. Maszkok állnak, amelyek helyőrzőként a létrehozandó vonalkódok formátumát jelző karakter. Vonalkódmaszk konfigurálásához állítsa be a vonalkódmaszk-karaktereket kell. Ugrás a **kereskedelmi és kereskedelmi**&gt;**Inventory management**&gt;**vonalkódok és címkék**&gt;**maszk karakterek**. Kattintson a **új** vonalkódmaszk-karakterek létrehozása. Vonalkódmaszk-karakterek hozhatók létre a következő vonalkód adatok jelöléséhez.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | Helyőrző a termékazonosítót.                                                                                     |
| **Any number**       | Adjon meg egy számot, amely lesz kemény kódolva a vonalkódok segítségével.                                                  |
| **Check digit**      | Azt jelzi, hogy a vonalkód formátum a vonalkódmaszk segítségével egy ellenőrző számjegy megerősíti a vonalkód érvényességét. |
| **Size digit**       | A vonalkód méretét tartalmazó termékváltozat létrehozott méretét jelzi.                                 |
| **Color digit**      | Színre színt tartalmazó termékváltozat létre vonalkódokat jelzi.                               |
| **Style digit**      | Azt jelzi, hogy a stílust tartalmazó termékváltozat létre vonalkódokat stílus.                             |
| **EAN license code** | EAN licenckódok kiállított EAN licenc helyőrzője.                                                       |
| **Ár**            | Jelzi, hogy ár ár beépített vonalkód.                                                                   |
| **Quantity**         | Azt jelzi, hogy a vonalkódokat beágyazott mennyiség véletlenszerű tömeg mennyiség.                                                |
| **Employee**         | Vonalkód szegmense vonalkód POS bejelentkezési alkalmazott azonosító számát jelzi.                                  |
| **Customer**         | Ügyfélszegmens Azonosítóját jelzi.                                                                                  |
| **Adatbevitel**       | *Még nincs megvalósítva.*                                                                                          |
| **Discount code**    | Jelzi, hogy a vonalkód engedmény hozzáadása az értékesítési tranzakció pont használt engedmény kódja             |
| **Ajándékutalvány**        | Ajándékutalványok kibocsátásakor vagy a kifizető ajándékutalvány jelzi.                                               |
| **Loyalty card**     | A hűséges vevők hozzáadása a tranzakcióhoz, és használható, ha a kifizető hűséges.                             |

## <a name="define-bar-code-masks"></a>A vonalkódmaszkok meghatározása
Után a szükséges vonalkódmaszkok vonalkódmaszk-karakterek vannak megadva, Ugrás **kereskedelmi és kereskedelmi**&gt;**Inventory management**&gt;**vonalkódok és címkék**&gt;**vonalkód a munkalapmaszk-beállítás**. Ezen a lapon határozhatja meg a korábban megadott karakterek használatára vonalkódmaszkok. Vonalkód maszkok vonalkódok létrehozásához használt, valamint azt, hogy ezek segítenek azonosítani a POS beolvasott vonalkódok.

1.  Kattintson a **új** hozhat létre egy új vonalkódmaszkot.
2.  Írja be az értékeket a **Maszkazonosító** és **leírás** mezők, és válassza ki a vonalkódtípus maszk a **típus** mezőben.
3.  A a **általános** szakaszban, jelölje be az értéket a **Vonalkódszabvány** mezőben, és adja meg a vonalkód előtagot, ha szükséges.
4.  A a **Vonalkódmaszkszegmens** szakaszban, hozzá kell létrehozni a vonalkód vonalkód szegmensek használandó.

Például, hozzon létre vonalkódmaszkot Maszkazonosító "Termék", akkor volna tegye a következőket:

1.  Hozzon létre egy új vonalkódmaszkot, és válassza ki a "Termék" típusú.
2.  Válassza ki a vonalkód szabvány, például "kód 39".
3.  Adja meg könnyen azonosítani a vonalkód használandó előtag. Például "22."
4.  A maszk szegmens hozzáadása. A "Termék" maszk szegmens be lesz jelölve.
5.  A termék szegmens, például '10' hosszú biztosítanak. Hossza meg kell egyeznie az üzlet általánosan használt termékazonosító hosszát. A maszk jelenik meg az előnézet a **általános** a szakasz **maszk**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>A vonalkódmaszkok vonalkódok rendelni
A vonalkódok maszkok kell rendelni a vonalkódok előtt be kell állítani. Az előző példában a továbbra is a vonalkódhoz rendelése a vonalkódban, tegye a következőket:

1.  Ugrás a **szervezet felügyelete**&gt;**a telepítő**&gt;**a vonalkódok**. Kattintson a **új** egy új vonalkód létrehozásához.
2.  Írja be az értékeket a **vonalkód****a telepítő** és ** telepítő ** mezőket.
3.  A a **általános** ebben a szakaszban a **vonalkódtípus** mezőben, válassza a "Kód 39". A a **maszk****ID** mezőben, jelölje ki a korábban létrehozott "Termék" maszk.
4.  A **méretét**, adja meg a "12".
5.  Click **Save**.

A vonalkódban már termékek vonalkódok létrehozásához használható. Példák a fenti lépések vonalkódmaszkok termékek létrehozása, de azok is bemutatják, hogyan lehet létrehozni bármely más támogatott vonalkód típusú vonalkódmaszkok. Vonalkódmaszkok, típusa és hossza az adott környezetben való használatra kell beállítani.


