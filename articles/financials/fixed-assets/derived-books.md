---
title: "Származtatott könyvek"
description: "Ez a cikk a származtatott könyv funkcióról nyújt áttekintést."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e43dcc15212ae90a33d59fa32692aabcba7a19cb
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="derived-books"></a>Származtatott könyvek

[!include [banner](../includes/banner.md)]

Ez a cikk a származtatott könyv funkcióról nyújt áttekintést.

A származtatott könyvek célja az, hogy egyszerűbb legyen a tárgyi eszközök tranzakcióinak rendszeres időközönként tervezett feladása.  Elsődleges könyvként egy könyvet választhat ki. Ez általában az értékcsökkenés könyveléséhez használatos könyv. Ezután hozzákapcsolhatja ezt más könyvekhez, amelyek úgy vannak beállítva, hogy az elsődleges könyvvel megegyező időintervallumokban adjanak fel tranzakciókat. Az adózási szempontú értékcsökkenés könyvei gyakran származtatott könyvként vannak beállítva. 

A származtatott könyvekkel feladott leggyakoribb tranzakciók a beszerzések, a beszerzési helyesbítések és a kivezetések. 

## <a name="example"></a>Példa

A B és C könyvek beállítása a származtatott könyvként van beállítva az A könyvhöz, amelynek tranzakciótípusa beszerzés. Az A könyvbe vigyen be egy beszerzési tranzakciót a 123-as tárgyi eszközhöz 1500,00 értékben. 

A tranzakció feladása során a program a B könyvben és a C könyvben is létrehoz és felad egy beszerzési tranzakciót a 123-as tárgyi eszközzel, 1500,00 értékben. Amikor előkészíti az elsődleges könyv tranzakcióit a tárgyieszköz-naplóba történő feladáshoz, a származtatott könyvek tranzakcióit is megtekintheti és módosíthatja. Ha egy másik naplóban készíti elő az elsődleges könyv tranzakcióit, akkor a származtatott értékek tranzakciói nem jelennek meg. A program azonban az elsődleges könyv tranzakcióinak feladása során feladja őket a megfelelő számlákra és feladási rétegekbe.

> [!NOTE]                                                                                                                               
> Azokat a könyveket, amelyek úgy vannak beállítva, hogy az elsődleges könyv feladási időközeitől eltérő időközönként adják fel a tranzakciókat, külön könyvként (nem származtatott könyvként) kell a tárgyi eszközhöz társítani.  

További információért lásd: [Feladás származtatott könyvekkel](post-derived-value-models.md).




