---
title: Vevői fizetési mód kialakítása
description: Fizetési mód létrehozása vevői kifizetésekhez.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab035c6268b701c78da32d589e99ece38c31781d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546801"
---
# <a name="establish-customer-method-of-payment"></a>Vevői fizetési mód kialakítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Fizetési mód létrehozása vevői kifizetésekhez. Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési mód pontra.
2. Kattintson az Új lehetőségre.
3. A Fizetési mód mezőben adjon meg egy azonosítót a kifizetés módjához.
    * A Fizetési mód azonosítója feltüntetésre kerül a számlákon és a kifizetéseken, így gondoskodjon arról, hogy világosan rögzíti a fizetés jellegét, illetve a bankszámlát.  
4. Adjon meg egy leírást a Leírás mezőben.
5. Válassza ki a kifizetés feladásához szükséges kifizetési állapotot.
    * Vevői kifizetés létrehozásakor az csak akkor adható fel, ha a fizetési állapot megegyezik az Ön által itt megjelölt fizetési állapottal.  
6. Válassza ki az ügyfélkifizetések létrehozásának módját a számlákhoz.
    * Ezt a lehetőség kizárólag fizetési javaslat futtatása esetén kerül alkalmazásra. Fizetési javaslat akkor használható fel vevői kifizetésekhez, ha állandó átutalást alkalmaz, és a pénzeszközöket a vevő bankszámláiról emeli le.  
7. Jelölje ki a kifizetés típusát.
    * A fizetéstípus segítségével tudja meghatározni, hogy a fizetés kapcsán sor kerül-e valamilyen ellenőrzésre.  
8. Válassza ki, milyen számlatípusokra adhatnak fel kifizetést.
    * Általában a bank volna kijelölve ennél a lehetőségnél.  
9. Válassza ki, melyik bankszámlára kerüljön rögzítésre ez a kifizetés.
10. Adja meg a banki tranzakció típusát a bankja által használt fizetési típus azonosításához.
    * A banki tranzakciótípus a banki egyeztetési folyamat során használható fel, az egyeztetés megkönnyítése érdekében.  
11. Válassza ki, hogy ez a kifizetés ideiglenesen felad-e áthidaló számlára.
    * Ha szeretné kipróbálni, hogy mennyi egy kifizetés banki átfutása, használja az Áthidaló funkciót. A kifizetés így ideiglenesen, a banki átfutás idejére, a Főkönyvi számlára kerül feladásra, mely időt követően a kifizetés az Ön által itt megjelölt bankszámlára kerül.  
12. Adja meg az áthidaló feladáshoz használt fő számlát.
    * Ez az a fő számla, amelyre - áthidalás esetén - a rendszer ideiglenesen feladja a kifizetést.  
13. A fájlformátum lap használatával adja meg az elektronikus kifizetésekhez való beállítást.
14. A fizetés ellenőrző lapján határozza meg a kötelező mezőket.
    * Ha például előírja, hogy az összes ilyen fizetési módú kifizetés letétbe kerüljön, úgy válassza ezt a lehetőséget a lapon.  
15. A fizetési attribútumok lapján határozza meg, mely fizetési attribútumokat kívánja használni ehhez a fizetési módhoz.
16. Kattintson a Mentés gombra.

