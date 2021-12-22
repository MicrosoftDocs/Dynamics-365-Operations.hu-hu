---
title: Tárgyieszköz-tranzakciók beállításai
description: Ez a témakör a tárgyieszköz-tranzakciók létrehozásának különféle módszereit mutatja be.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c5530bb7b0472aad75ec04c00ba828b8efb877d
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891572"
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

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Tárgyieszköz-tranzakciótípusok rögzítésének lehetőségei


| Tranzakció típusa                    | Modul                   | Beállítások                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Beszerzés, beszerzés helyesbítése | Tárgyi eszközök             | Tárgyi eszközök, készlet a tárgyi eszközökhöz   |
|                                     | Főkönyv           | Általános napló                           |
|                                     | Kötelezettségek         | Számlanapló, számla-jóváhagyási napló |
|                                     | Beszerzés és forrás | Beszerzési rendelés                            |
| Értékcsökkenés                        | Tárgyi eszközök             | Tárgyi eszközök                              |
|                                     | Főkönyv           | Általános napló                           |
| Kivezetés                            | Tárgyi eszközök             | Tárgyi eszközök                              |
|                                     | Főkönyv           | Általános napló                           |
|                                     | Kinnlevőségek      | Szabadszöveges számla                         |

A fennmaradó érték nem frissül a tárgyi eszköz értékcsökkenési időszakaihoz, amikor az értékcsökkenési tranzakciótípusú naplósor manuálisan jön létre, vagy adategységen keresztül importálódik. A fennmaradó érték akkor frissül, amikor az értékcsökkenési javaslat folyamatot használják a naplósor létrehozására.

További tudnivalókért lásd: [Tárgyieszköz-integráció](fixed-asset-integration.md).

A rendszer megakadályozza, hogy az értékcsökkenést kétszer ugyanarra az időszakra könyvelje. Ha például két felhasználó külön-külön készít értékcsökkenési javaslatokat januárra, akkor az első felhasználó értékcsökkenése az első naplóban kerül könyvelésre. Amikor a második felhasználó értékcsökkenést könyvel a második naplóban, a rendszer ellenőrzi az értékcsökkenés utolsó futtatásának dátumát, és másodszor nem könyvel értékcsökkenést ugyanarra az időszakra.

### <a name="transactions-that-require-a-different-voucher-number"></a>Más utalványszámot igénylő tranzakciók

A következő tárgyieszköz-tranzakciók különböző bizonylatszámokat fognak használni:

- Egy eszközön további beszerzés történik, és „elmaradt” értékcsökkenés kiszámítására kerül sor.
- Egy eszköz fel van osztva.
- Bekapcsolásra kerül az értékcsökkenés kivezetéskori kiszámítására használandó paraméter, és ezután a eszköz kivezetésre kerül.
- Egy eszköz szolgáltatási dátuma a beszerzési dátum elé esik. Emiatt egy értékcsökkenési kiigazítás lesz feladva.

> [!NOTE]
> Tranzakciók bevitelekor győződjön meg arról, hogy minden tranzakció ugyanarra a tárgyi eszközre vonatkozik. A bizonylat nem lesz feladva, ha egynél több tárgyi eszközt tartalmaz, még akkor is , ha az **Új bizonylat** mező értéke **Csak egy bizonylatszám** a Főkönyv rész **Naplónevek** oldalán. Ha a bizonylatban egynél több tárgyi eszköz szerepel, akkor megjelenik a következő üzenet: „Csak egy tárgyieszköz-tranzakció lehet bizonylatonként”, és nem lehet feladni a bizonylatot.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
