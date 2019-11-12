---
title: Eszköz mértékei
description: A témakör bemutatja, hogyan lehet eszközmérték típusokat létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bc6b9e944a7ecf6b769a8e3c2f9b1fbafaa60734
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626108"
---
# <a name="counters"></a>Számlálók

[!include [banner](../../includes/banner.md)]

A témakör bemutatja, hogyan lehet számláló típusokat létrehozni az Eszközkezelés modulban. Az számlálótípusokkal lehet mérni a számlálókat lehet regisztrálni eszközökön, például a termelési órák száma vagy a tárgyi eszközön termelt mennyiség tekintetében. Az eszköztípusok az számlálótípusokhoz kapcsolódnak. Ez azt jelenti, hogy egy eszköz esetében csak akkor használható egy számláló, ha az eszköz típusánál be van állítva a számláló.

Az eszközökre vonatkozó számlálóregisztrációk előtt létre kell hoznia a **Számlálókban**használni kívánt számlálótípusokat. Ezután az eszközökre vonatkozó számlálóregisztrációkat kell létrehoznia a **Számlálók**helyen. 

Az számlálók a karbantartási tervekben használhatók. Egy karbantartási terv sora lehet „Számláló” típusú például, amely a termelési órák számához vagy a termelt mennyiséggel kapcsolatos. 

Az számláló regisztrálása manuálisan vagy automatikusan történhet, a termelési órák vagy a termelt mennyiségek alapján. Egy számlálót úgy is be lehet állítani, hogy a három frissítési mód egyikét használja (a **Frissítés** mezőben választható ki a **Számlálók** alatt):
  
- Manuális – manuálisan kell regisztrálni az számlálóértékeket.  
- Termelési órák – a számláló automatikusan frissül a termelési órák száma alapján.  
- Termelt mennyiség– a számláló automatikusan frissül a termelt mennyiség alapján.  

>[!NOTE]
>Ha a termelt mennyiséget használja, az *összes* regisztrált cikk szerepel a számlálóregisztrációban, a jó mennyiség is és a hibás mennyiség is. Ha szükséges, manuálisan is be lehet állítani számlálóregisztrációkat.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Számlálótípusok létrehozása eszközszámláló regisztrációkhoz

1. Válassza az **Eszközkezelés** > **Beállítás** > **Eszköztípusok** > **Számlálók**lehetőséget.
2. Válassza ki az **Új** lehetőséget egy új számlálótípus létrehozásához.
3. Szúrjon be egy azonosítót a **Számláló** mezőbe, és a számláló nevét a **Név** mezőbe.
4. Az **Általános** gyorslapon válassza ki a számlálóegységet az **Egység** mezőben.
5. A **Frissítés** mezőben válassza ki a számlálóhoz használandó frissítési módot.
6. Válassza az „igen” beállítást a **Számlálóértékek öröklése** választógombon ha a tárgyieszköz-szerkezethez tartozó tárgyi eszközöknek automatikusan örökölniük kell a fölérendelt a számlálóregisztrációkat.
7. A **Teljes összesítés** mezőben válassza ki a számlálóhoz ezen számlálótípus felhasználásával használandó összesítési módszert. Az „összeg” az alapbeállítás, amellyel a program folyamatosan hozzáadja a regisztrált értékeket a teljes értékhez. Az „Átlag” akkor használható, ha egy számláló esetében be van állítva egy eszköz küszöbértékének figyelése, például a hőmérséklet, rezgés vagy kopás az eszközön. 
8. Az **Eltérés felfelé** mezőbe írja be a felső szintet százalékban annak ellenőrzéséhez, hogy a manuális számlálóregisztrációk egy elvárt tartományon belül vannak-e. Az ellenőrzés alapja a meglévő számlálóregisztrációk lineáris növekedése.
9. Az **Eltérés lefelé** mezőbe írja be az alsó szintet százalékban annak ellenőrzéséhez, hogy a manuális számlálóregisztrációk egy elvárt tartományon belül vannak-e. Az ellenőrzés alapja a meglévő számlálóregisztrációk lineáris csökkenése.
10. A **Típus** mezőben válassza ki, hogy milyen típusú üzenetet (tájékoztatás, figyelmeztetés, hiba) kíván megjeleníteni, ha a megadott tartományon kívüli eltérések következnek be, amikor manuális számlálóregisztrációkat hajt végre.
11. Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket a számláló használhat.
12. A **Kapcsolódó eszközszámlálók** gyorslapon adja meg azokat azt a számlálót, amelyeket automatikusan frissíteni szeretne az számláló frissítésekor.


>[!NOTE]
>A kapcsolódó számlálót csak akkor frissíti automatikusan a program, ha a kapcsolódó számláló tárgyieszköz-típusa szerepel a számláló beállításaiban. Például: Beállít egy számlálót a „Termelési órák” elemhez és hozzáadja a „Teherautómotor” eszköztípust. Ha a számláló frissítése megtörtént, akkor a program a kapcsolódó „Olaj” számlálót is frissíti ugyanazzal az számlálóértékkel. A **Számlálók** beállítása tartalmazza az „Órák” beállítást. Ezenkívül az „Olaj" számláló esetében a „Teherautómotor” eszköztípust hozzá kell adni az **Eszköztípusok** gyorslaphoz, hogy biztosítva legyen a számláló kapcsolata. Az alábbi képernyőképek láthatók az Óra és Olaj számlálók beállításával kapcsolatos példa.

Ha eszköztípusokat ad egy számlálóhoz a **Számlálók**alatt, akkor a számláló automatikusan hozzá lesz adva az eszköztípusokhoz **Számlálók** gyorslapon az [Eszköztípusok](../setup-for-objects/object-types.md) alatt.

![1. ábra](media/071-setup-for-objects.png)

