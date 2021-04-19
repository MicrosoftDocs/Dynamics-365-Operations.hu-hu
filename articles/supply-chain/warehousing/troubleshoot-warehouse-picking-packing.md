---
title: Kitárolás és csomagolás – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben kitárol és csomagol a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1a54fa9dc21fb1691d74905a1215f4dfea31f136
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828130"
---
# <a name="troubleshoot-picking-and-packing"></a>Kitárolás és csomagolás – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben kitárol és csomagol a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>A következő hibaüzenet jelenik meg: „A dimenzió helye nem hagyható üresen, ha a dimenzió sorozatszáma be van állítva.”

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet akkor jelenik meg, ha egy sorozatszámos cikkhez olyan raktárat hoz létre, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt.

### <a name="issue-resolution"></a>Probléma megoldása

Az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában. A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban. Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>A következő hibaüzenet jelenik meg: „Érvénytelen azonosítótábla”.

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet jelenik meg a Raktárkezelés mobilalkalmazásban, amikor beolvas egy azonosítót.

### <a name="issue-resolution"></a>Probléma megoldása

Győződjön meg arról, hogy az azonosítótábla-azonosító szerepel az azonosítótáblák táblázatában, és hogy az azonosítótáblán lévő cikkek és mennyiségek elérhetők (más szóval nincsenek zárolva).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>A következő hibaüzenet jelenik meg: „A „Szállítmány súlya” (=-%1) mező csak pozitív számokat tartalmazhat. A frissítés meg lett szakítva.”

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet akkor jelenik meg, ha a munka csomagolási helyekről átmeneti helyekre, illetve az átmeneti helyekről a dokkolóhelyekre történő feldolgozáskor van egy nyitott munka.

### <a name="issue-resolution"></a>Probléma megoldása

A probléma megoldásához menjen a **Rendszerfelügyelet \> Időszakos feladatok \> Adatbázis \> Konzisztencia ellenőrzése** lehetőségre, majd futtassa a **Raktári rakománysúly konzisztencia ellenőrzése** folyamatot.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>A következő hibaüzenet jelenik meg: „A mennyiség nem érvényes az %1 egységre”.

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet akkor jelenik meg, amikor több köteg között próbál *kitárolásokat szétosztani*.

### <a name="issue-resolution"></a>Probléma megoldása

A raktári dolgozónak a *Rövid kitárolási* folyamatot kell használnia a Raktárkezelés mobilalkalmazásban. Ha több köteget próbál kiválasztani ugyanarról a helyről, használhatja az alkalmazásban a **Teljes** lehetőséget is.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>Nem tudom áthelyezni a készletet olyan helyre, amely azonosítótábla-vezérelt.

### <a name="issue-description"></a>Probléma leírása

A kitárolt mennyiségek nem csökkenthetők a rakományon.

### <a name="issue-resolution"></a>Probléma megoldása

A régebbi verziókban a kitárolt mennyiségek nem csökkenthetők a rakományon. Most azonban már visszatárolhatja az azonosítótábla-vezérelt helyre. A kitárolt mennyiség csökkentése lapon meg kell adnia a **Hely** értéket és a rakomány sor **Azonosítótábla** értékét a **Csökkentett kitárolt mennyiség** oldalon.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>Nyomtathatok szállítólevelet vagy csomagolási tartalmat raktáronként?

### <a name="issue-description"></a>Probléma leírása

Szállítólevelet vagy csomagolási tartalmat szeretne nyomtatni raktár vagy hely szerint a **Munkavizsgálati sablonsor frissítés** lapon.

### <a name="issue-resolution"></a>Probléma megoldása

Ha a nyomtatáskezelési beállításokkal nyomtat egy dokumentumot, korlátozza a hatókört (hely/raktár) a Nyomtatáskezelés segítségével, ne a **Nyomtatási beállítások szerkesztése** lehetőséget használja a **Munkanaplózási sablonsor frissítési** lapon.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Nem tudom törölni a szállítólevelet, miután ki lett adva egy értékesítési rendelésből.

### <a name="issue-description"></a>Probléma leírása

Ha a WMS-hez engedélyezve vannak a kitárolási és szállítási folyamatok, akkor nem vonhatja vissza a szállítólevelet, miután azt az értékesítési rendelésből kiadta.

### <a name="issue-resolution"></a>Probléma megoldása

A WMS-hez engedélyezett cikkek könyvelt szállítólevélének helyesbítéséhez a könyvelést a rakományból kell kiadnia, nem pedig közvetlenül a rendelésből. A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. A raktárkezelési folyamatokon keresztül kitárolt és szállított értékesítési rendelés általában a rakományból vagy a szállítmányból és magából az értékesítési rendelésbizonylatból frissíthető. Ha azonban az értékesítési rendelés bizonylatából frissíti az értékesítési rendelést, a csomagjegyzék sztornírozása még mindig nem végezhető el a rakományból vagy értékesítési rendelésből. Ezért azt javasoljuk, hogy használja a szállítólevél kiadást a rakományból. Ebben az esetben a betöltésből elvégzendő sztornírozás engedélyezve lesz.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>A következő hibaüzenet jelenik meg: „A fürthöz nincs elegendő munka.”

### <a name="issue-description"></a>Probléma leírása

A *Rendszer által irányított fürtkitárolás* folyamat használatakor, ha olyan fürtprofilt állít be, amelyben például 10 pozíció tárolható ki, a folyamat a tervek szerint működik, ha elegendő munka áll rendelkezésre a 10 pozíció kitárolásához. Ha azonban csak nyolc pozíciót lehet kitárolni, akkor ez a hibaüzenet jelenik meg, mert nincs elég munka egy fürthöz.

### <a name="issue-resolution"></a>Probléma megoldása

A probléma megoldásához szerkesztse a fürtprofilt, és állítsa a **Pozíciók aktiválása** lehetőséget *Nem* értékre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]