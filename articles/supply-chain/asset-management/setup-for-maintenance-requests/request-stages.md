---
title: Karbantartási kérések életciklus-állapotai
description: Ez a témakör azt ismerteti, hogy miként állíthatja be a karbantartási kérés életciklus-állapotait az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9022d866bf0da08a72ba9169587f87c1b77527a6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217221"
---
# <a name="maintenance-request-lifecycle-states"></a>Karbantartási kérések életciklus-állapotai

[!include [banner](../../includes/banner.md)]

 


A karbantartási kérés életciklus-állapotai meghatározzák, hogy a kérés milyen fázisokon mehet keresztül. Ilyen fázis például a **Létrehozva**, **Aktív** és **Befejezve** állapot. A karbantartási kérés munkarendeléssé átalakításakor a karbantartási kérés életciklus-állapotát **Befejezve** vagy **Lezárt** állapotúra kell frissíteni, ha a karbantartási kérés már nem aktív. Az **Összes karbantartási kérés** listaoldalán megtekintheti az összes karbantartási kérést, függetlenül azok életciklus-állapotától.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Karbantartási kérés életciklus-állapotainak beállítása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Életciklus-állapotok** elemet.
2. Válassza ki az **Új** elemet egy karbantartási kérés életciklus-állapotának létrehozásához.
3. Az **Életciklus-állapot** mezőben adja meg az életciklus-állapot azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.

    A **Részletek** gyorslapon az **Életciklusmodellek** mezőben látható az adott életciklus-állapotot használó karbantartási kérés életciklusmodelljeinek a száma.

5. Az **Általános** gyorslapon állítsa az **Aktív** beállítást **Igen** értékre, ha a karbantartási kérésnek mindaddig aktívnak kell lennie, amíg ebben az életciklus-állapotban van.
6. Állítsa a **Tényleges befejezés beállítása** lehetőséget **Igen** értékre, ha az ebben az életciklus-állapotban lévő karbantartási kérésben automatikusan meg kell adni egy tényleges befejezési dátumot és időpontot.
7. Állítsa a **Munkarendelés létrehozása** beállítást **Igen** értékre, ha az ebben az életciklus-állapotban lévő karbantartási kérésből munkarendelés hozható létre.
8. Állítsa a **Törlés** lehetőséget **Igen** értékre, ha a karbantartási kérés törölhető, amíg ebben az életciklus-állapotban van.
9. A **Frissítés** gyorslapon az **Eszköz** szakaszának **Bejövő** és **Kimenő** beállításai akkor fontosak, ha a raktárjavítást használ. A megfelelő beállítást akkor kell **Igen** értékre beállítani, ha a karbantartási kérelemben kiválasztott eszközök életciklus-állapotát automatikusan **Bejövő** vagy **Kimenő** állapotúra kell módosítani, amikor a karbantartási kérelem életciklus-állapota **Bejövő** vagy **Kimenő** értékre van állítva.

A következő ábra a **Karbantartási kérések életciklus-állapotai** oldalt szemlélteti.

![Karbantartási kérések életciklus-állapotai oldal](media/02-setup-for-requests.png)

> [!NOTE]
> A karbantartási kérések életciklus-állapotait, az életciklus-állapot csoportjait és típusait ugyanúgy használják, mint a munkarendelés életciklus-állapotait, csoportjait és típusai. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Karbantartási kérés életciklusmodelljeinek beállítása

Miután létrehozta a karbantartási kérésekhez szükséges életciklus-állapotokat, azok feloszthatók életciklusállapot-csoportokra vagy -modellekre. A karbantartási kérések életciklusmodelljei segítségével különböző típusú karbantartási kérésekhez felhasználható áramlási folyamatot hozhat létre. Legalább egy szabványos karbantartási kéréshez tartozó életciklus-modellt létre kell hozni.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Életciklus-modellek** elemet.
2. Válassza ki az **Új** elemet egy karbantartási kérés életciklusmodelljének létrehozásához.
3. Az **Életciklusmodell** mezőben adja meg az életciklusmodell azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.

    A **Részletek** gyorslapon az **Életciklus-állapotok** mezőben látható az adott életciklusmodellben kiválasztott életciklus-állapotok száma. A **Karbantartási kérések típusai** mezőben az ezen életciklus-modellt használó karbantartási kérések típusainak száma látható.

5. Az **Életciklus-állapotok** gyorslapon válassza ki azokat az életciklus-állapotokat, amelyeket fel kell venni az életciklus-modellbe:

    - Az életciklus-modellben feltüntetendő életciklus-állapotot válassza ki a **Hátralevő életciklus-állapotok** szakaszban, majd a jobbra nyíl ![Jobbra nyíl](media/03-setup-for-requests.png) gombbal helyezze át a **Kijelölt életciklus-állapotok** szakaszba.
    - Ahhoz, hogy az összes elérhető életciklus-állapotot feltüntesse az életciklus-modellben, nyomja meg az **Összes elérhető állapot** ![Összes elérhető állapot](media/04-setup-for-requests.png) gombot. Az összes életciklus-állapot a **Kijelölt életciklus-állapotok** szakaszba kerül.
    - Ha el kíván távolítani egy életciklus-állapotot az életciklus-modellből, válassza ki az adott állapotot a **Kijelölt életciklus-állapotok** szakaszban, majd a Balra nyíl ![Balra nyíl](media/05-setup-for-requests.png) gombbal helyezze át a **Hátralévő életciklus-állapotok** szakaszba.

6. Az **Általános** gyorslapon a **Frissítések** szakasz mezői a relevánsak, ha raktárjavítást használ.

    - A **Bevételezett eszköz életciklus-állapota** mezőben válassza ki azt az eszközéletciklus-állapotot, amelyre a karbantartási kérésnél kiválasztott eszközöket automatikusan frissíteni kell, amikor beérkeznek raktárjavításhoz.
    - A **Kiszállított eszköz életciklus-állapota** mezőben válassza ki azt az eszközéletciklus-állapotot, amelyre a karbantartási kérésnél kiválasztott eszközöket automatikusan frissíteni kell, amikor visszaérkeznek javítás után.

A következő ábra a **Karbantartási kérések életciklusmodellek** oldalt szemlélteti.

![Karbantartási kérés életciklusmodelljei oldal](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]