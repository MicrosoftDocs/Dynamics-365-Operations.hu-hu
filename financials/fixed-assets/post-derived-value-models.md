---
title: "Feladás származtatott könyvekkel"
description: "Ez a cikk a származtatott könyvek használatának módját ismerteti."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: aaacf596f2ea1107a53647d779e9d2b6c37ab530
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="post-with-derived-books"></a>Feladás származtatott könyvekkel

[!include[banner](../includes/banner.md)]


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

Ha felad egy, az ÉM 1 könyvet használó tárgyi eszközre vonatkozó beszerzést, akkor a program a beszerzést nem csak az ÉM 1-be, hanem ÉM 2 származtatott könyvbe is feladja. Mindkét tárgyi eszközök könyv állapota frissül Nyitottra.

> [!NOTE]                                                                                                         
> Ha nem használ származtatott értékcsökkenési könyveket, akkor a VM 1 értékmodellbe és VM 2 könyvbe is fel kell adni a tárgyieszköz-beszerzést.

További információért lásd: [Származtatott könyvek](derived-books.md)




