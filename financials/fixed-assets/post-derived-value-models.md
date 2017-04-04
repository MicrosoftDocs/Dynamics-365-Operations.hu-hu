---
title: "A származtatott könyvek feladása"
description: "Ez a cikk a származtatott könyvek használatának módját ismerteti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: ca077727910059878fb16a3f78c5b9133c6c741f
ms.lasthandoff: 03/31/2017


---

# <a name="post-with-derived-books"></a>A származtatott könyvek feladása

Ez a cikk a származtatott könyvek használatának módját ismerteti.

Ha származtatott könyvet tartalmazó értékmodellhez ad fel tranzakciókat, a származtatott tranzakciókat a program automatikusan feladja a naplókból, a beszerzési rendelésekből vagy a szabadszöveges számlázásokból. Azonban ha Tárgyieszköz-naplóban készíti elő az elsődleges könyvtranzakciókat, akkor megtekintheti és módosíthatja a származtatott tranzakciók összegeit, mielőtt feladja őket.
-   Bizonyos számlákat, így az áfaszámlát és a vevői vagy szállítói számlákat a program csak egyszer – az elsődleges könyv feladása során – frissít. A származtatott könyvtranzakciók feladásra kerülnek azokhoz a számlákhoz, amelyek a származtatott könyvhöz lettek meghatározva a Tárgyi eszköz feladási profilok lapon.
-   A beszerzés gyakran a származtatott könyvek tranzakciótípusa. Ezt akkor lehet használni, amikor a tárgyi eszköz beszerzésének az idejétől a könyvet és a származtatott könyvet kell alkalmazni a tárgyi eszközre.
-   A tranzakciótípus egyéb felvehető értékei. Ha például az elsődleges könyv és a származtatott könyvek az értékesítést és a kivezetést illetően ugyanazokat az intervallumokat használják, akkor az összes tranzakciótípus rendelkezésre áll a származtatott értékcsökkenés könyv beállítása során.

> [!WARNING]
> A származtatott könyvbe feladott összeg megegyezik az elsődleges könyvbe feladott összeggel. Ha a könyvek értékcsökkenési módszere eltérő, akkor nem ajánlott a származtatott eljárással készíteni értékcsökkenési tranzakciókat. |

## <a name="example"></a>Példa 
A következő adatok leírják, hogyan állítson be beszerzési tranzakciókat a származtatott könyv funkcióval.

1.  Az áfakönyvek létrehozása a Könyvek lapon.
    -   A könyvelési könyv: VM 1, Jelenlegi feladási réteg
    -   Az adózáshoz használt könyv: VM 2, Adó feladási réteg

2.  A VM 1-en kattintson a Származtatott könyvek lapra. Válassza ki a VM 2-t a Könyv mezőben és a Beszerzés elemet a Tranzakciótípus mezőben.

A könyveket ezután csatolni lehet meghatározott tárgyi eszközökhöz. 

Beszerzés könyvelésekor a befektetett eszköz könyv: ÉM 1, a vásárlás feladása nem csak az ÉM 1, hanem ÉM 2 származtatott könyv. Mindkét tárgyieszköz-könyvek állapotának értékről Nyitott értékre módosul.

> [!NOTE]                                                                                                         
> Ha nem használ származtatott értékcsökkenési könyveket, akkor a VM 1 értékmodellbe és VM 2 könyvbe is fel kell adni a tárgyieszköz-beszerzést.

További tudnivalókért lásd: [származtatott könyvek](derived-books.md)


