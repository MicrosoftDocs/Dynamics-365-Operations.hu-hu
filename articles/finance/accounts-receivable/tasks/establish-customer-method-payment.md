---
title: Vevői fizetési mód kialakítása
description: Ez a témakör ismerteti a vevők a fizetési mód létrehozását ügyfélkifizetésekhez
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b9960c3fdf0d65be19e28dbb41913a310ae7530
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140214"
---
# <a name="establish-customer-method-of-payment"></a>Vevői fizetési mód kialakítása

[!include [banner](../../includes/banner.md)]

Ez a témakör ismerteti a vevők a fizetési mód létrehozását ügyfélkifizetésekhez Ez a feladat az USMF bemutatócéget használja.

1. A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Fizetés beállítása > Fizetési módok** elemre.
2. Válassza az **Új** lehetőséget.
3. A **Fizetési mód** mezőben adjon meg egy azonosítót a kifizetés módjához. A Fizetési mód azonosítója feltüntetésre kerül a számlákon és a kifizetéseken, így gondoskodjon arról, hogy világosan rögzíti a fizetés jellegét, illetve a bankszámlát.  
4. Adjon meg egy leírást a **Leírás** mezőben.
5. Válassza ki a kifizetés feladásához szükséges kifizetési állapotot. Vevői kifizetés létrehozásakor az csak akkor adható fel, ha a fizetési állapot megegyezik az Ön által itt megjelölt fizetési állapottal.  
6. Válassza ki az ügyfélkifizetések létrehozásának módját a számlákhoz. Ezt a lehetőség kizárólag fizetési javaslat futtatása esetén kerül alkalmazásra. Fizetési javaslat akkor használható fel vevői kifizetésekhez, ha állandó átutalást alkalmaz, és a pénzeszközöket a vevő bankszámláiról emeli le.  
7. Jelölje ki a kifizetés típusát. A fizetéstípus segítségével tudja meghatározni, hogy a fizetés kapcsán sor kerül-e valamilyen ellenőrzésre.  
8. Válassza ki, milyen számlatípusokra adhatnak fel kifizetést. Általában a bank volna kijelölve ennél a lehetőségnél.  
9. Válassza ki, melyik bankszámlára kerüljön rögzítésre ez a kifizetés.
10. Adja meg a banki tranzakció típusát a bankja által használt fizetési típus azonosításához. A banki tranzakciótípus a banki egyeztetési folyamat során használható fel, az egyeztetés megkönnyítése érdekében.  
11. Válassza ki, hogy ez a kifizetés ideiglenesen felad-e áthidaló számlára. Ha szeretné kipróbálni, hogy mennyi egy kifizetés banki átfutása, használja az Áthidaló funkciót. A kifizetés így ideiglenesen, a banki átfutás idejére, a Főkönyvi számlára kerül feladásra, mely időt követően a kifizetés az Ön által itt megjelölt bankszámlára kerül.  
12. Adja meg az áthidaló feladáshoz használt fő számlát. Ez az a fő számla, amelyre - áthidalás esetén - a rendszer ideiglenesen feladja a kifizetést.  
13. A **Fájlformátum** lap használatával adja meg az elektronikus kifizetésekhez való beállítást.
14. A **Fizetés ellenőrzése** lapon határozza meg a kötelező mezőket. Ha például előírja, hogy az összes ilyen fizetési módú kifizetés letétbe kerüljön, úgy válassza ezt a lehetőséget a lapon.  
15. A **Fizetési attribútumok** lapon határozza meg, mely fizetési attribútumokat akarja használni ehhez a fizetési módhoz.
16. Válassza a **Mentés** lehetőséget.

