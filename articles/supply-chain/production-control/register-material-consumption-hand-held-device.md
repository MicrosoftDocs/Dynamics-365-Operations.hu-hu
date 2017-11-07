---
title: "Anyagfelhasználás regisztrálása mobileszköz segítségével"
description: "Ez a témakör olyan munkafolyamatot ír le, amely lehetővé teszi a nyersanyag-felhasználás regisztrálását a termelésben egy kézi eszköz használatával."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f948b8f1d846a009afe59e39ff3772d4d1fed9bf
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="register-material-consumption-using-a-mobile-device"></a>Anyagfelhasználás regisztrálása mobileszköz segítségével
Ez a témakör olyan munkafolyamatot ír le, amely lehetővé teszi a nyersanyag-felhasználás regisztrálását a termelésben egy kézi eszköz használatával.

<a name="introduction"></a>Bevezetés
------------

A munkafolyamat akkor releváns, ha az anyag nyomon követhetősége szigorú követelmény. Ebben az esetben az anyagok nyomonkövethetőségének megőrzése érdekében jelenteni kell a fogyasztás pontos időtartamát és mennyiségét. Ez a folyamat ellentétben áll az előzetes vagy utólagos kiürítési műveletekkel, ahol eltolás van a regisztrálás időpontja és a tényleges felhasználás időpontja között. Ez a magyarázata annak, hogy miért nem használható az automatikus felhasználási stratégia bizonyos anyagok nyomonkövethetőségi követelményeire. Nézzünk egy egyszerű forgatókönyvet, amely azt ismerteti, hogyan állítsunk be úgy egy munkafolyamat, hogy lehetővé tegyük a nyersanyag-felhasználás termelés során történő regisztrálását egy kézi eszközzel. [![munkafolyamat beállítása nyersanyag-felhasználás kézi eszközzel történő rögzítéséhez](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Forgatókönyv részletei

Egy folyamatos gyártási folyamat (5) az RM-100 köteg szerint nyilvántartott nyersanyagot használja fel. Az anyag a Bulk-001 (1) helyen aktuálisan megtalálható a PL-1 azonosítótáblán két köteggel (B1 és B2), mindkettő mennyisége 100 kg. A raktári munkát (2) kiadják és feldolgozzák az RM-100 esetében, a Bulk-001-ból az anyagot kitárolják a PIL-01 termelési bemeneti helyre (3), amely nem azonosítótáblás szabályozásúként van definiálva van. A gépkezelő leméri az anyagot a termelési bemeneti helyről (3), és regisztrálja a tömeget és a ténylegesen felhasznált kötegszámot (4). A termelési bemeneti helyről az anyag egy részét meghatározott időközönként manuálisan adják hozzá a termelési folyamathoz. Amikor a gépkezelő anyagot ad hozzá, az anyagot mérlegen le kell mérni, valamint regisztrálni kell a kötegszámot.

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a>Állítsa be a munkafolyamatot a felhasználás kézi eszközzel történő regisztrálásához
Hozzon létre készterméket (FG-100) olyan anyagjegyzékkel, amely az RM-100 köteg szerint nyilvántartott nyersanyagot tartalmazza. Adjon hozzá két RM-100 köteget (B1 és B2) 100-as mennyiségben a helyhez. Bulk-001 az azonosítótáblán: PL-1. Az anyagjegyzék RM-100 anyagjegyzéksorában levő kiürítési elv értéke **Kézi**. Állítsa a termelés alapértelmezett bemeneti helyét PIL-01 értékre. Ezt úgy teheti meg, ha ezt a helyet választja alapértelmezett termelési bemeneti helynek az 51-es raktárban.

1.  Új mobileszköz-menüpont létrehozása: 

-    **Menüpont neve** – Anyagfelhasználás regisztrálása. 
-    **Beosztás** – Anyagfelhasználás regisztrálása. 
-    **Mód** – Közvetett. 
-    **Tevékenységkód** – Anyagfelhasználás regisztrálása.

2.  Adja hozzá a menüelemet a **Production Mobile** mobileszközmenühöz.
3.  Termelési rendelés létrehozása a késztermékhez: 

-    **Cikkszám** – FG-100 
-    **Telephely** – 5 
-    **Raktár** – 51 
-    **Mennyiség** – 150

A termelési rendelés **Becsült** és **Engedélyezett** értékeket kap, és létrejön a raktárkezelési munka.

4.  Hajtsa végre a munkát a kézi eszköz nyersanyag-kitároláshoz használt munkafolyamatával.

Ez az anyagot az ömlesztett tárolóhelyről a PIL-01 termelési bemeneti helyre viszi. A munka befejezése után az anyag állapota **Kitárolás a termelési bemeneti helyén** lesz. Az állapot a munka feldolgozása után **Kitárolva** vagy **Foglalt tényleges** lehet. Ez a **Kiadás állapota a raktár képernyőre történő helyezés után** paraméterrel van beállítva.

5.  Indítsa el a termelési rendelést az ügyfélből vagy a kézi eszközről a **Termelés indítása** menüpont használatával.

A termelési rendelés elindítása után regisztrálhatja a nyersanyag-felhasználását a munkafolyamat segítségével a kézi eszközön. Kezdjük azzal, hogy a B1 köteg-hez 25 kg felhasználást regisztrálunk.

6.  Válassza ki az **Anyag regisztrálása** **Felhasználás** menüelemet a kézi eszközhöz, és írja be a következő adatokat: 

-    A termelési rendelés száma. 
-    Az anyagfelhasználás helye, ebben az esetben: PIL-01. 
-    Cikkszám: RM-100. 
-    Kötegszám: B1. 
-    Mennyiség: 25.

7.  Válassza ki az **OK** lehetőséget.

Vegye figyelembe, hogy a kijelzőn megjelenik „A naplósor létrehozva” üzenet. A termelési rendelésen van egy, az RM-100 cikkszámhoz és a B1 kötegszámhoz tartozó **Termelési kitárolási lista** típusú üres napló. 

Választhat, hogy folytatja-e a regisztrálást, például a B2 kötegszám esetében, és ahányszor az **OK** lehetőséget választja, a rendszer új naplósort ad hozzá a nyitott naplóhoz. 

A regisztrálás befejezése után válassza a **Kész** lehetőséget a napló feladásához és a munkafolyamat befejezéséhez.

### <a name="additional-comments"></a>További megjegyzések 

-   Ha a felhasználó megszakítja a munkafolyamatot egy naplósor létrehozása után, a napló fel nem adott állapotban van, de ha a felhasználó egy későbbi időpontban ezt a munkafolyamatot használja ugyanahhoz a termelési rendeléshez, a rendszer a sorokat a nyitott naplóhoz adja hozzá, nem pedig egy új naplóhoz.
-   Az új munkafolyamat a sorozatszámok bejegyzését is támogatja.
-   Csak olyan cikkszámot lehet regisztrálni, amely az anyagjegyzékben vagy a kiválasztott termelési rendelés vagy kötegrendelés képletében meg van határozva.
-   Az anyag túlfogyasztása engedélyezett. Például ha a becsült mennyiségű felhasználandó anyagmennyiség 100 kg, akkor a túlfogyasztás mennyisége például 105 kg lehet.



