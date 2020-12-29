---
title: Munkavégzési helyszín életciklus-állapotai
description: Ez a cikk azt ismerteti, hogyan állítható be a munkavégzési helyszínek állapota és életciklusmodellje az Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationLifecycleModel, EntAssetFunctionalLocationLifecycleState
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eedc21dde32671b4f5539ac4e798a8e1329c191
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429817"
---
# <a name="functional-location-lifecycle-states"></a>Munkavégzési helyszín életciklus-állapotai

[!include [banner](../../includes/banner.md)]

 

Ez a cikk azt ismerteti, hogyan állítható be a munkavégzési helyszínek életciklus-állapota és életciklusmodellje az Eszközkezelésben. A munkavégzési helyszínek életciklus-állapota határozza meg a munkavégzési helyszín esetleges állapotait (például létrehozott, aktív, befejezett). Az életciklus-állapottól függetlenül minden munkavégzési helyszín megtekinthető az **Összes munkavégzési helyszín** listaoldalon. Ha módosítani szeretné egy munkavégzési helyszín állapotát, jelölje ki az **Összes munkavégzési helyszín** listaoldalon, és válassza a **Munkavégzési helyszín állapotának frissítése** lehetőséget.

## <a name="set-up-functional-location-lifecycle-states"></a>Munkavégzési helyszín életciklus-állapotainak beállítása

1. Válassza ki az **Eszközök kezelése** > **Beállítás** > **Munkavégzési helyszínek** > **Életciklus-állapotok** lehetőséget.
2. Ha új állapotot szeretne létrehozni a munkavégzési helyszínhez, válassza ki az **Új** lehetőséget.
3. Adja meg az állapot azonosítóját az **Életciklus-állapot** mezőben, és a munkavégzési helyszín állapotát a **Név** mezőben. Az **Életciklusmodellek** mezőben látható, hogy hány munkavégzési helyszín életciklusmodellje használja a munkavégzési helyszín állapotát.
4. Az **Általános** gyorslap **Aktív** váltógombjánál válassza az „Igen” lehetőséget, ha a munkavégzési helyszínnek aktívnak kell lennie ebben az állapotban.
5. Az **Eszközök létrehozása** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy automatikusan létre lehessen hozni egy eszközt a munkavégzési helyszín nevével, és telepíteni lehessen a munkavégzési helyszínen ebben az állapotban.  
>[!NOTE]
>Ez a váltógomb össze van kapcsolva az **Eszköztípus** mezővel (amely az **Általános** gyorslapon található a **Munkavégzési helyszínek típusai** űrlapon – **Eszközök kezelése** > **Beállítás** > **Munkavégzési helyszín** > **Munkavégzési helyszínek típusai**).
6. A **Hely átnevezése** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy lehessen módosítani a munkavégzési helyszín nevét ebben az állapotban.
7. Az **Új alhelyek** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy lehessen új alhelyeket felvenni a munkavégzési helyszínhez ebben az állapotban.
8. Az **Eszközök telepítése** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy lehessen eszközöket telepíteni a munkavégzési helyszínen ebben az állapotban.
9. A **Munkavégzési helyszín törlése** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy lehessen törölni a munkavégzési helyszínt ebben az állapotban.
10. Az **Életciklus-állapot** mezőben állítson be állapotot az eszközhöz, ha azt szeretné, hogy az munkavégzési helyszínen telepített összes eszköz életciklus-állapota automatikusan frissüljön ebben az állapotban. Példa: ha bezár egy munkavégzési helyszínt, és az életciklus-állapotát „Befejezve” értékre állítja, akkor érdemes automatikusan „Nincs használatban” értékre módosítani az adott munkavégzési helyszínen telepített eszközök életciklus-állapotát.


>[!NOTE]
>A munkavégzési helyszínek életciklus-állapotai, életciklusmodelljei és típusai ugyanúgy vannak összekapcsolva és használva, mint a munkarendelések életciklus-állapotai, életciklusmodelljei és típusai. 

## <a name="set-up-functional-location-lifecycle-models"></a>Munkavégzési helyszín életciklusmodelljeinek beállítása

A munkavégzési helyszínekhez szükséges életciklus-állapotok létrehozása után az állapotok csoportokba oszthatók. Ezzel létrehozható a munkavégzési helyszínek különböző típusaihoz használható életciklusmodell-forgalom. Legalább egy munkavégzési helyszín normál életciklusmodelljét létre kell hozni.

1. Válassza ki az **Eszközök kezelése** > **Beállítás** > **Munkavégzési helyszínek** > **Életciklusmodellek** lehetőséget.
2. Válassza ki az **Új** lehetőséget egy új életciklusmodell létrehozásához.
3. Adja meg az életciklusmodell azonosítóját az **Életciklusmodell** mezőben, és az életciklusmodell nevét a **Név** mezőben. A **Munkavégzési helyszínek típusai** és az **Életciklus-állapotok** mezőben látható, hogy a munkavégzési helyszínek hány típusa használja az életciklusmodellt, illetve az életciklusmodellben kiválasztott állapotok számát.
4. Az **Életciklus-állapotok** gyorslapon válassza ki a modellben használandó állapotokat. Ehhez kattintson az állapotra a **Fennmaradó életciklus-állapotok** szakaszban, majd az ![előre nyíl](media/02-setup-for-functional-locations.png) gombra.
5. Ha egy modellhez az összes rendelkezésre álló állapotot ki szeretné választani, kattintson a ![minden elérhető állapot kiválasztása](media/03-setup-for-functional-locations.png) gombra. Az összes állapot átkerül az **Életciklus-állapotok kiválasztva** szakaszba.
6. Ha el szeretne távolítani egy állapotot a kijelölt modellből, válassza ki az **Életciklus-állapotok kiválasztva** szakaszban, és kattintson a ![vissza nyíl](media/04-setup-for-functional-locations.png) gombra.
7. Az **Életciklus-állapot frissítései** lehetőséggel megadhatja, hogy melyik életciklus-állapotok követhetnek egy kiválasztott állapotot.
