---
title: "Szolgáltatási sablonok"
description: "A szolgáltatási szerződés sablonként adható meg, és később a sablon sorai más szolgáltatási szerződésekbe vagy szervizrendelésekbe másolhatók."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 09f2da382cd7f3e0e3d4bfa389e9cdf74f00b501
ms.openlocfilehash: ade518095b77141fb31b597a955dd23aaae119d7
ms.contentlocale: hu-hu
ms.lasthandoff: 02/27/2018

---

# <a name="service-templates"></a>Szolgáltatási sablonok

[!include[banner](../includes/banner.md)]

A szolgáltatási szerződés sablonként adható meg, és később a sablon sorai más szolgáltatási szerződésekbe vagy szervizrendelésekbe másolhatók.

## <a name="example"></a>Példa

Egy ügyfél, akinek a vállalat szolgáltatást nyújt, öt különböző helyen egyforma lifteket szervizeltet.

Öt szolgáltatási szerződést akar létrehozni az ügyfél számára, mindegyik telephelyhez egyet.
A létrehozás ismétlődő feladatainak csökkentése, illetve a különböző szerződések egységes kitöltése érdekében létrehoz egy szolgáltatási szerződést, és azt megadja sablonként a lifteken végzett szervizmunkához.

Így más bemásolhatja a sablon sorait az öt új szolgáltatási szerződésbe, és mindegyik szolgáltatási szerződést a sablonból tölti fel a program adatokkal.

## <a name="create-a-template"></a>Sablon létrehozása

Szolgáltatássablon létrehozásához létre kell hoznia egy szolgáltatási szerződést, létre kell benne hoznia a szükséges sorokat, majd a szolgáltatási szerződést egy szolgáltatássablon-csoporthoz kell hozzárendelnie.

> [!NOTE]
> Szolgáltatási szerződést csak akkor lehet sablonként megadni, ha nincsen hozzá csatolva szervizrendelés. Ezenkívül sablonként meghatározott szolgáltatási szerződésből nem lehet szervizrendeléseket létrehozni.

## <a name="copy-template-lines"></a>Sablonsorok másolása

Szolgáltatássablonból másik szolgáltatási szerződésbe vagy szervizrendelésbe lehet sorokat másolni.

Amikor sablon sorait szervizrendelésekbe vagy szolgáltatási szerződésekbe másolja a sabloncsoportok fastruktúrában jelennek meg, és mindegyik csoportot ki lehet bontani. Ez a nézet lehetővé teszi mindegyik sablon és sablonsor megjelenítését.

Ha a sablonokat a használatuknak megfelelő név szerinti csoportokba rendezte, könnyebb meghatározni, hogy mely szolgáltatásisablon-sorokat kell másolni.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Szolgáltatási sablonok sorainak másolása](copy-service-template-lines.md)

