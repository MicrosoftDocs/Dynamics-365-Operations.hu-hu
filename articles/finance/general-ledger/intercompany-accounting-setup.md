---
title: Vállalatközi könyvelés beállítása
description: Ez a témakör ismerteti a vállalatközi könyvelés beállításának módját annak érdekében, hogy a vállalatközi naplók használhatók legyenek főkönyvi felosztásokhoz és pénzügyi naplókhoz, például a napi naplókhoz, szállítóiszámla-naplókhoz és fizetési naplókhoz.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: kfend
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9c9914d9fff3407d8d469fe2ed27a9bfd6b26a50
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720365"
---
# <a name="intercompany-accounting-setup"></a>Vállalatközi könyvelés beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a vállalatközi könyvelés beállításának módját annak érdekében, hogy a vállalatközi naplók használhatók legyenek főkönyvi felosztásokhoz és pénzügyi naplókhoz, például a napi naplókhoz, szállítóiszámla-naplókhoz és fizetési naplókhoz.

Vállalatközi naplók számos helyzetben létrehozhatóak, például napi naplók, szállítóiszámla-naplók, főkönyvi felosztások és központosított kifizetések számára. Az esetek engedélyezéséhez, be kell állítania a vállalatközi könyvelést.

## <a name="define-main-accounts"></a>Fő számlák meghatározása
Először, létre kell hoznia a vállalatközi fő számlákat, hogy használhassa az Esedékes ide és az Esedékes innen lehetőségeket a számlázási bejegyzésekből. Tanácsos minden egyes vállalatnál egyedi fő számlát használni, az egyeztetés és a vállalatközi számlázási bejegyzések törlésének egyszerűsítése érdekében. Ha egy kereskedelmi partnert, vagy ellenoldali dimenziót használ a vállalatközi fél azonosítására, a dimenziót megadhatja fix dimenzióként a főszámlán, amely a vállalatközi számlázásban van megadva. Amikor a fő számlákat állítja be, állítsa a **Főszámla típusa** mezőt **Mérleg** értékre a **Fő számlák** oldalon.

## <a name="define-journal-names"></a>Naplónevek meghatározása
Ezután meg kell adnia egy naplónevet. Állítsa a **Naplótípus** mezőt **Napi** értékre a **Naplónevek** oldalon. Rendkívül hasznos lehet, ha a vállalatközi könyveléshez egy adott naplónevet használ.

## <a name="define-intercompany-accounting-setup"></a>Vállalatközi könyvelés beállításának meghatározása
A **Vállalatközi könyvelés** oldal használatával létrehozhatók azon jogiszemély-párok, amelyek tranzakciókat bonyolíthatnak le egymással. A Vállalatközi könyvelési beállítása meg van osztva, így a beállítások minden jogi személyen belülről láthatók. Új jogiszemély-pár létrehozásánál ellenőrizze, hogy tudja-e, melyik jogi személy minősül meghatározás szerint kiindulási vállalatnak és melyik célvállalatnak. Vállalatközi tranzakciók megadásakor a tranzakció határozza meg, mely jogi személy kezdeményezése vagy indítja a tranzakciót. Vegyük például, hogy a vállalatközi könyvelés USMF-re (kiindulási) and USSI-re (van) van beállítva. Ha egy felhasználó az USSI-nél aktív, és megad egy vállalatközi tranzakciót az USMF-rel, a tranzakció nem kerül feladásra, mert a vállalatközi könyvelésben csak az USMF van kezdeményezőként meghatározva. Amennyiben mindkét vállalat kezdeményezhet tranzakciót, úgy egy második jogiszemély-párt is létre kell hoznia a fordított beállítás céljára. 

Válassza ki a **Tartozik számla (Kiinduló)** és **Követel számla (Cél)** elemeket mind a kezdeményező, mind a cél jogi személynek. Határozza meg, mely **Napló neve** lesz használatos akkor, ha a tranzakció a célvállalatban jön létre. A kiindulási vállalat naplója már ismert, mert a vállalatközi tranzakció létrehozásakor a felhasználó kiválasztotta. 

Végül válassza ki, mely jogi személyhez kerül a könyvelés a kiegészítő összegek után - ilyen például a készpénzfizetési engedmény, illetve a központosított fizetések realizált nyereségeinek/veszteségeinek elszámolása. 

Fordított kapcsolat az első jogiszemély-pár létrehozása után könnyen beállítható a **Vállalatközi könyvelés** oldalon a **Fordított kapcsolat létrehozása** gomb segítségével. A fordított pár létrehozásakor a célvállalat adatai átmásolódnak a kiindulási vállalathoz, és fordítva. A célvállalat számára meghatározott napló megmarad. A legtöbb szervezet ugyanazokat az elnevezési szokásokat használja a naplónevekhez, hogy a naplónév azonos legyen. Ha a naplónév eltér, figyelmeztetés jelenik meg a mezőben, amely jelzi, hogy a napló nem létezik, és hogy ki lehet választani egy másik naplót.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
