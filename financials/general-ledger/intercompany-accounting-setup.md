---
title: "Vállalatközi könyvelés beállítása"
description: "Ez a témakör ismerteti, hogy a vállalatközi naplók a főkönyvi felosztásban és pénzügyi naplókra, például a napi naplókat, szállítói számla naplók és kifizetési naplók használható vállalatközi könyvelés beállítása."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Vállalatközi könyvelés beállítása

Ez a témakör ismerteti, hogy a vállalatközi naplók a főkönyvi felosztásban és pénzügyi naplókra, például a napi naplókat, szállítói számla naplók és kifizetési naplók használható vállalatközi könyvelés beállítása.

Vállalatközi naplók is létrehozható különböző helyzetekben, például a napi naplókat, szállítói számla naplók, főkönyvi felosztásban és központosított fizetési. Az esetek engedélyezéséhez, be kell állítania a vállalatközi könyvelést.

## <a name="define-main-accounts"></a>Fő számlák meghatározása
Először, létre kell hoznia a vállalatközi fő számlákat, hogy használhassa az Esedékes ide és az Esedékes innen lehetőségeket a számlázási bejegyzésekből. Tanácsos minden egyes vállalatnál egyedi fő számlát használni, az egyeztetés és a vállalatközi számlázási bejegyzések törlésének egyszerűsítése érdekében. Ha a kereskedelmi partnerekkel vagy partner dimenzió vállalatközi fél azonosítására használ, ezt a dimenziót határozhat meg rögzített dimenziónak a fő számla meghatározása a vállalatközi könyvelés. A fő számlák beállításakor meg kell a **fő típusa** mező **mérleg** meg a **fő számlák** oldalon.

## <a name="define-journal-names"></a>A Naplónevek megadása
Ezután meg kell adnia egy naplónevet. Állítsa be a **naplótípus** mező **napi** a a **Naplónevek** oldalon. Rendkívül hasznos lehet, ha a vállalatközi könyveléshez egy adott naplónevet használ.

## <a name="define-intercompany-accounting-setup"></a>Adja meg a vállalatközi könyvelés beállítása
A **vállalatközi könyvelés** lap egymással a párok is transact jogalanyok létrehozására szolgál. A vállalatközi könyvelési beállítás meg van osztva, így a telepítő minden jogi személy belül látható. Két új jogi személy létrehozása esetén ellenőrizze, hogy milyen jogi személy minősül, és a célvállalat származó vállalat tudomást. Vállalatközi tranzakciók megadásakor a tranzakció határozza meg, mely jogi személy kezdeményezése, vagy a tranzakció származó. Például a vállalatközi könyvelés van beállítva (származó) USMF és USSI (cél). Ha a felhasználó aktív a USSI és USMF tartalmazó vállalatközi tranzakciók belép, a tranzakció nem könyveli, mert a vállalatközi könyvelés csak USMF van definiálva a megbízó alatt. Amennyiben mindkét vállalat egy tranzakció is származnak, szüksége lesz egy második jogalany pár a kölcsönös beállítás létrehozásához. 

Válassza ki a **tartozik számla (által fizetendő)** és **követel számla (mert a)** mind a kiinduló és a jogi személy. Határozza meg, amely **neve** lesz, ha a tranzakció létrejön a célvállalat. A napló a származó vállalat már ismert, mert be van jelölve a felhasználó által, a vállalatközi tranzakciók létrehozásakor. 

Végül válassza ki, mely jogi személy kap a kiegészítő összegeket, például a készpénzfizetési engedmény és központosított fizetési realizált nyereség/veszteség elszámolása. 

Kölcsönös kapcsolat könnyen beállíthatja a a **vállalatközi könyvelés** lap segítségével a **kölcsönös kapcsolat létrehozása** után az első pár jogi személy létrehozása gombra. A kölcsönös kulcspár létrehozásakor a célvállalatnak az a adatainak másolása kiindulási vállalatát és fordítva. A célvállalat definiálva a napló marad. A legtöbb szervezet használja az azonos elnevezési a Naplónevek, úgy, hogy a napló neve megegyezik. Ha eltér a napló nevét, figyelmeztetés jelenik meg a mező jelzi, hogy a napló nem létezik, és kiválasztható egy másik naplóban.


