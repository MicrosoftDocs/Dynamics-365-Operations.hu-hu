---
title: Adószámítás áttekintése
description: Ez a cikk bemutatja az adószámítási képesség általános hatókörét és szolgáltatásait.
author: EricWangChen
ms.date: 09/08/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.search.form: TaxIntegrationTaxServiceParameters
ms.openlocfilehash: a193db82b2b079c1e10fbfb6bfde7aa43b18bc4a
ms.sourcegitcommit: dbb997f252377b8884674edd95e66caf8d817816
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2022
ms.locfileid: "9465166"
---
# <a name="tax-calculation-overview"></a>Adószámítás áttekintése

[!include [banner](../includes/banner.md)]

Az adószámítás egy hiperskálázható több-bérlős szolgáltatás, amely lehetővé teszi a Global Tax Engine számára, hogy automatizálja és egyszerűsítse az adómeghatározási és számítási folyamatot. Az adómotor teljesen konfigurálható. A konfigurálható elemek közé tartozik többek között az adóköteles adatmodell, az adókód, az adóalkalmazási mátrix és az adószámítási képlet. Az adómotor a Microsoft Azure alapszolgáltatási platformon fut, és modern technológiát és exponenciális méretezhetőséget kínál.

Az adószámítás integrálva van a Dynamics 365 Pénzügy és a Dynamics 365 Supply Chain Management. Végül integrálva lesz a Dynamics 365 Project Operations, Dynamics 365 Commerce és más saját és harmadik féltől származó alkalmazásokkal is.

