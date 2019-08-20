---
title: Eszköz mértékei
description: A témakör bemutatja, hogyan lehet eszközmérték típusokat létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783329"
---
# <a name="asset-measures"></a>Eszköz mértékei

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A témakör bemutatja, hogyan lehet eszközmérték típusokat létrehozni az Eszközkezelés modulban. Az eszközmérték-típusokkal lehet mérni a méréseket lehet regisztrálni eszközökön, például a termelési órák száma vagy a tárgyi eszközön termelt mennyiség tekintetében. Az eszköztípusok az eszközmérték-típusokhoz kapcsolódnak. Ez azt jelenti, hogy egy eszköz esetében csak akkor használható egy eszközmérték, ha az eszköz típusánál be van állítva az eszközmérték.

Az eszközökre vonatkozó mértékregisztrációk előtt létre kell hoznia a **Számlálókban**használni kívánt eszközmérték-típusokat. Ezután az eszközökre vonatkozó mértékregisztrációkat kell létrehoznia az **Eszközök mértékei**helyen. 

Az eszközmértékek a karbantartási tervekben használhatók. Egy karbantartási terv sora lehet „Számláló” típusú például, amely a termelési órák számához vagy a termelt mennyiséggel kapcsolatos. 

Az eszközmértékek regisztrálása manuálisan vagy automatikusan történhet, a termelési órák vagy a termelt mennyiségek alapján. Egy eszközmértéket úgy is be lehet állítani, hogy a három frissítési mód egyikét használja (a **Frissítés** mezőben választható ki a **Számlálók** alatt):
  
- Manuális – manuálisan kell regisztrálni az eszközmérték-értékeket.  
- Termelési órák – a számláló automatikusan frissül a termelési órák száma alapján.  
- Termelt mennyiség– a számláló automatikusan frissül a termelt mennyiség alapján.  

>[!NOTE]
>Ha a termelt mennyiséget használja, az *összes* regisztrált cikk szerepel a mértékregisztrációban, a jó mennyiség is és a hibás mennyiség is. Ha szükséges, manuálisan is be lehet állítani eszközmérték-regisztrációkat.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Számlálótípusok létrehozása eszközszámláló regisztrációkhoz

1. Válassza az **Eszközkezelés** > **Beállítás** > **Eszköztípusok** > **Számlálók**lehetőséget.
2. Válassza az **Új** lehetőséget egy új eszközmérték-típus.
3. Szúrjon be egy azonosítót a **Számláló** mezőbe, és a számláló nevét a **Név** mezőbe.
4. Az **Általános** gyorslapon válassza ki a mértékegységet az **Egység** mezőben.
5. A **Frissítés** mezőben válassza ki az eszközhöz használandó frissítési módot.
6. Válassza az „igen” beállítást a **Számlálóértékek öröklése** választógombon ha a tárgyieszköz-szerkezethez tartozó tárgyi eszközöknek automatikusan örökölniük kell a fölérendelt eszközön végzett regisztrációkat.
7. A **Teljes összesítés** mezőben válassza ki a tárgyi eszközmértékhez ezen eszközmérték felhasználásával használandó összesítési módszert. Az „összeg” az alapbeállítás, amellyel a program folyamatosan hozzáadja a regisztrált értékeket a teljes értékhez. Az „Átlag” akkor használható, ha egy eszköz esetében be van állítva egy eszköz küszöbértékének figyelése, például a hőmérséklet, rezgés vagy kopás az eszközön. 
8. Az **Eltérés felfelé** mezőbe írja be a felső szintet százalékban annak ellenőrzéséhez, hogy a manuális eszközmérték-regisztrációk egy elvárt tartományon belül vannak-e. Az ellenőrzés alapja a meglévő eszközmérték-regisztrációk lineáris növekedése.
9. Az **Eltérés lefelé** mezőbe írja be az alsó szintet százalékban annak ellenőrzéséhez, hogy a manuális eszközmérték-regisztrációk egy elvárt tartományon belül vannak-e. Az ellenőrzés alapja a meglévő eszközmérték-regisztrációk lineáris csökkenése.
10. A **Típus** mezőben válassza ki, hogy milyen típusú üzenetet (tájékoztatás, figyelmeztetés, hiba) kíván megjeleníteni, ha a megadott tartományon kívüli eltérések következnek be, amikor manuális eszközmérték-regisztrációkat hajt végre.
11. Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket az eszközmérték használhat.
12. A **Kapcsolódó eszközmértékek** gyorslapon adja meg azokat az eszközmértékeket, amelyeket automatikusan frissíteni szeretne az ezsközmérték frissítésekor.


>[!NOTE]
>A kapcsolódó eszközmértéket csak akkor frissíti automatikusan a program, ha a kapcsolódó eszközmérték tárgyieszköz-típusa szerepel az eszközmérték beállításaiban. Például: Beállít egy eszközmértéket a „Termelési órák” elemhez és hozzáadja a „Teherautómotor” eszköztípust. Ha a tárgyi az eszközmérték frissítése megtörtént, akkor a program a kapcsolódó „Olaj” számlálót is frissíti ugyanazzal az eszközmérték-értékkel. A **Számlálók** beállítása tartalmazza az „Órák” beállítást. Ezenkívül az „Olaj" eszközmérték esetében a „Teherautómotor” eszköztípust hozzá kell adni az **Eszköztípusok** gyorslaphoz, hogy biztosítva legyen az eszközmérték kapcsolata. Az alábbi képernyőképek láthatók az Óra és Olaj eszközmértékek beállításával kapcsolatos példa.

Ha eszköztípusokat ad egy eszközmértékhez a **Számlálók**alatt, akkor az eszközmérték automatikusan hozzá lesz adva az eszköztípusokhoz **Számlálók** gyorslapon az [Eszköztípusok](../setup-for-objects/object-types.md) alatt.

![1. ábra](media/071-setup-for-objects.png)


