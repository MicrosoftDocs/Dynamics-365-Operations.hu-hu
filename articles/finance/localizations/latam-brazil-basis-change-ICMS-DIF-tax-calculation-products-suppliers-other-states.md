---
title: Más államok szállítói termékeire vonatkozó ICMS-DIF adószámítások alapváltozása
description: Ez a témakör az ICMS-DIF adótípus számításának konfigurációját írja le, amikor egy pénzügyi bizonylatot a brazil Grande do Sul (RS) vagy São Bizonylato (SP) államban érkezik.
author: Kai-Cloud
ms.date: 06/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218649"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>A más államok szállítói termékeire vonatkozó ICMS-DIF adószámításokban alapváltozás (kettős alap)

Ez a témakör az **ICMS-DIF** adótípus számításának konfigurációját írja le, amikor egy pénzügyi bizonylatot a brazil Grande do Sul (RS) vagy São Bizonylato (SP) államban érkezik.

Az állami törvényben leírott definíciók szerint az összegyűjtött Mercadorias e De Mercadorias e Serviços (ICMS) szabálynak követnie kell ezt a szabályt:

*Beszedni szükséges ICMS* = ([(*Művelet* összege - *forrásból származó ICMS*) ÷ (1 – *ICMS %* belső)] × *ICMS %* belső) – *ICMS-összeg a forrásból*

## <a name="example"></a>Példa

Az RS-államban brazil vállalat pénzügyi bizonylatot kap egy beszerzésről az sp államban. A vállalatnak az RS állam (18 százalék) és a sp állam (12 százalék) között meg kell gyűjtenie az ICMS százalékos eltérését. Az alapot ugyanakkor az előző szabály szerint kell kiszámítani.

- **Művelet összege:** 1 000,00 Brazil reál (R$ 1 000,00)
- **ICMS-interstate:** R$ 120,00
- **ICMS-százalék AZ RS-állapotban:** 18 százalék
- **AZ RS-államban beszedhető ICMS-** (\[(1000 – 120) ÷ (1 – 0,18)\] × 0,18) – 120 = R$ 73,17 

## <a name="resolution"></a>Megoldás

Az ICMS-DIF eltérésnek az RS-állam szabályai szerinti kiszámításához a következő módon kell áfakódokat és áfacsoportokat beállítani:

1. Hozzon létre egy áfakódot a 12 százalékos ICMS fogadására (a másik államban). Ezzel a kóddal lehet regisztrálni a szállítótól visszakövethető adó összegét.
2. Hozzon létre egy áfakódot az ICMS-DIF összegyűjtéséhez. Ennek az áfakódnak 18 százalékos összeggel kell lennie (a saját államban), hogy meghatározza a 18 és 12 százalék közötti különbséget. Állítsa az adótípust **ICMS-DIF típusúra**. Ezt az áfakódot a következő módon kell meghatározni a számítási paraméterek között:

    - Az Eredet **mezőben** válassza a Bruttó **összeg százaléka lehetőséget**.
    - A Számítás **alapja mezőben** válassza ki a **soronkénti nettó összeget**.
    - Az adózási kód megadása úgy, hogy 3 értékű **pénzügyi értéket tartalmazzon**. Ilyen módon a pénzügyi **könyvek** modul engedélyezésekor automatikusan létrejön a korrekciós tranzakció.
    - Az áfacsoport konfigurációjában válassza **ki az ICMS-DIF** áfakódhoz az "Use **tax**" beállítást.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>A különbözeti adókulcs használata két alap ICMS-DIF áfakód konfigurációjában

A korábban leírt beállítások **használata után a kettős alapszabályban ki lesz számítva az ICMS-DIF** áfakód. Ugyanakkor a névleges adókulcs 18 százalék lesz, amely eltér az egyszerű alapszabály 6 százalékos mértéktől. Ez a különbség inkonzisztenciát okoz a pénzügyi bizonylatok és az adóbevallások során. Microsoft Dynamics A 10.0.29-es pénzügyi verzió 365-ös verziójával engedélyezheti, **hogy az inkonzisztenciát eltávolítsa az ICMS-DIF** **kettős** alapeset funkciójában.

- Az előző szakaszban található **lépéseken kívül válassza ki az ICMS 12** **áfakódot az Áfa áfamezőben**.
- **Az ICMS-DIF** áfakód adómátumának beállítása 18 százalékra. A **Százalék/Összeg** mezőben a névleges adókulcs 6 százalék lesz.

> [!NOTE]
> Az **ICMS-DIF** **és az ICMS 12** áfakódnak ugyanabban az áfacsoportban kell lennie.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Alapváltozás (kettős adóalap) más államok iCMS-DIF adószámításaiban a nem adófizető ügyfelek (DIFAL) termékeire

**Kettős alapszámítás engedélyezése az ICMS-DIFAL** **számára** az értékesítési tranzakcióknál a Funkciókezelésben, hogy a más államból származó, nem adófizető ügyfelek számára történő kereskedelemben támogassák az alapváltási ICMS-DIF szolgáltatást. Az ICMS-DIF minta áfakódja az értékesítési rendelési és a szabadszöveges számlatranzakciókban lesz hatályos.

**A (Brazília) kettős alapszámítás engedélyezése az ICMS-DIFAL IPI-esetekhez** **funkcióhoz** a Funkciókezelésben, hogy olyan helyzetek is támogatott legyen, amikor a más államból származó nem adófizető ügyfelekkel történő kereskedelem felelős a Proxyto sobre Produtos Industrializados (IPI) számára is. Az IPI-áfakód adóösszegét a rendszer felismeri és alkalmazza az ICMS-DIFAL adóalapban.

- Az értékesítési rendelés vagy **a szabadszöveges számla fejlécében, a Pénzügyi adatok gyorskódok oldalon a** **Végső felhasználó beállítást Igen beállításra kell** állítani **.**
- A beszerzési rendelés vagy szállítói számla fejlécében **a** **Pénzügyi adatok gyorsététen a Használat és felhasználás** beállítást Igen beállításra kell **állítani.**