> [!IMPORTANT]
> Ha engedélyezi az Adószámítás funkciót, előfordulhat, hogy a kapcsolódó adatokon végzett egyes műveletek a szolgáltatási adatokat karbantartó adatközponttól eltérő adatközpontban kerülnek végrehajtásra. Az adószámítás engedélyezése előtt tekintse át a [Felhasználási](https://go.microsoft.com/fwlink/?linkid=2156043) feltételeket. Az Ön személyes adatainak védelme fontos a számunkra. További információt az [adatvédelmi nyilatkozatban találhat](https://go.microsoft.com/fwlink/?LinkId=521839).

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

- Ázsia és a csendes-óceáni régió
- Ausztrália
- Brazília
- Kanada
- Európa
- Franciaország
- India
- Japán
- Dél-Afrika
- Svájc
- Egyesült Arab Emírségek
- Egyesült Királyság
- Egyesült Államok

> [!NOTE]
> Az Adószámítás nem támogatja a Dynamics 365 korábbi verzióit, például a Dynamics AX 2012-t vagy a Dynamics 365 helyben telepített verzióit.

## <a name="versions"></a>Verziók
Javasoljuk, hogy importálja és állítsa be az adószámítás konfigurációját a Pénzügy vagy az Ellátásilánc-kezelés verziójának megfelelő verzióval.

| Pénzügyi vagy ellátásilánc-kezelés verziója | Adókonfigurációs verzió               |
| --------------- | --------------------------------------- |
| 10.0.30         | Adószámítási konfiguráció 40.55.239 |
| 10.0.29         | Adószámítási konfiguráció 40.55.236 |
| 10.0.28         | Adószámítási konfiguráció 40.54.234 |
| 10.0.27         | Adószámítási konfiguráció 40.54.234 |


## <a name="data-flow"></a>Adatáramlás

Az adószámítási folyamat szerkezeti része. 

1. Az RCS-ben megtekintheti és importálhatja az adóköteles dokumentummodell-konfigurációkat és a modelltérkép-konfigurációkat. Ha egy speciális forgatókönyvhöz ki kell bővítenie a konfigurációkat, lásd: [Adatmezők hozzáadása az adókonfigurációkban.](tax-service-add-data-fields-tax-configurations.md)
2. Az RCS-ben hozzon létre vagy tartson fenn adójellemzőket. Az adózási funkciókat az adókulcsok és az adóalkalmazhatósági szabályok karbantartására használhatja.
3. Az adófunkciók beállításának befejezése után tegye közzé az adókonfigurációkat és az adófunkciókat az RCS-ből a globális adattárban.
4. A Pénzügyek menüpontban válassza ki, hogy melyik adófunkció beállítási verzióját kívánja használni egy adott jogi személy esetében.
5. A pénzügyek és a Supply Chain Management területén a szokásos módon végezze a tranzakciókat. Ha adószámításra van szükség, az ügyfél összegyűjti az információkat a tranzakcióból, például az értékesítési vagy a beszerzési rendelésből, és az információkat hasznos teherként csomagolja. Ezt követően az adó kiszámítására vonatkozó kérést küldenek.
6. Az ügyféltől beérkezik az adószámítási kérelem, és a számítás befejeződik. Az adózási eredményt ezután visszaküldi az ügyfélnek.
7. A Dynamics 365 ügyfél megkapja az adózási eredményt, és az adószámítás eredményét egy forgalmiadó-oldalon jeleníti meg.

## <a name="supported-transactions"></a>Támogatott tranzakciók

Az adószámítás tranzakciónként engedélyezhető. 

Az alábbi táblázat felsorolja a megfelelő verzióban támogatott tranzakciókat.

| Verzió | Tranzakciók |
|---------|--------------|
| 10.0.29 | Időszaki naplók |
| 10.0.28 | Szállító fizetési naplója<br> Vevői kifizetési napló | 
| 10.0.26 | Általános naplók<br> Szállítói számla naplója |
| 10.0.23 | Szabadszöveges számla |
| 10.0.21| Értékesítés<br><ul><li>Értékesítési ajánlat</li><li>Értékesítési rendelés</li><li>Megerősítés</li><li>Kitárolási lista</li><li>Szállítólevél</li><li>Értékesítési számla</li><li>Jóváírás</li><li>Visszárurendelés</li><li>Fejléc vegyes költségek</li><li>Sor vegyes költsége</li></ul>Beszerzés<br><ul><li>Beszerzési rendelés</li><li>Visszaigazolás</li><li>Bevételezések listája</li><li>Termékbevételezés</li><li>Beszerzési számla</li><li>Fejléc vegyes költségek</li><li>Sor vegyes költsége</li><li>Jóváírás</li><li>Visszárurendelés</li><li>Beszerzési igénylés</li><li>A beszerzési igénylési sor vegyes díja</li><li>Ajánlatkérés</li><li>Ajánlatkérés fejlécének vegyes díja</li><li>Ajánlatkérés sorának vegyes díja</li></ul>Készlet<ul><li>Átmozgatási rendelések – szállítás</li><li>Átmozgatási rendelés – bevételezés</li></ul>|

## <a name="supported-countriesregions"></a>Támogatott országok/régiók

Az adószámítás támogatott honosítási szolgáltatásokkal futtatható. A következő táblázat felsorolja a jogi személy elsődleges címében található országokat/régiókat.

| Verzió | Ország/régió |
|---------|----------------|
| 10.0.26 | - Kína <br>- Cseh Köztársaság<br>- Spanyolország |
| 10.0.24 | Mexikó |
| 10.0.23 | - Thaiföld <br>- Japán <br>- Malajzia <br>- Szingapúr |
| 10.0.22 | - Ausztrália<br>- Bahreini <br>- Kanada<br>- Egyiptomi <br>- Hongkong (KKT) <br>Kuvait <br>- Új-Zéland <br>- Omán <br>- Katar <br>- Szaúd-arab <br>- Dél-Afrika <br>- Egyesült Arab Emírségek |
| 10.0.21 | - Ausztria <br>- Belgium <br>- Dánia <br>- Észt <br>- Finnország <br>- Franciaország <br>- Németország <br>- Magyarország <br>- Izland <br>- Írország <br>- Olaszország <br>- Lettország <br>- Litván <br>- Hollandia <br>- Norvégia <br>- Lengyelország <br>- Svédország <br>- Svájc <br>- Egyesült Királyság <br>- Amerikai Egyesült Államok |

Bármely olyan ország/régió esetén, amelyet nem a Microsoft honosított, az adószámítás más globális szolgáltatásokkal is engedélyezhető és futtatható.

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Az adószolgáltatás első lépései](./global-get-started-with-tax-calculation-service.md)

[Több adószám](./emea-multiple-vat-registration-numbers.md)

[Adófunkció támogatása átmozgatási rendeléshez](./tasks/tax-feature-support-for-transfer-order.md)

[Hogyan építsünk bővítményt az adószolgáltatásban?](./tax-service-add-data-fields-tax-integration-by-extension.md)
