---
title: Adószámítás áttekintése
description: Ez a témakör az adószámítási funkció általános hatókörét és jellemzőit ismerteti.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 72895cc18368ebf38818f30510cec999391c7910
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394586"
---
# <a name="tax-calculation-overview"></a>Adószámítás áttekintése

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Az adószámítás egy hiperskálázható több-bérlős szolgáltatás, amely lehetővé teszi a Global Tax Engine számára, hogy automatizálja és egyszerűsítse az adómeghatározási és számítási folyamatot. Az adómotor teljesen konfigurálható. A konfigurálható elemek közé tartozik többek között az adóköteles adatmodell, az adókód, az adóalkalmazási mátrix és az adószámítási képlet. Az adómotor a Microsoft Azure alapszolgáltatási platformon fut, és modern technológiát és exponenciális méretezhetőséget kínál.

Az adószámítás integrálva van a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management szolgáltatásokkal. Végül integrálva lesz a Dynamics 365 Project Operations, Dynamics 365 Commerce és más saját és harmadik féltől származó alkalmazásokkal is.

> [!IMPORTANT]
> Ha engedélyezi az Adószámítás funkciót, előfordulhat, hogy a kapcsolódó adatokon végzett egyes műveletek a szolgáltatási adatokat karbantartó adatközponttól eltérő adatközpontban kerülnek végrehajtásra. Az adószámítás engedélyezése előtt tekintse át a [Felhasználási](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) feltételeket. Az Ön személyes adatainak védelme fontos a számunkra. További információt az [adatvédelmi nyilatkozatban találhat](https://go.microsoft.com/fwlink/?LinkId=521839).

Az Adószámítás egy mikroszolgáltatás-alapú adómotor, amely exponenciális skálázhatóságot kínál, és a következő feladatok elvégzésében segít:

- Automatikusan meghatározza a helyes forgalmiadó-csoportot, a tételek forgalmiadó-csoportját és az adókódokat egy továbbfejlesztett meghatározási mechanizmus segítségével.
- Több adóregisztrációs szám támogatása egy jogi személyen belül, és a helyes adóregisztrációs szám automatikus meghatározása az adóköteles ügyleteknél.
- Támogatja az adók meghatározását, kiszámítását, könyvelését és elszámolását az átutalási megbízások esetében.
- Konfigurálható adószámítási képletek és feltételek meghatározása az Ön egyedi üzleti követelményeihez.
- Az adómegállapítási és -számítási megoldás megosztása a jogi személyek között a karbantartási erőfeszítések megtakarítása és a hibák elkerülése érdekében.
- Támogatja az ügyfél és a szállító adóregisztrációs számának meghatározását.
- Támogatási lista kódjának meghatározása.
- Adószámítási paraméterek támogatása az adójoghatóságok szintjén.

Az Adószámítás használatához telepítse az Adószámítás bővítményt a projektjéből a Microsoft Dynamics Lifecycle Services oldalon. Ezután fejezze be a beállítást a [Regulatory Configuration Serviceban](https://marketing.configure.global.dynamics.com/), és engedélyezze az adószámítást a Pénzügyek és Supply Chain Managementben. További tájékoztatás: [Első lépések az adószolgáltatással](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Elérhetőség

Az adószámítás a 10.0.21-es verziótól kezdve általában minden ügyfél számára elérhető a termelési környezetben.

Az új funkciókat továbbra is szállítani fogják. Gyakran ellenőrizze a legfrissebb kiadási tervet, hogy tájékozódjon a támogatott funkciók lefedettségéről és terjedelméről.

Az adószámítás a következő Azure-földrajzi területeken van telepítve. Az ügyfelek igényei alapján további Azure földrajzi területeket is hozzáadunk.

- Ázsia és a csendes-óceáni térség
- Ausztrália
- Kanada
- Európa
- Japán
- Egyesült Királyság
- Egyesült Államok

> [!NOTE]
> Az Adószámítás nem támogatja a Dynamics 365 korábbi verzióit, például a Dynamics AX 2012-t vagy a Dynamics 365 helyben telepített verzióit.

## <a name="data-flow"></a>Adatáramlás

Az alábbiakban a tTax-számítás adatáramlási folyamatát vázoljuk fel. 

1. Az RCS-ben megtekintheti és importálhatja az adóköteles dokumentummodell-konfigurációkat és a modelltérkép-konfigurációkat. Ha egy speciális forgatókönyvhöz ki kell bővítenie a konfigurációkat, lásd: [Adatmezők hozzáadása az adókonfigurációkban.](tax-service-add-data-fields-tax-configurations.md)
2. Az RCS-ben hozzon létre vagy tartson fenn adójellemzőket. Az adózási funkciókat az adókulcsok és az adóalkalmazhatósági szabályok karbantartására használhatja.
3. Az adófunkciók beállításának befejezése után tegye közzé az adókonfigurációkat és az adófunkciókat az RCS-ből a globális adattárban.
4. A Pénzügyek menüpontban válassza ki, hogy melyik adófunkció beállítási verzióját kívánja használni egy adott jogi személy esetében.
5. A pénzügyek és a Supply Chain Management területén a szokásos módon végezze a tranzakciókat. Ha adószámításra van szükség, az ügyfél összegyűjti az információkat a tranzakcióból, például az értékesítési vagy a beszerzési rendelésből, és az információkat hasznos teherként csomagolja. Ezt követően az adó kiszámítására vonatkozó kérést küldenek.
6. Az ügyféltől beérkezik az adószámítási kérelem, és a számítás befejeződik. Az adózási eredményt ezután visszaküldi az ügyfélnek.
7. A Dynamics 365 ügyfél megkapja az adózási eredményt, és az adószámítás eredményét egy forgalmiadó-oldalon jeleníti meg.

## <a name="supported-transactions"></a>Támogatott tranzakciók

Az adószámítás tranzakciónként engedélyezhető. 

A 10.0.21-es verzió a következő tranzakciókat támogatja: 

- Értékesítés

    - Értékesítési ajánlat
    - Értékesítési rendelés
    - Visszaigazolás
    - Kitárolási lista
    - Szállítólevél
    - Értékesítési számla
    - Jóváírás
    - Visszárurendelés
    - Fejléc vegyes költségek
    - Sor vegyes költsége

- Beszerzés

    - Beszerzési rendelés
    - Visszaigazolás
    - Bevételezések listája
    - Termékbevételezés
    - Beszerzési számla
    - Fejléc vegyes költségek
    - Sor vegyes költsége
    - Jóváírás
    - Visszárurendelés
    - Beszerzési igénylés
    - A beszerzési igénylési sor vegyes díja
    - Ajánlatkérés
    - Ajánlatkérés fejlécének vegyes díja
    - Ajánlatkérés sorának vegyes díja

- Készlet

    - Átmozgatási rendelések – szállítás
    - Átmozgatási rendelés – bevételezés

## <a name="supported-countriesregions"></a>Támogatott országok/régiók

Az adószámítás jogi személyenként engedélyezhető. 

A 10.0.21-es verzió a jogi személyek elsődleges címének következő országait/régióit támogatja:

- Ausztria
- Belgium
- Dánia
- Észtország
- Finnország
- Franciaország
- Németország
- Magyarország
- Izland
- Olaszország
- Lettország
- Litvánia
- Hollandia
- Norvégia
- Lengyelország
- Svédország
- Svájc
- Egyesült Királyság
- Egyesült Államok

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Az adószolgáltatás első lépései](./global-get-started-with-tax-calculation-service.md)

[Több adószám](./emea-multiple-vat-registration-numbers.md)

[Adófunkció támogatása átmozgatási rendeléshez](./tasks/tax-feature-support-for-transfer-order.md)

[Hogyan építsünk bővítményt az adószolgáltatásban?](./tax-service-add-data-fields-tax-integration-by-extension.md)
