---
title: Egy helyhez tartozó ütemezés létrehozása
description: Ez az eljárás bemutatja az egy helyhez tartozó, még el nem indított termelési rendelések ütemezését.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0db5095020bc14d56ae3680e7d0caa68789180e
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469282"
---
# <a name="create-a-schedule-for-a-site"></a>Egy helyhez tartozó ütemezés létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja az egy helyhez tartozó, még el nem indított termelési rendelések ütemezését.  Az USMF bemutatócég segítségével végzik el ezt az eljárást.


## <a name="identify-production-orders-that-are-not-started"></a>Határozza meg az el nem indított termelési rendeléseket
1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést az „1”-es értékkel ellátott Hely mezőben.
    * Az 1 egy helyet jelöl az USMF-ben. Ha nem használ USMF-et, válasszon ki egy helyet a saját vállalatai közül.  
3. Nyissa meg az Állapot oszlopszűrőt.
4. Alkalmazzon szűrőt a „Állapot mezőben” az „Ütemezett értékkel” a „pontosan” szűrési operátor használatával.

## <a name="create-a-schedule"></a>Hozzon létre egy ütemezést
1. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
2. A Művelet panelen kattintson az Ütemezés elemre.
3. Kattintson a Feladatok ütemezése lehetőségre.
4. Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól visszafelé” lehetőséget.
5. Válassza a Nem lehetőséget a Véges kapacitás mezőben.
6. Válassza a Nem lehetőséget a Véges anyag mezőben.
7. Kattintson az OK gombra.
    * Ez eltarthat egy ideig.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Az ütemezett termelési rendelés eredményének megtekintése.
1. A listában jelölje meg a kiválasztott sort.
    * Bármelyik sort megjelölheti.  
2. A Művelet panelen kattintson a Termelési rendelés elemre.
3. Kattintson a Minden feladat elemre.
    * Ezen a lapon megtekintheti a feladatok listáját. Az ütemezés lapon megtekintheti a feladat kezdő és záró dátumát.  
4. Kattintson az Anyagok elemre.
    * Ezen a lapon megtekintheti a becsült anyagfelhasználást a termelési rendelésben és az aktuális rendelkezésre álló készletben szereplő műveletekre vonatkozóan.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]