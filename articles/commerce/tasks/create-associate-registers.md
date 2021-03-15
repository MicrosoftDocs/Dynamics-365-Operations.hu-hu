---
title: " Pénztárgépek létrehozása és hozzárendelése"
description: Ez az eljárás azt mutatja be, hogy hogyan lehet pénztár (POS) jegyzéket létrehozni.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2415945c5a8f73e095627d638fcc572c50ffe8ca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964895"
---
# <a name="create-and-associate-registers"></a> Pénztárgépek létrehozása és hozzárendelése

[!include [banner](../includes/banner.md)]

Ez az eljárás azt mutatja be, hogy hogyan lehet pénztár (POS) jegyzéket létrehozni. Ez az eljárás az USRT bemutatócéget használja.

1. Ugorjon a Kiskereskedelem és kereskedelem > Csatorna beállítás > Pénztár beállítás > Pénztárgépek lehetőségre.
2. Kattintson az Új elemre.
3. Adjon meg egy azonosítót az új jegyzékre vonatkozóan a Pénztárgép száma mezőben.
    * A regisztrációs azonosító általában tartalmazza azokat a kódokat, amelyek segítik a pénztárgép az üzlethez és az üzleten belüli helyéhez történő hozzárendelését, amelyhez tartozik.  
4. Írjon be egy jól felismerhető nevet a Név mezőbe a pénztárhoz.
5. Az Üzlet száma mezőben adjon meg, vagy válasszon ki egy értéket.
6. A Hardverprofil mezőben adjon meg, vagy válasszon ki egy értéket.
    * A hardverprofilok segítségével meghatározhatja azokat a perifériás eszközöket, amelyek olyan pénztárhoz vannak csatlakoztatva, mint például a pénztárfiók és a nyugtanyomtató.  
7. A Vizuális profil mezőben adjon meg vagy válasszon ki egy értéket.
    * A vizuális profilok segítségével adhatja meg a POS háttérben látható képeket, a bejelentkezési oldalt, illetve a POS-nál használt témákat.  
8. Írjon be egy értéket az EFT POS pénztárgép száma mezőbe.
    * Az EFT POS pénztárgép száma arra szolgál, hogy tájékoztassa a fizetés feldolgozóját arról, hogy melyik fizetési terminál küld engedélyezésre vonatkozó kéréseket. Ezt az értéket gyakran a „Terminál azonosítója” vagy „TID” néven nevezik. A TID általában a fizetésre szolgáló eszközön lévő címkén található.  
9. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]