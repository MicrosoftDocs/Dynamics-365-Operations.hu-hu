---
title: Tárgyieszköz-tranzakciók beállításai
description: Ez a témakör a tárgyieszköz-tranzakciók létrehozásának különféle módszereit mutatja be.
author: ShylaThompson
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3540cf17050a953a97c7291a1bcbe5ebf6fb670e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815716"
---
# <a name="fixed-asset-transaction-options"></a>Tárgyieszköz-tranzakciók beállításai

[!include [banner](../includes/banner.md)]

Ez a témakör a tárgyieszköz-tranzakciók létrehozásának különféle módszereit mutatja be.

A tárgyi eszközök modul integrálható a főkönyv, a követelések és a kinnlevőségek modullal. Arra is lehetőség van, hogy a készletbenkezelésben található cikkek belső felhasználás céljából átkerüljenek a tárgyi eszközök modulba.

## <a name="accounts-payable"></a>Kötelezettségek
Tárgyieszköz-tranzakciókat a Naplóbizonylat képernyőn is lehet rögzíteni. Ez a lap a Számlanapló lapról nyitható meg. A Naplóbizonylat képernyőt a Számla-jóváhagyási napló képernyőről is megnyithatja. Az Ellenszámla típusa mezőben válassza a Tárgyi eszközök lehetőséget. Aztán az Ellenszámla típusa mezőben válassza ki a tárgyi eszköz számát. A Tárgyi eszközök lapon adjon meg egy értéket a Tranzakció típusa és a Könyv mezőben.

## <a name="accounts-receivable"></a>Kinnlevőségek
Megadhat Tárgyieszköz-tranzakciókat a Szabadszöveges számla képernyőn.  A Szabadszöveges számla képernyőn a Számlasorok rácsban válasszon ki egy sortételt. Kattintson a Soradatok gyorslapra. Adja meg a tárgyi eszköz számát és könyvét a kivezetési tranzakcióhoz. Szabadszöveges számláknál a tárgyieszköz-tranzakció típusa mindig Kivezetés – eladás.

## <a name="procurement-and-sourcing"></a>Beszerzés és forrás
Tárgyieszköz-tranzakciókat a Beszerzési rendelés képernyőn is lehet rögzíteni. Adja meg az értékesítési rendelés létrehozásához szükséges adatokat, majd kattintson az OK gombra. A Beszerzési rendelés képernyőn kattintson a Soradatok gyorslapra. Ezt követően a Tárgyi Eszközök lapon adhatja meg a tárgyieszköz-csoportra vonatkozó adatokat. 

Egy létező tárgyi eszközre vonatkozó beszerzési tranzakció feladásához adja meg a tárgyi eszköz számát, könyvét és tranzakciótípusát. A tárgyi eszköz ezek nélkül az információk nélkül nem adható fel. Egy új tárgyi eszközre vonatkozó beszerzési tranzakció feladásához jelölje be az Új tárgyi eszköz? jelölőnégyzetet, majd válassza ki azt a tárgyieszköz-csoportot, amelyhez az új tárgyi eszközt társítani szeretné. Azonban a sorhoz tartozó tárgyieszköz-mezők egyike sem érhető el, ha a cikk egy olyan készletmodell-csoportban van, amely elszámolóáras készletmodellt használ. Emellett a Tárgyi eszközök paraméterei képernyőn meghatározott lehetőségek szintén meghatározzák, hogy fel lehet-e adni a beszerzési tranzakciót a beszerzési modulokból. 

Ha egy beszerzési rendelést vagy a Készlet a tárgyi eszközökhöz naplót használja tárgyi eszközök beszerzéséhez, az a készletértéket is befolyásolja.

## <a name="general-ledger"></a>Főkönyv
A tárgyieszköz-tranzakciók bármely típusát fel lehet adni az Általános napló képernyő következő naplóiba: ( > ) vagy ( > ) . Emellett a tárgyieszköz-naplókat is használhatja a tárgyieszköz-tranzakciók feladásához.

## <a name="options-for-entering-fixed-asset-transaction-types"></a>Tárgyieszköz-tranzakciótípusok rögzítésének lehetőségei


| Tranzakció típusa                    | Modul                   | Beállítások                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Beszerzés, beszerzés helyesbítése | Tárgyi eszközök             | Tárgyi eszközök, készlet a tárgyi eszközökhöz   |
|                                     | Főkönyv           | Általános napló                           |
|                                     | Kötelezettségek         | Számlanapló, számla-jóváhagyási napló |
|                                     | Beszerzés és forrás | Beszerzési rendelés                            |
| Értékcsökkenés                        | Tárgyi eszközök             | Tárgyi eszközök                              |
|                                     | Főkönyv           | Általános napló                           |
| Kivezetés                            | Tárgyi eszközök             | Tárgyi eszközök                              |
| ** **                               | Főkönyv           | Általános napló                           |
| ** **                               | Kinnlevőségek      | Szabadszöveges számla                         |


A tárgyi eszközök értékcsökkenési időszakok fennmaradó értéke nem frissül, ha az értékcsökkenési tranzakció típusú naplósort manuálisan hozták létre vagy importálták egy adatentitáson keresztül. Ez az érték frissül, ha az értékcsökkenés javaslati folyamata segítségével hozták létre a naplósort.

További tudnivalókért lásd: [Tárgyieszköz-integráció](fixed-asset-integration.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]