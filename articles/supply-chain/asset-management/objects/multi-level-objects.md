---
title: Többszintű eszközök
description: Ez a témakör a többszintű eszközök létrehozásának és törlésének módját ismerteti.
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
ms.openlocfilehash: 5c2a4052f9beca554932d7f2547288e02358b603
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571507"
---
# <a name="multi-level-assets"></a>Többszintű eszközök

[!include [banner](../../includes/banner.md)]

 

Ez a témakör a többszintű eszközök létrehozásának és törlésének módját ismerteti. Az eszközöket és a kapcsolódó aleszközöket hierarchikus fastruktúrában lehet létrehozni. Így megjelenítheti az eszközök közötti kapcsolatokat és függőségeket. A karbantartási munkákat a fastruktúra minden szintjéhez lehet kapcsolni. Statisztikákat egyéni szintekhez, vagy az összes aleszközszint összességéhez is létre lehet hozni.

Az **Összes eszköz** listoldalon (**Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz**) az **Eszköz** oszlopban megtlaálható az eszközök listája hierarchikus sorrendben. A **Fölérendelt** oszlop a kapcsolódó fölérendelt elemet mutatja. Ezenkívül, ha már létrehoztak eszközöket és aleszközöket, akkor a **Kapcsolódó információk** ablaktábla **Eszközfa** szakaszában láthatók az eszközök fastruktúrában.

Az eszközök létrehozásával kapcsolatos további tudnivalókért tekintse meg az [Eszköz létrehozása](../objects/create-an-object.md) részt. Aleszköz létrehozásához válassza ki a fölérendelt eszközt az **Általános** gyorslap **Fölérendelt** mezőjében.

## <a name="copy-an-asset-or-asset-structure"></a>Eszköz vagy eszközstruktúra másolása

Ha a vállalatnál több hasonló eszközstruktúra is van, az Eszközkezelés Másolás funkciója segítségével gyorsan létrehozhatja azokat.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget.
2. Az **Összes eszköz** listaoldalon válassza ki a másolni kívánt eszközt. Ha például a teljes eszközstruktúrát kívánja másolni (az aleszközöket is beleértve), válasszon ki egy fölérendelt eszközt.
3. Válassza az **Eszköz másolása** lehetőséget. A **Másolás forrása** szakasz **Eszköz** mezője a listaoldalon kiválasztott eszközre van állítva.
4. A **Másolás célja** szakasz **Eszköz mezőjében** adja meg az új eszköz nevét.
5. Ha a létrehozott eszköz egy meglévő eszközstruktúrához kell, hogy tartozzon, akkor válasszon egy fölérendelt azonosítót a **fölérendelt eszköz** szakasz **Eszköz** mezőjében.
6. Válassza ki az **OK** lehetőséget. Az új eszközstruktúra megjelenik az **Összes eszköz** listaoldalon. A másolt eszközhöz kapcsolódó összes eszközattribútum, karbantartási terv és karbantartási kör átkerül az új eszközre vagy eszközstruktúrára.

Eszközstruktúra másolásakor az új struktúrában szereplő aleszközök neve megegyezik a másolt aleszközök nevével. A másolási eljárás befejezése után egyszerűen megváltoztathatja az eszköz nevét és egyéb beállításait. Válassza ki az eszközt az **Összes eszköz** listaoldalon, majd kattintson a **szerkesztés** gombra.

> [!NOTE]
> Eszköz-vagy eszközstruktúra másolásakor az új eszközök életciklus-állapota visszaáll az eszközök kezdeti életciklus-állapotaként megadott tetszőleges állapotra. A munkavégzési helyszín visszaáll az alapértelmezett munkavégzési helyszínre.

## <a name="delete-an-asset-or-asset-structure"></a>Eszköz vagy eszközstruktúra törlése

Ha egy eszköz kapcsolódó aleszközökkel rendelkezik, akkor azt csak akkor törölheti, ha bármelyik eszközre nincs regisztrálva karbantartási kérés, munkarendelési feladat, hibaregisztrációk vagy állapotfelmérések.

1. Az **Összes eszköz** listaoldalon válassza ki a törölni kívánt eszközt.
2. Válassza a **Törlés** lehetőséget.

> [!NOTE]
> Ha ezzel az eljárással nem lehet törölni egy eszközt, egy másik módszer a törlés kezelésére, hogy egy eszközéletciklus-állapotot állítson be erre a célra. Beállíthat például egy **Selejtezett** vagy **Törölt** életciklus-állapotot az **Eszköz életciklus-állapotai** oldalon.
