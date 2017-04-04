---
title: "Származtatott könyvek"
description: "Ez a cikk a származtatott könyv funkcióról nyújt áttekintést."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 9319fe95a25b38ca12cbc8633763b042e4086aea
ms.lasthandoff: 03/31/2017


---

# <a name="derived-books"></a>Származtatott könyvek

Ez a cikk a származtatott könyv funkcióról nyújt áttekintést.

Származtatott könyvek célja egyszerűsítése érdekében a befektetett eszköz tranzakcióinak rendszeres időközönként tervezett feladása.  Az elsődleges könyvként választhat egy könyvet. Ez általában az értékcsökkenés könyveléséhez használatos könyv. Ezután hozzákapcsolhatja ezt más könyvekhez, amelyek úgy vannak beállítva, hogy az elsődleges könyvvel megegyező időintervallumokban adjanak fel tranzakciókat. Az adózási szempontú értékcsökkenés könyvei gyakran származtatott könyvként vannak beállítva. 

A származtatott könyvekkel feladott leggyakoribb tranzakciók a beszerzések, a beszerzési helyesbítések és a kivezetések. 

## <a name="example"></a>Példa

A B és C könyvek beállítása a származtatott könyvként van beállítva az A könyvhöz, amelynek tranzakciótípusa beszerzés. Az A könyvbe vigyen be egy beszerzési tranzakciót a 123-as tárgyi eszközhöz 1500,00 értékben. 

A tranzakció feladása során a program a B könyvben és a C könyvben is létrehoz és felad egy beszerzési tranzakciót a 123-as tárgyi eszközzel, 1500,00 értékben. Amikor előkészíti az elsődleges könyv tranzakcióit a tárgyieszköz-naplóba történő feladáshoz, a származtatott könyvek tranzakcióit is megtekintheti és módosíthatja. Ha egy másik naplóban készíti elő az elsődleges könyv tranzakcióit, akkor a származtatott értékek tranzakciói nem jelennek meg. A program azonban az elsődleges könyv tranzakcióinak feladása során feladja őket a megfelelő számlákra és feladási rétegekbe.

> [!NOTE]                                                                                                                               
> Azokat a könyveket, amelyek úgy vannak beállítva, hogy az elsődleges könyv feladási időközeitől eltérő időközönként adják fel a tranzakciókat, külön könyvként (nem származtatott könyvként) kell a tárgyi eszközhöz társítani.  

További tudnivalókért lásd: [feladás származtatott könyvek](post-derived-value-models.md).


