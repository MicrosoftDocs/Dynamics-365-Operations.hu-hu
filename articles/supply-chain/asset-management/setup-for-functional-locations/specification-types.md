---
title: Karbantartási attribútumtípusok
description: Ez a témakör bemutatja, hogyan lehet attribútumtípusokat létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 469bcb16bb3099ffabdccfb026f0414de0213aaa
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889098"
---
# <a name="maintenance-attribute-types"></a>Karbantartási attribútumtípusok

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja, hogyan lehet attribútumtípusokat létrehozni az Eszközkezelés modulban. Az attribútumok a különböző elemek tulajdonságainak leírására szolgálnak. A következő elemeknél lehet beállítani attribútumokat:

- [Munkavégzési helyszínek típusai](../setup-for-functional-locations/functional-location-types.md)
- [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md)
- [Eszköztípusok](../setup-for-objects/object-types.md)
- Eszközök

A beállítható attribútumok az elemtől függően változhatnak. Egy munkavégzési helyszín esetében például a hely konfigurációjához és fizikai méretéhez állíthat be attribútumokat. Egy eszköztípus vagy eszköz esetében a motor térfogatához, energiafogyasztásához és maximális terheléséhez különböző feltételek mellett is beállíthat attribútumokat.

## <a name="create-attribute-types"></a>Attribútumtípusok létrehozása

Létrehozhatja saját attribútumtípusait. Ezenkívül a termékdimenziókat áthelyezheti az **Attribútumtípusok** oldalra.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Attribútumtípusok** lehetőséget.
2. Ha első alkalommal hoz létre attribútumtípusokat, válassza ki a **Termékdimenziók létrehozása** elemet a szabványos termékdimenziók automatikus áthelyezéséhez.
3. Válassza ki az **Új** lehetőséget egy új attribútumtípus létrehozásához.
4. Az **Attribútumtípus** mezőben adja meg az attribútumtípus nevét.
5. Adjon meg egy leírást a **Leírás** mezőben.
6. Az **Egység** mezőben szükség szerint válassza ki a megfelelő attribútumegységet.
7. Az **Adattípus** mezőben válasszon ki egy adattípust az egységhez.
8. Ha a **Karakterláncot** választotta adattípusként, kövesse az alábbi lépéseket az attribútumtípus értékeinek létrehozásához:

    1. Válassza ki az attribútumtípust, majd az **Értékek** lehetőséget.
    2. Az **Attribútumértékek** mezőben válassza ki az **Új** lehetőséget.
    3. Az **Attribútumtípus** mezőben válasszon ki egy attribútumtípust (dimenziót).
    4. Az **Érték** mezőben adja meg a kapcsolódó értéket.
    5. Adjon meg egy leírást a **Leírás** mezőben.
    6. Mentse a rekordot.
    7. Térjen vissza az **Attribútumtípusok** oldalra.

9. Mentse a rekordot.

    A **Munkavégzési helyszín típusai** mezőben az attribútumtípust használó munkavégzési helyszínek száma látható. Az **Eszköztípusok** mezőben az azt használó eszköztípusok száma látható.
