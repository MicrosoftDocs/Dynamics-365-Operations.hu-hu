---
title: Szolgáltatási sablonok
description: A szolgáltatási szerződés sablonként adható meg, és később a sablon sorai más szolgáltatási szerződésekbe vagy szervizrendelésekbe másolhatók.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7c99e56751230a7b8881dc55c1d460674cc6f0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850488"
---
# <a name="service-templates"></a>Szolgáltatási sablonok

[!include [banner](../includes/banner.md)]

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

## <a name="related-articles"></a>Kapcsolódó cikkek

[Szolgáltatási sablonok sorainak másolása](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]