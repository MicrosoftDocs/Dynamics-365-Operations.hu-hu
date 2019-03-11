---
title: Beszerzési szerződés létrehozása
description: Ez az eljárás végigvezeti a beszerzési szerződés létrehozásán.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b317f0a0fc8f198bad9501f325557ac2a4796989
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "338613"
---
# <a name="create-a-purchase-agreement"></a>Beszerzési szerződés létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás végigvezeti a beszerzési szerződés létrehozásán. Ez általában egy beszerzési vezető által történik. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. A kezdés előtt létre kell hozni a beszerzési szerződés osztályozásait. Miután létrehozta a megállapodást, használhatja, amikor létrehoz egy beszerzési rendelést, és ez bemásolja a beszerzési szerződés feltételeit a megállapodás által érintett rendelés fejlécébe és soraiba.


## <a name="create-a-new-purchase-agreement"></a>Új beszerzési szerződés létrehozása
1. Ugorjon a Beszerzés és vásárlás > Beszerzési szerződések > Beseszerzési szerződések gombra.
2. Kattintson az Új lehetőségre.
3. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Beszerzési szerződés osztályozása mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Bontsa ki az Általános szakaszt.
10. Adjon meg egy dátumot a Lejárati dátum mezőben.
    * Ez a lejárati dátum lesz az alapértelmezés az összes kötelezettségvállalási sorban, és meghatározza, mennyi ideig érvényesek a kötelezettségek.  
11. A Dokumentum címe mezőbe írja be a beszerzési szerződés nevét.
    * Hagyja az Alapértelmezett kötelezettségvállalás mezőt Termékmennyiségi kötelezettség értéken (vagy módosítsa erre, ha nem ez az értéke).  
    * Az alapértelmezett kötelezettségvállalási érték határozza meg a megállapodási sorokban látható opciókat. Ha új kötelezettségtípusra van szüksége a megállapodási sorok létrehozásakor, módosítsa az alapértelmezett kötelezettséget a fejlécben.  A kötelezettségvállalásoknak 4 típusa van: Termékmennyiségi kötelezettség – egy adott mennyiségű termékre; Termék értékére vonatkozó kötelezettség – termékösszeg adott pénznemben; Termék kategóriaértékére vonatkozó kötelezettség – egy beszerzési kategóriában lévő konkrét összeg devizában, ahol az összeg katalóguscikkre vagy a katalóguson kívüli cikkre vonatkozhat; Értékre vonatkozó kötelezettség – adott pénznemben lévő összegre, amely bármely termékre vagy beszerzési kategóriára vonatkozhat.  
12. Kattintson az OK gombra.

## <a name="add-a-commitment"></a>Kötelezettség hozzáadása
1. Kattintson az Új sor hozzáadása lehetőségre.
2. A listában jelölje meg a kiválasztott sort.
3. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Jelölje ki a terméket, amelyhez hozzá szeretné adni a kötelezettségvállalást.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Adjon meg egy számot a Mennyiség mezőben.
    * Ez az a teljes mennyiség, amelyeket a megállapodás szerint beszerez a szállítótól.  
7. Adjon meg egy számot az Egységár mezőben.
8. Bontsa ki a Soradatok szakaszt.
9. Állítsa a Maximális kényszerítése opciót Igen-re.
    * A Maximum betartatása beállítás korlátozza a kötelezettségvállalás használatát. Csak a Mennyiség mezőben megadott mennyiséget vásárolhatja meg az adott sorhoz.  
10. Csukja össze a Soradatok szakaszt.

## <a name="add-header-conditions"></a>Fejlécben megadott feltételek hozzáadása
1. A Művelet ablaktáblában kattintson a Beállítások elemre.
2. Kattintson a Nézetváltás elemre.
3. Kattintson a Fejlécnézet gombra.
4. Bontsa ki a Feltételek szakaszt.
5. A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Alapértelmezés szerint a szállítói számla fizetési feltételei láthatók itt.       
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Kiszállítási mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. A Szállítási feltételek mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="confirm-and-activate-the-agreement"></a>Erősítse meg és aktiválja a megállapodást
1. A Művelet panelen kattintson a Beszerzési szerződés elemre.
2. Kattintson a Megerősítés gombra.
    * Állítsa a Szerződés megjelölése érvényesként beállítást Igen értékre.  
3. Kattintson az OK gombra.
4. A Művelet panelen kattintson a Beszerzési szerződés elemre.
5. Kattintson a Beszerzési szerződés-visszaigazolásokra.
    * Az Előnézet/nyomtatás beállítás lehetővé teszi a beszerzési szerződéshez dokumentum létrehozását, amelyet kinyomtathat vagy elküldhet a szállítónak. Ha később frissítési a szerződést, és ismételten megerősíti, mindkét verzió megjelenik itt.  
6. Zárja be a lapot.

