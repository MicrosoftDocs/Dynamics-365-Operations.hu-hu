---
title: "Elavult szolgáltatások"
description: "Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve."
author: sericks007
manager: AnnBe
ms.date: 03/22/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e629673c3a923ec74809e276ec39464bfacda124
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="removed-or-deprecated-features"></a>Eltávolított vagy elavult szolgáltatások

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör a Dynamics 365 for Finance and Operations alkalmazásból eltávolított szolgáltatásokat írja le, illetve azokat, amelyek elavultak.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!Note]
> A Dynamics 365 for Finance and Operations 2017. júliusi kiadása a 8-as platformfrissítéssel verziótól kezdve minden eltávolított és elavult szolgáltatás esetében feltüntetjük a telepítések típusát. Az ebben a témakörben említett korábbi kiadások kivétel nélkül csak a felhőtelepítést támogatták.

## <a name="dynamics-365-for-finance-and-operations-80-with-platform-update-15"></a>Dynamics 365 for Finance and Operations 8.0 15-ös platformfrissítéssel
Nincsenek funkciók eltávolítva vagy elavulttá nyilvánítva ebben a kiadásban. A 15-ös platformfrissítés halmozott és tartalmazza a 13-as platformfrissítés, a 14-es platformfrissítés a 15-ös platformfrissítés új vagy módosított szolgáltatásait.

## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 12-es platformfrissítéssel

### <a name="personalized-product-recommendations"></a>Személyre szabott termékajánlások 
2018. február 15-től a kiskereskedők már nem jeleníthetnek meg személyre szabott termékjavaslatok a pénztári (POS) eszközökön. További információ: [Személyre szabott termékajánlatok áttekintése](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/personalized-product-recommendations).  

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük.  |
| **Felváltotta másik szolgáltatás?**   | Szám 2018 tavaszától azonban a funkció újbóli bevezetését tervezzük annak érdekében, hogy kihasználhassunk egy új ajánlási szolgáltatást.   |
| **Érintett területek**         | Személyre szabott termékajánlások a POS felületén.                                                    |
| **Telepítési beállítás**              | Mind                                                                                      |
| **Állapot**                         |Eltávolítva 2018. február 15-én. Ez hatással van a Dynamics 365 for Operations 1611 és újabb verzióit használó ügyfelekre is.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Elektronikus jelentéskészítési (ER) funkciók listájának kibővítése
A lehetőség az ER kifejezésszerkesztőben használandó egyéni funkciók bevezetésére (további tájékoztatás: [Elektronikus jelentéskészítési funkciók listájának kibővítése](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) már nem támogatott. Az ER API-kon végrehajtott módosítások következtében az ER Kifejezésszerkesztő beépített függvényeit meghívó API belsővé vált, és többé nem lehet kiterjeszteni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Kódzárolási kezdeményezés  |
| **Felváltotta másik szolgáltatás?**   | Egyik sem. Amikor csak új beépített függvényre van szükség, új bővítési kérelmet kell benyújtani az ER-keretrendszer csapatnak.<br><br>Ideiglenes megoldásként, amíg az ER-csapat fejleszti a kért függvényt, a szükséges logika egy egyéni alkalmazásosztály metódusaként is programozható. Ez a metódus egy ER kifejezésben érhető el a hozzáadott ER adatforrás tulajdonságaként az **Application\Class** típusnak, amely az egyéni alkalmazásosztályra hivatkozik.  |
| **Érintett területek**         | Elektronikus jelentéskészítési keretrendszer                                                      |
| **Telepítési beállítás**              | Mind                                                                                      |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations, Enterprise edition 7.3 verzióban.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Készlet a cikkcsoport és készlet a készletdimenzió korosítási jelentései szerint

Ezt a két jelentést már nem támogatja a Finance and Operations. Ehelyett a **Készletkorosítási** jelentés használható a felhasználói élmény fokozása érdekében.

|   |  |
|--------------|-----------------------|
| **Megszűnés oka**       | Máshol már meglévő funkció  |
| **Felváltotta másik szolgáltatás?** | Igen. A két jelentést leváltotta a **Készletkorosítási** jelentés.     |
| **Érintett területek**       | Készletkezelés, költségkezelés        |
| **Telepítési beállítás**        | Mind|
| **Állapot**                       | Elavult: A két jelentés menüpontjai el lettek távolítva a 7.3 verzióban. A jelentések kódja azonban a termékben marad. A terv szerint valamelyik jövőbeli programverzióban eltávolítjuk a kódot. |

### <a name="power-bi-content-packs-published-to-powerbicom"></a>Power PI tartalmi csomagok közzététele a PowerBI.com webhelyen
A **Költségkezelés**, a **Pénzügyi teljesítmény** és a **Kiskereskedelmi csatorna teljesítménye** tartalomcsomagok, amelyek közzé lettek téve PowerBI.com a webhelyen, elavultak a Microsoft Power BI termékfrissítéseinek következtében. A rendszerfelügyeleti képernyők, amelyeknek a segítségével ezeket a tartalmi csomagokat telepítették a PowerBI.com webhelyre, szintén elavultak a Finance and Operations megoldásban.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Microsoft Power BI termékfrissítések. |
| **Felváltotta másik szolgáltatás?**   | A Power BI tartalmi csomagok (a PowerBI.com webhelyen közzétéve) helyébe analitikai alkalmazások lépnek, amelyek az adatbázis szintjén teszik lehetővé a megoldásintegrációt. Az analitikai alkalmazásokkal kapcsolatos további tudnivalókat lásd: [Beágyazott Power BI munkaterületek](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Érintett területek**         | Költségkezelés, pénzügy és kiskereskedelem                                                                                               |
| **Telepítési beállítás**              | Csak felhő (A PowerBI.com webhellyel való integráció nem támogatott a helyszíni telepítések esetében.)                                                                                                            |
| **Állapot**                         | Elavult: A funkció eltávolításának cél időkerete 2018 2. negyedéve.    |

### <a name="standard-ui-in-data-management-workspace"></a>Normál kezelőfelület az adatkezelési munkaterületen

A normál adatkezelési kezelőfelület a régebbi kezelőfelület, amely a felhasználók számára alapértelmezetten jelenik meg, amikor megnyitják az adatok kezelése munkaterületet.

|   |  |
|------------------|-------------------------|
| **Elavulás/eltávolítás oka** | Befektetünk az új felhasználói élmény nyújtásában az új felhasználói felület segítségével.             |
| **Felváltotta másik szolgáltatás?**   | Az új felhasználói felület neve *Bővített nézet*, és a régi felhasználói felületet váltja le.            |
| **Érintett területek**         | Adatkezelési munkaterület                                                     |
| **Telepítési beállítás**              | Mind                                                                           |
| **Állapot**                         | Elavult: A funkció eltávolításának cél időkerete 2018 2. negyedéve. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Fogyasztási adó, áfa, szolgáltatási adó India esetében

Ezeket az adókat már magában foglalja az indiai GST.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Ezeket az adókat már magában foglalja az indiai GST.                          |
| **Felváltotta másik szolgáltatás?**            | Indiai GST                                                              |
| **Érintett területek**                  | Adó                                                                     |
| **Telepítési beállítás**                       | Minden modul                                                   |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |    

### <a name="file-validation-utility-fvu-for-india"></a>Fájlellenőrzési segédprogram (FVU) India esetében

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Vevői használat hiánya.                                                  |
| **Felváltotta másik szolgáltatás?**            | Nincs                                                                      |
| **Érintett területek**                  | Indiai adóelőleg                                                  |
| **Telepítési beállítás**                       | Minden modul                                                                    |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |        

### <a name="tdstcs-certificate-for-india"></a>TDS/TCS-tanúsítvány India esetében

A felhasználók a kormányzati portálról tölthetik le.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Vevői használat hiánya.                                                  |
| **Felváltotta másik szolgáltatás?**            | Nincs                                                                      |
| **Érintett területek**                  | Indiai adóelőleg                                                  |
| **Telepítési beállítás**                       | Minden modul                                                                   |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Exportálási/importálási (EXIM) ösztönző rendszer India esetében


|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Vevői használat hiánya.                                                  |
| **Felváltotta másik szolgáltatás?**            | Nincs                                                                      |
| **Érintett területek**                  | Importálás és exportálás                                                       |
| **Telepítési beállítás**                       | Minden modul                                                                    |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Személyre szabott termékajánlások 
2018. február 15-től a kiskereskedők már nem jeleníthetnek meg személyre szabott termékjavaslatok a pénztári (POS) eszközökön. További információ: [Személyre szabott termékajánlatok áttekintése](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/personalized-product-recommendations).  

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük.  |
| **Felváltotta másik szolgáltatás?**   | Szám 2018 tavaszától azonban a funkció újbóli bevezetését tervezzük annak érdekében, hogy kihasználhassunk egy új ajánlási szolgáltatást.   |
| **Érintett területek**         | Személyre szabott termékajánlások a POS felületén.                                                    |
| **Telepítési beállítás**              | Mind                                                                                      |
| **Állapot**                         |Eltávolítva 2018. február 15-én. Ez hatással van a Dynamics 365 for Retail 7.2 és újabb verzióit használó ügyfelekre is. |


## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Dynamics 365 for Finance and Operations, Enterprise Edition 2017 júliusi kiadás 8-es platformfrissítéssel

### <a name="warehouse-mobile-devices-portal"></a>Raktári mobileszközportál

A Raktári mobileszközportál (Warehouse mobile devices portal – WMDP) egy különálló összetevő volt a helyszíni saját telepítésekhez. Ezt az összetevőt már nem támogatja a Finance and Operations. A WMDP funkció helyére egy natív alkalmazás lépett, amely javítja a felhasználói élményt.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció.       |
| **Felváltotta másik szolgáltatás?**   | Igen. Ezt a funkciót felváltotta a Finance and Operations – Raktárkezelés funkció. Ha további információt szeretne a beállításról és az előfeltételekről, lásd a következőt: [A Microsoft Dynamics 365 for Finance and Operations – Raktárkezelés telepítése és konfigurálása](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/install-configure-warehousing-app). |
| **Érintett területek**         | Raktárkezelés, szállításkezelés     |
| **Telepítési beállítás**              | A Raktári mobileszközportál (Warehouse mobile devices portal – WMDP) egy különálló összetevő volt a helyszíni saját telepítésekhez.               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Továbbfejlesztett banki egyeztetési szabály kézi egyeztetéshez

Az egyeztetési munkalapon a dokumentumok kézi egyeztetéséhez egy egyeztetési szabályt használtak.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás.                                                                         |
| **Felváltotta másik szolgáltatás?**   | Szám Az oszlopszűrési lehetőségeket kell használni az egyeztetendő dokumentumok keresésére. |
| **Érintett területek**         | Készpénz- és bankkezelés                                                               |
| **Telepítési beállítás**              | Mind                                                                                    |
| **Állapot**                         | Eltávolítva 2017 júliusában.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 3-as platformfrissítéssel

### <a name="aeb-payment-formats-for-spain"></a>Spanyol AEB fizetési formátumok

A Consejo Superior Bancario fizetési formátumok átutalási fájlok bankhoz történő küldésére voltak használatosak vevői és szállítói kifizetések esetén. Ezen formátumok tartalmát az Asociación Española de Banca határozta meg. A következőket fedi le: Cuaderno 19, 32, 58, 34.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                                  |
| **Felváltotta másik szolgáltatás?**   | Igen, az ISO20022 átutalási és beszedési formátumok Spanyolország esetében |
| **Érintett területek**         | Kötelezettség és kinnlevőség                                    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Banki átutalásos kifizetések Litvánia esetében

A banki átutalásos kifizetések létrehozása és nyomtatása a fizetési átutalás (LT) exportformátumban történt Litvánia vonatkozásában. A litván piac 2005-ben kezdte el a LITAS egységesített elektronikus bankrendszert használni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Litvánia esetében     |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>BBS Direkte Remittering fizetési formátumok Norvégia esetében

A BBS Direkte Remittering fizetési formátumok a következőket tartalmazzák: vevői fizetés beszedésének exportálása (beszedési megbízás) és a válaszüzenet importálása.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.  |
| **Felváltotta másik szolgáltatás?**   | A Norvégiában rendelkezésre álló, AvtaleGiro vevői fizetési formátum használható beszedési megbízási üzenetek létrehozására. A visszaigazoló üzenetek importálása a jövőbeli kiadásokban kerül bevezetésre. |
| **Érintett területek**         | Kötelezettség és kinnlevőség   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Számlatükör eszköz Spanyolország esetében

Ez az eszköz akkor használatos, ha a számlatükör esetében jelentős változtatásokra van szükség Spanyolországban. A felhasználók importálhatják az új számlatükröt Microsoft Excel vagy a szöveges formátumban, valamint importálhatják a pénzügyi kimutatásokat is.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás                                                  |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                             |
| **Érintett területek**         | Főkönyv                                                 |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="dom80-payment-format-for-belgium"></a>Belga Dom80 fizetési formátum

Hagyományos fizetési formátum fizetés beszedéséhez (beszedési megbízási).

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                          |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO 20022 beszedési megbízási fizetési formátum Belgium esetében.         |
| **Érintett területek**         | Kinnlevőségek                                            |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>DTA/EZAG fizetési formátumok Svájc esetében

A DTA/EZAG formátumok az ESR rendszer integrált részét alkotják, mert rendelkezhetnek hivatkozási számmal. Mivel a hivatkozási számok nem kötelezők, ezért bármilyen szállítói fizetés feldolgozható ezen formátumok használatával. Ezeket a formátumokat olyan vállalatok használják, amelyeknek a „Postfinance”-től eltérő helyen van bankszámlája.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Svájc esetében   |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>EDIFACT-DIRDEB fizetési formátum Ausztria esetében.

EDIFACT-DIRDEB fizetési formátum fizetés beszedéséhez (beszedési megbízás).

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                          |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO 20022 beszedési megbízási fizetési formátum Ausztria esetében         |
| **Érintett területek**         | Kinnlevőségek                                            |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="edivat-for-belgium"></a>EDIVAT Belgium esetében

EDIVAT a biztonságos levelezésen keresztüli elektronikus nyilatkozat elavult belga szabványa. A Microsoft Dynamics AX 2012 megtartja a "csak olvasásra" megoldást annak érdekében, hogy a régebbi adatokhoz hozzá lehessen férni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez a funkció már nincs használatban.                           |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                             |
| **Érintett területek**         | Főkönyv                                                 |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>eGiro EDIFACT CREMUL fizetési importformátum Norvégia esetében

Az eGiro az ENSZ EDIFACT CREMUL (Multiple Credit Advice Message) nemzetközi szabványon alapszik, amely a vevői kifizetések automatikus feladásához használatos. A Microsoft Dynamics AX rendszerben az eGiro egy vevői kifizetés importformátumaként van megvalósítva.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                                                     |
| **Felváltotta másik szolgáltatás?**   | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                       |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                            |

### <a name="external-inventory-for-poland"></a>Külső készlet Lengyelország esetében

Szállítótól beszerzés nélkül, értékesítésre átvett áruk bizonylata. A külső készleten kezelt áruk, amelyek a normál készletet nem érintik, és automatikusan eladhatóak, majd később megvásárolhatók. Ez a folyamat tényleges készletmozgást hoz létre.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Másik szolgáltatás váltotta fel                                    |
| **Felváltotta másik szolgáltatás?**   | Igen, a bejövő szállítmány alapfunkciója                |
| **Érintett területek**         | Kötelezettségek, készletkezelés                         |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Pénzügyi beszámolók létrehozása Kelet-Európa esetében

Egy eszköz szolgál a könyvelési és adójelentések adatgyűjtésének beállításához és az adatok XLS vagy DOC jelentéssablonba való exportálásához

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás                                                                            |
| **Felváltotta másik szolgáltatás?**   | Szám Az eszközt elektronikus jelentési konfigurációk fogják leváltani a jövőbeli kiadásokban. |
| **Érintett területek**         | Főkönyv                                                                           |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Vevői kifizetési tranzakciók importálása Finnország esetében

Kiválaszthat egy olyan importálási formátumot a finn fizetésekhez, amely a vevői kifizetési tranzakciókat importálja egy bank által biztosított külső fájlból.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                                                     |
| **Felváltotta másik szolgáltatás?**   | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                       |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>A Finnországra vonatkozó fizetési tranzakciók importálása a főkönyvi naplóba

Finnországra vonatkozó, specifikus formátum, amellyel könyvelési tranzakciók importálhatóak a főkönyvbe.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                                                     |
| **Felváltotta másik szolgáltatás?**   | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                       |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integráció az Isabel-hez szinkronizált (CIS) rendszerekkel Belgium esetében

Az Isabel az elektronikus banki ügyintézés európai rendszere, Belgiumban de facto szabványnak minősül.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az Isabel-klienssel való integráció már nincs forgalomban.   |
| **Felváltotta másik szolgáltatás?**   | Szám A már nem használt fizetési formátumok helyébe ISO20022 átutalási fizetési formátum lépett Belgium esetében. |
| **Érintett területek**         | Kötelezettségek     |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>A számlatükör és a számviteli szabályok módosulása Spanyolország esetében

Ez a funkció a számlatükör és a számviteli szabályok változásaihoz használatos Spanyolországban esetében. Leképezi a számlákat, hogy segítsen a régi számlatükröt az új számlatükörré alakítani, és összehasonlítja az előző pénzügyi évet az új pénzügyi évvel még akkor is, ha azokhoz eltérő számlaszámokat rendeltek.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás                                                  |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                             |
| **Érintett területek**         | Főkönyv                                                 |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori szállítói fizetési formátum

Hagyományos olasz fizetési formátum átutalásokhoz.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                          |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Olaszország esetében         |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="payment-export-formats-for-estonia"></a>Kifizetésexportálás formátuma Észtország esetében

Banki fizetés exportálása a Telehansa és Teleservice formátumot használja.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Észtország esetében       |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="payment-file-archive-for-norway"></a>Fizetési fájlarchívum Norvégia esetében

Amikor fizetési fájlok jönnek létre, a fájlarchívum automatikusan archivál minden létrehozott fájlt, még akkor is fájlokat korábban írták vagy olvasták.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Másik szolgáltatás váltotta fel                                        |
| **Felváltotta másik szolgáltatás?**   | Igen. Elektronikus jelentéskészítési archivált feladatok                            |
| **Érintett területek**         | Kötelezettségek, kinnlevőségek, a szervezet felügyelete |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.     |

### <a name="payment-import-formats-for-estonia"></a>Kifizetésimportálás formátuma Észtország esetében

Banki fizetés importálása a TeleTeenus formátumot használja.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                                                    |
| **Felváltotta másik szolgáltatás?**   | Szám A formátumok helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                        |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                             |

### <a name="payroll-information-in-human-resources"></a>Bérlistaadatok az Emberi Erőforrásokban

Emberi Erőforrások Bérlistaadatai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a funkciót az alapvető Bérlista és az Emberi Erőforrások lapokok váltotta fel.  |
| **Felváltotta másik szolgáltatás?**   | A **Juttatások** és a **Bevételek** oldalakon, valamint az egyéb kapcsolódó, korábban az amerikai Bérszámfejtésben levő oldalakon újrakonfigurálást végeztünk, így ezek most az Emberi erőforrások alapkonfiguráció részei, ezért a külső bérlisták feldolgozását segítik. Ez a funkció a **Humán Erőforrások 1** \> **Bérlista**-konfigurációs kulcs használatával érhető el. |
| **Érintett területek**         | Emberi Erőforrások, Bérlista   |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva.    |

### <a name="performance-management-goal-workflow"></a>Teljesítménymenedzsment, célok munkafolyamata

A teljesítménymenedzsment a célok kezelését tartalmazza, és integrálja a teljeseítményellenőrzést.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítménymenedzsment át lett tervezve, és a célok oldalainak száma csökkent a folyamat egyszerűsítése érdekében.                 |
| **Felváltotta másik szolgáltatás?**   | Szám A célok láthatók a vezetők számára az Vezetők önkiszolgáló portálján; ezeket a vezető módosíthatja és megtekintheti. |
| **Érintett területek**         | Emberierőforrás-menedzselés       |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>PostGirot és a Postgirot Utland fizetési formátumok Svédország esetében

PostGirot és a Postgirot Utland fizetési formátumok Svédország esetében.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Svédország esetében        |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="radio-frequency-identifier"></a>Rádiófrekvenciás azonosító

A rádiófrekvenciás azonosítás (Radio Frequency Identification – RFID) egy olyan adatgyűjtési technológia, amely az azonosítási adatok tárolásához elektronikus címkéket használ, az azonosítási adatok beolvasásához pedig nem közvetlen rálátású olvasót.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony vevői használat és korlátozott szolgáltatáskészlet.   |
| **Felváltotta másik szolgáltatás?**   | Nincs                                              |
| **Érintett területek**         | Készletgazdálkodás                            |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Állami számlák számozására vonatkozó jelentés Lettország esetében

A lett jogszabályok szigorú szabályokat írnak elő az értékesítési számlák számozására vonatkozóan. A funkciók segítségével egyedi számokat lehet az értékesítési számlákhoz rendelni, a felhasználó vagy felhasználói csoport alapján. Ezután lehet létrehozni egy jelentést vagy egy XML-fájlt. A felhasznált számlaszámokról jelentést is lehet nyomtatni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az állami számlák számozását már nem kell fenntartani. A felhasznált számlaszámokra vonatkozó jelentésre már nincs szükség. |
| **Felváltotta másik szolgáltatás?**   | Nincs       |
| **Érintett területek**         | Kinnlevőségek    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Valamely vállalat vezetője és főkönyvelője nevének beállítása Litvánia esetében

A vállalat vezetőjének és főkönyvelőjének nevét a vállalati adatok között lehet megadni, és fel lehet használni különböző, helyi nyomtatott jelentésekben.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Másik szolgáltatás váltotta fel                                     |
| **Felváltotta másik szolgáltatás?**   | Igen, a tisztviselők beállítása ugyanerre a célra használható.   |
| **Érintett területek**         | Kötelezettségek, Kinnlevőségek, Készpénz- és bankkezelés |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="shipping-carrier-interface"></a>Szállítmányozói felületek

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció   |
| **Felváltotta másik szolgáltatás?**   | A szállításkezelés részlegesen lecserélte |
| **Érintett területek**         | Értékesítés és marketing, Készletkezelés  |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva.  |

### <a name="telepay-payment-formats-for-norway"></a>TelePay fizetési formátumok Norvégia esetében

TelePay fizetési formátumok közé tartozik a szállítói fizetés exportálása (átutalás) és a vevői kifizetési gyűjtemény (beszedési megbízás).

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                                                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum és AvtaleGiro vevői kifizetési formátum Norvégia esetében |
| **Érintett területek**         | Kötelezettség és kinnlevőség                                                          |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Szállítói fizetésexportálási formátumok Finnország esetében

Finnországban két formátum érhető el fizetések exportálásához. LM02 (FI) belföldi fizetésekhez használható, az LUM2 (FI) pedig külföldi fizetésekhez.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Finnország esetében       |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="warehouse-management-ii"></a>Raktárkezelés II

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A korábban a **Készletkezelés** modulban elérhető Raktárkezelés II megoldás (WMS II) ugyanazokkal a funkciókkal rendelkezik, mint a Microsoft Dynamics AX 2012 R3 verzióban kiadott **Raktárkezelés** modul.                                                                         |
| **Felváltotta másik szolgáltatás?**   | A Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 és Microsoft Dynamics AX 2012 R3 CU9 verziókban kiadott **Raktárkezelés** modul váltja fel a Raktárkezelés II szolgáltatást. Az új modul több speciális funkcióval és rugalmasabb raktárkezelési folyamatokkal rendelkezik, mint a Raktárkezelés II funkció. |
| **Érintett területek**         | Készletkezelés, értékesítés és marketing, beszerzés és forrás   |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva.    |

### <a name="worker-reminders-in-human-resources"></a>Dolgozói emlékeztetők az Emberi Erőforrásokban

Emberi Erőforrások Bérlistaadatai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat                                                           |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                  |
| **Érintett területek**         | Emberi erőforrások                                                     |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva |

### <a name="workflow-for-creating-goals"></a>Célok létrehozásának munkafolyamata

A munkavállalók céljai létrehozásának kezelésére vonatkozó munkafolyamat a számos olyan munkafolyamat egyike, amely rendelkezésre állt a teljesítménykezelési folyamat koordinálásának elősegítésére.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítménymenedzsment teljesen átalakult a Microsoft Dynamics 365 for Finance and Operations alatt.     |
| **Felváltotta másik szolgáltatás?**   | Az átalakított teljesítménymendzsment funkciója segítségével jobban lehet felügyelni a célok tartalmát, az előrehaladás nyomon követéséhez használt méréseket és a kiegészítő dokumentumok csatolását. A célok sablonként tárolhatók, és ezután újra felhasználhatók. Ezen funkció segítségével gyorsabban beállíthatók további célok az alkalmazottak számára. |
| **Érintett területek**         | Emberierőforrás-menedzselés                 |
| **Állapot**                         | A Dynamics 365 for Operations 1611-es verziójában el lett távolítva. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Szállítói számla módosításainak érvénytelenítésére vonatkozó képesség

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Teljesítménynövekedés.        |
| **Felváltotta másik szolgáltatás?**   | Nincs                             |
| **Érintett területek**         | Kötelezettségek               |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában. |

### <a name="aif-axd-and-axbc-integrations"></a>AIF, AxD és AxBC integrációja

Az Alkalmazásintegrációs keretrendszerben (AIF-ben) adatok cserélhetőek ki külső rendszerekkel, szolgáltatásként kitett üzleti logikán keresztül. A Dynamics AX dokumentumokon és .NET Business Connector-on (AxBC) alapuló szolgáltatásokat tartalmaz. Dokumentumok XML használatával hozhatóak létre. Az XML által tartalmazott fejlécadatok hozzáadásával *üzenet* hozható létre, amely a Dynamics AX rendszerbe vagy rendszerből átvihető. Dokumentumok például az értékesítési rendelések és a beszerzési rendelések. Azonban szinte minden entitást (például vevőt) képviselhet dokumentum. A dokumentumokon alapuló szolgáltatások az **Axd \<Document\>** osztályokat használják.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az AIF és az AxD-k architektúráját nem sikerült felhőszolgáltatáshoz méretezni. A tömeges importálás során teljesítményproblémák léptek fel.                                        |
| **Felváltotta másik szolgáltatás?**   | Ezt a szolgáltatást felváltotta az Adatimportálási és -exportálási keretrendszer, amely támogatja az ismétlődő tömeges importálást/exportálást. AxBC esetén a tényleges táblák használatát javasoljuk. |
| **Érintett területek**         | AxD-k, AxBC-k és AIF   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.   |

### <a name="boms-without-bom-versions"></a>Anyagjegyzékek Anyagjegyzék-verziók nélkül

Korábban az **Anyagjegyzék-verziók** konfigurációs kulcs letiltásakor, az anyagjegyzék-verziók (BOM) minden képernyőn rejtett állapotba kerültek, és a rendszer kötelezővé tette a kiadott termékek és anyagjegyzékek közti 1:1 arányú kapcsolatot. A Dynamics AX jelenlegi verziójában az **Anyagjegyzék-verziók** konfigurációs kulcsot nem lehet letiltani.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Anyagjegyzék-verziók konfigurációs kulcsokkal való vezérlése nem méretezhető felhő környezetre. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                                      |
| **Érintett területek**         | Termékinformációk kezelése, Készletkezelés                                    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                                                          |

### <a name="brazilian-bordero"></a>Brazil borderó

Egyedi fizetési mód brazil vállalatok esetében

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Brazil borderó fizetési mód támogatása már nem része a brazil honosításnak |
| **Felváltotta másik szolgáltatás?**   | Nincs   |
| **Érintett területek**         | Kötelezettségek   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="brazilian-sintegra-statement"></a>Brazil Sintegra kivonat

Szövetségi adókimutatás az ICMS adó esetében

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez a kimutatás már nem alkalmazható néhány brazil államban. |
| **Felváltotta másik szolgáltatás?**   | Szám A felhasználók általános elektronikus jelentési eszközt használhatnak a kimutatás beállításához, ha arra bizonyos helyzetekben szükség van. |
| **Érintett területek**         | Pénzügyi könyvek    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brazil SCAN készenléti mód az NF-e esetében

A (SCAN) készenléti környezet a Nota Fiscal eletrônica (NF-e) állapotának előállítására, exportálására és importálására szolgál, amikor nem érhető el a Secretaria da Fazenda (SEFAZ) környezet.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez a készenléti módszer már nem alkalmazható minden brazil államban |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                          |
| **Érintett területek**         | Kinnlevőségek                                                         |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.              |

### <a name="business-analyzer"></a>Business Analyzer

Ez a mobilalkalmazás lehetővé teszi a felhasználók számára a kulcsfontosságú üzleti mutatók áttekintését.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel.   |
| **Felváltotta másik szolgáltatás?**   | A Microsoft Power BI Pénzügyi teljesítményfigyelő tartalmi csomagja magába foglalja a Business Analyzer alkalmazásban korábban elérhető kulcsfontosságú üzleti mutatókat. |
| **Érintett területek**         | Főkönyv      |
| **Állapot**                         | Elavult: Az üzleti elemző elavult.    |

### <a name="business-statistics"></a>Üzleti statisztikák

Üzleti statisztikai lekérdezések beállítása, amelyek segítségével elemezhető a szervezet teljesítménye.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Üzleti intelligencia (BI) elavult megközelítése, alacsony vevői használat és a korlátozott szolgáltatási kör. |
| **Felváltotta másik szolgáltatás?**   | Új Üzleti Intelligencia megoldások a Dynamics AX jelenlegi verziójában.                                      |
| **Érintett területek**         | Beszerzés és forrás, Kötelezettségek, Értékesítés és marketing, Kinnlevőségek         |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>A Számla-jóváhagyási naplóban található Dokumentum dátumának módosítása funkció

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat                                                               |
| **Felváltotta másik szolgáltatás?**   | Igen. A feladott szállítói tranzakció dokumentumdátuma módosítható. |
| **Érintett területek**         | Kötelezettségek                                                        |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>A holland ClieOp03 fizetési formátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A formátum már nem alkalmazható Hollandiában, mivel azt felváltotta a SEPA funkció. |
| **Felváltotta másik szolgáltatás?**   | SEPA exportkifizetések  |
| **Érintett területek**         | Minden modul     |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="compliance-center"></a>Megfelelési Központ

A Megfelelési Központ egy Enterprise Portal webhely volt, amely a Sarbanes-Oxley törvénnyel kapcsolatos megfelelési kezdeményezések dokumentációs követelményeinek kezelésére szolgált.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Vevői használat hiánya. A Microsoft SharePoint magában foglalja ugyanazt a képességet, ami korábban a Megfelelési Központban volt elérhető. |
| **Felváltotta másik szolgáltatás?**   | Nincs   |
| **Érintett területek**         | Megfelelés és belső ellenőrzés  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.    |

### <a name="connector-for-microsoft-dynamics"></a>Connector for Microsoft Dynamics

Ezzel az eszközzel integrálták a Microsoft Dynamics CRM rendszerből származó kulcsadatokat a Microsoft Dynamics ERP alkalmazásokba.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel. |
| **Felváltotta másik szolgáltatás?**   | Common Data Service                                      |
| **Érintett területek**         | Connector for Microsoft Dynamics                         |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Tárolóegység és a készleten lévő több dimenzió

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció |
| **Felváltotta másik szolgáltatás?**   | Igen. Az AX 2012 óta, ezt a funkciót az összesített kötegrendelések szolgáltatáskészlet váltotta fel. Ez a szolgáltatáskészlet tartalmazza az egyesített készletnézetet. |
| **Érintett területek**         | Termékinformációk kezelése, Gyártásvezérlés, Készletkezelés, Értékesítés és marketing  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában. |

### <a name="cue-group-metadata"></a>Kötegcsoport-metaadatok

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Kötegcsoportok használatával korábban egy vagy több Köteget lehetett megjeleníteni az Adatterületen. A feltöltés korlátozottsága mellett teljesítményproblémák is felléptek, mivel egy szülőűrlapon történő rekordváltoztatás a Kötegcsoport minden egyes Kötegéhez létrehozott egy lekérdezést. |
| **Felváltotta másik szolgáltatás?**   | Nincs      |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.  |

### <a name="cue-metadata"></a>Köteg-metaadatok

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A köteg-metaadatok információk számlálására vagy összesítésére korlátozódtak.    |
| **Felváltotta másik szolgáltatás?**   | Annak érdekében, hogy a modellezéshez nagyobb rugalmasságot biztosítsunk, bevezettük a csempe-metaadatokat. Modellezhet például aktuális számlálókat, navigációt, valamint fő teljesítménymutatókat (KPI-ket). A Köteg-metaadatokat közvetlenül helyettesítik a Csempeszámláló metaadatai. |
| **Érintett területek**         | Minden modul           |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában      |

### <a name="danish-check-format"></a>Dán csekkformátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A dán csekkformátum elrendezésének támogatása megszűnt, a jelentést eltávolítottuk a dán honosításból. |
| **Felváltotta másik szolgáltatás?**   | Nincs    |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="data-partitions"></a>Adatpartíciók

Az adatpartíciók az adatok logikus elkülönítését biztosítják a Microsoft Dynamics AX adatbázisában.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az adatpartíciókat a Microsoft Dynamics AX 2012 R2 változatában vezették be adatok elkülönítéséhez. Általános esetben a vállalat leányvállalatokkal rendelkezik, és egy leányvállalat adatait nem láthatja egy másik leányvállalat, annak ellenére, hogy mindkét leányvállalatot azonos informatikai részleg kezeli. Azonban további parancsfájlok és kezelési többletköltség voltak szükségesek új partíciók létrehozására és azok adatokkal való feltöltésére, és a partíció adatainak biztonsági mentésére. A felhőben, ahol hozzáférésünk van platformhoz mint szolgáltatáshoz (PaaS), adatbázis-szolgáltatáshoz (Windows Azure a Microsoft SQL adatbázis), sokkal hatékonyabb az adatbázist elkülönítési tárolóként használni, mint a elkülönítést végezni a programon belül. Függetlenül attól, hogy adatpartíció szükségesek leányvállalatoknak, több bérlőnek vagy csak mérlegelésre, úgy véljük, hogy az esetek jobban kezelhetők több Finance and Operations példánnyal. |
| **Felváltotta másik szolgáltatás?**   | Az adatpartíciókat használó vevőknek a Finance and Operations több példányát kell használniuk, ha az adatbázis szintű elkülönítése kritikus fontosságú.    |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Adatbázis és fájlmegosztás tárolása a mellékletek számára

A Microsoft Dynamics AX 2012 lehetővé tette a mellékletek tárolását az adatbázisban és a fájlmegosztásokban. Ezek a lehetőségek a továbbiakban nem támogatottak.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fájlmegosztással történő tárolás a továbbiakban már nem támogatott, mert a felhőalapú tárolási környezet nem tud kommunikálni a helyi fájlmegosztásokkal. Az adatbázia-alapú tárolás helyére az Azure Blob-tárolás lépett. Az Azure Blob-tárolás megegyezik az adatbázisban való tárolással, mivel a dokumentumok elérése csak a Dynamics 365 for Finance and Operations ügyfélképernyőkön keresztül történhet. Ez a megoldás azzal a plusz előnnyel jár, hogy olyan tárhelyet kínál, amely nem befolyásolja negatívan az adatbázis teljesítményét. A Blob-tárolás a dokumentumkezelés alapértelmezett tárolási mechanizmusa, és azonnal működik. |
| **Felváltotta másik szolgáltatás?**   | Az adatbázia-alapú tárolás helyére az Azure Blob-tárolás lépett.   |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.   |

### <a name="delimitation"></a>Elválasztás

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció hasznossága nem mutatható ki. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                     |
| **Érintett területek**         | Munkaidő és jelenlét                    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.         |

### <a name="desktop-client"></a>Asztali ügyfél

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics AX ügyfél felhasználói felületét a több platformon és eszközön való jobb felhasználhatóság érdekében újraterveztük.                      |
| **Felváltotta másik szolgáltatás?**   | Az új webes ügyfél az asztali képernyő metaadatain és programozási modelljén alapul, amelyeket egy multimédiás webes platform szolgáltatása érdekében módosítottunk. |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.   |

### <a name="direct-database-connection"></a>Közvetlen adatbázis-kapcsolat

A Dynamics AX 2012 R3 rendszerben a Retail Modern pénztár az Enterprise POS rendszerhez hasonló módon, közvetlenül tudott kapcsolódni a csatorna-adatbázishoz. Ez ráadás volt a Retail Modern pénztár Retail Server kiszolgálón keresztül kommunikáló szokásos kommunikációs módja mellett.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A közvetlen adatbázis-kapcsolathoz alacsonyabb szintű biztonsági protokollok voltak szükségesek, és elsődleges használati célja a legmagasabb szintű teljesítmény elérése volt. A Finance and Operations teljesítménybeli és biztonsági fejlesztései következtében ez a funkció több problémát okoz, mint amennyit megold. |
| **Felváltotta másik szolgáltatás?**   | Szám Jelenleg csak a szabványos Retail Server által biztosított kommunikáció támogatott.  |
| **Érintett területek**         | Csatorna-adatbázis/Retail Modern pénztár   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.  |

### <a name="dutch-swift-mt940"></a>Holland SWIFT MT940

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A honosított funkció helyett már az általános funkció használatos.                    |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt a funkciót a Továbbfejlesztett banki egyeztetés funkció váltotta fel. |
| **Érintett területek**         | Minden modul                                                                              |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL, Németország)

Ez a funkció az eXtensible Business Reporting Language (XBRL) kimenetet biztosítja, amely kifejezetten a német eBilanz rendszertan részére lett szánva.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Vevői használat hiánya.  |
| **Felváltotta másik szolgáltatás?**   | Ezt a szolgáltatást nem váltotta fel másik, azonban számos speciális, széles körű XBRL funkciókat magában foglaló XBRL csomag érthető el a német piac számára. |
| **Érintett területek**         | Management Reporter      |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="enterprise-portal-client"></a>Enterprise Portal-ügyfél

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Egy együgyfeles platform biztosított.  |
| **Felváltotta másik szolgáltatás?**   | Az új webes ügyfél az asztali képernyő metaadatain és programozási modelljén alapul, amelyeket egy multimédiás webes platform szolgáltatása érdekében módosítottunk. |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.   |

### <a name="environmental-sustainability"></a>Környezeti fenntarthatóság

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony vevői használat és korlátozott szolgáltatáskészlet.  |
| **Felváltotta másik szolgáltatás?**   | Nincs              |
| **Érintett területek**         | Megfelelés és belső ellenőrzés, Kötelezettségek  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában. |

### <a name="form-activex-and-managed-host-controls"></a>ActiveX és Felügyelt Állomás vezérlők

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az ActiveX és Felügyelt Állomás vezérlők a már megszűnt asztali ügyfélen alapulnak. |
| **Felváltotta másik szolgáltatás?**   | A bővíthető vezérlési keretrendszer támogatja új, HTML-, CSS- és JavaScript-alapú vezérlések kiépítését, továbbá Microsoft Visual Studio Tooling környezetben elsőrangú vezérlő. |
| **Érintett területek**         | Minden modul     |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Ellenőrző tranzakciók létrehozása a köteg használatával

Előjegyzés létrehozás nem lehetséges köteg használatával, azonban a felhasználó által továbbra is végrehajtható.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Nem létezik olyan képernyő, amely a köteg használatával létrehozott előjegyzési fájl tárolására és megjelenítésére alkalmas lenne. |
| **Felváltotta másik szolgáltatás?**   | Előjegyzések továbbra is létrehozhatók, ekkor a fájl mentésének helyét a felhasználó állíthatja be.   |
| **Érintett területek**         | Kötelezettségek, Kinnlevőségek, Készpénz- és bankkezelés  |
| **Állapot**                         | Eltávolítva az AX 7.0-s verziójában.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Német DTAUS kifizetési export és számlakivonat-import (összegek és tranzakciók)

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A formátum már nem alkalmazható Németországban, mivel azt felváltotta a SEPA funkció.                    |
| **Felváltotta másik szolgáltatás?**   | Igen, ez a funkció le lett cserélve a SEPA kifizetési export és a továbbfejlesztett banki egyeztetés funkciókra a számlakivontok importálásához. |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="german-dtazv-payment-format"></a>Német DTAZV fizetési formátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A formátum már nem alkalmazható Németországban, mivel azt felváltotta a SEPA funkció. |
| **Felváltotta másik szolgáltatás?**   | SEPA exportkifizetések    |
| **Érintett területek**         | Minden modul   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.    |

### <a name="german-mt940-import"></a>Német MT940 importálása

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A honosított funkció helyett már az általános funkció használatos.                    |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt a funkciót a Továbbfejlesztett banki egyeztetés funkció váltotta fel. |
| **Érintett területek**         | Minden modul                                                                              |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                           |

### <a name="german-xml-eu-sales-list"></a>Német XML-formátumú EU Értékesítési lista

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Német EU Értékesítési Lista jelentés XML-formátuma, már nem támogatott. Csak az ELMA5 szövegfájl formátumban lehet a Német Adóhivatal számára jelenteni az EU értékesítési lista jelentést. |
| **Felváltotta másik szolgáltatás?**   | Nincs         |
| **Érintett területek**         | Adó        |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="gl-ssrs-reports"></a>GL SSRS-jelentések

A következő menüpontokat tartalmazó jelentések eltávolításra kerültek: **Összegző főkönyvi kivonat**, **Részletes főkönyvi kivonat**, **Számlatükör**, **Könyvvizsgálati ellenőrzés**, **Egyenlegek** és **Egyenleglista**.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Microsoft SQL Server Reporting Services (SSRS) pénzügyi jelentéseket felváltották a Felügyeleti jelentéskészítő funkciói és az alapértelmezett jelentések. |
| **Felváltotta másik szolgáltatás?**   | Felügyeleti jelentéskészítő (a Dynamics AX jelenlegi verziójában **Pénzügyi jelentéskészítés** megjelöléssel)    |
| **Érintett területek**         | Főkönyv   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.   |

### <a name="infopart-and-formpart-metadata"></a>InfoPart és FormPart metaadatai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az InfoPart és FormPart metaadatok két különböző ügyfél számára engedélyezték Adatterületek létrehozását. |
| **Felváltotta másik szolgáltatás?**   | Fejlesztés után az InfoPart metaadatokat, amelyek egy egyszerűsített képernyődefiníciót adtak meg, Képernyővé alakítottuk. Fejlesztés után a FormPart metaadatokat, amelyek egy Képernyőre hivatkoztak, közvetlenebb hivatkozással váltottuk fel. |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.        |

### <a name="main-account-list-page"></a>Fő számla listaoldal

A jogi személy számláinak listája és kapcsolódó egyenleginformációk

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az egyenleginformációk elérhetőek a **Főkönyvi kivonat** listaoldalon, számla és dimenzió szerint.  |
| **Felváltotta másik szolgáltatás?**   | A **Fő számlák** ugyanazt a számlalistát tartalmazza, amit korábban a **Fő számla** listaoldal. A **Fő számlák** rácsnézetével egy még kisebb, rácsszerű megjelenítés is elérhető. |
| **Érintett területek**         | Főkönyv      |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Malajziai és szingapúri banki pénzforgalmi jelentés

Ez a szolgáltatás olyan pénzforgalmi jelentés nyomtatását tette lehetővé a felhasználó számára, amelyen megjelentek a kiválasztott bankszámlák megadott dátumtartományához kapcsolódó tranzakciók, illetve a pénzbeáramlások és a pénzkiáramlások részletei.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ugyanezek az adatok a Banki tranzakció lekérdezéséből is beszerezhetőek. |
| **Felváltotta másik szolgáltatás?**   | A Banki tranzakció lekérdezése                                            |
| **Érintett területek**         | Készpénz- és bankkezelés                                                |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.          |

### <a name="mexican-cfd-electronic-invoice"></a>Mexikói CFD elektronikus számla

Ez a funkció lehetővé tette a CFD módszerrel történő mexikói elektronikus számlák létrehozását, abban az esetben ha vállalat írja alá a számlát, valamint kérvényezi a kapcsolódó állami engedélyeket. Ez a szolgáltatás egy olyan havi jelentést is magában foglal, amely a periódusban kiadott összes elektronikus számlát tartalmazza.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A módszer már nem alkalmazható. Az adóhatóságok beszüntettették az elektronikus számlák CFD módszerrel való létrehozását. Ennek helyét a CFDI (Comprobante Fiscal Digital a través de Internet) módszer vette át, amelynek megfelelően egy külső szolgáltató (PAC) ír alá. A havi jelentést eltávolítottuk, a felhasználók egy lekérdezési lehetőség segítségével kérhetnek le előzménytranzakciókat. |
| **Felváltotta másik szolgáltatás?**   | Nincs    |
| **Érintett területek**         | Kinnlevőségek, Projekt   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="mexico-realized-and-unrealized-vat"></a>Mexikói realizált és nem realizált áfa

A Microsoft Dynamics AX 2012 a nem realizált áfát a Mexikó-specifikus nem realizált adó funkció használatával kezelte.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció  |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt a funkciót felváltotta az alapból biztosított standard feltételes áfa funkció. |
| **Érintett területek**         | Adó   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook-integráció


|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a funkciót a Microsoft Exchange Server integrációja váltotta fel. |
| **Felváltotta másik szolgáltatás?**   | Igen                                                                            |
| **Érintett területek**         | Értékesítés és marketing                                                            |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Készlet- és raktárkezelési naplók személyes zárolása

A készlet- és raktárnaplók már nem támogatják naplók megjelölését egy kiválasztott felhasználó személyes tartalmaként. A naplók zárolásának folyamata csak felhasználócsoportok személyes tartalmaként, illetve szerkesztés alatt támogatott.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció hasznossága nem mutatható ki. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                     |
| **Érintett területek**         | Készletgazdálkodás                   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.         |

### <a name="product-builder"></a>Termékszerkesztő

A Termékszerkesztő használatával korábban értékesítési rendelésekből, beszerzési rendelésekből, termelési rendelésekből, értékesítési ajánlatokból projektajánlatokból vagy cikkszükségletekből származó cikkek dinamikus konfigurálására volt lehetőség. Egy modellezési változókkal rendelkező termékmodell alapján a felhasználó ki tudta választani a vevői követelményeknek megfelelő értékeket, valamint létre tudott hozni egy egyedi, anyagjegyzékkel és útvonallal rendelkező termékváltozatot.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Termékszerkesztő a végfelhasználók számára X++ kódot jelenített meg, a Dynamics AX jelenlegi verziójában nem támogatott. Az átfedő, nagy terjedelmű kódbázisok ismétlődő karbantartásainak elkerülése érdekében eltávolításra került.  |
| **Felváltotta másik szolgáltatás?**   | Igen. A megszorításon alapuló konfiguráció a Dynamics AX 2012 verzióban jelent meg, és már akkor megtörtént annak a bejelentése, hogy a Termékszerkesztő a későbbi verziókban elavulttá válik. A megszorításon alapuló konfigurációs technológia van kiválasztva az alaptermékekhez a konfiguráció engedélyezéséhez. További tudnivalókért lásd: [Termékkonfigurációs modell felépítése](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/pim/build-product-configuration-model). |
| **Érintett területek**         | Termékinformációk kezelése, Értékesítés és marketing  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.      |

### <a name="rename-product-dimension"></a>Termékdimenzió átnevezése

Ez a szolgáltatás lehetővé tette a három alap termékdimenzió egyikének (méret, szín vagy stílus) átnevezését egy olyan névre, amely jobban megfelel az üzleti követelményeknek. Az átnevezés kiterjedt minden olyan címkére, ahol megjelent a termékdimenzió neve.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics AX jelenlegi verziója nem támogatja címkék módosítását futtatás alatt. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                            |
| **Érintett területek**         | Termékinformációk kezelése                                                |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                                                |

### <a name="retail-server-connectivity-using-http"></a>Retail Server kapcsolat ellenőrzése HTTP segítségével

A Dynamics AX 2012 R3 rendszerben a Retail Server a HTTP-kommunikáció (nem védett) használatával működött. Ez a szabványos HTTPS-t használó szokásos kommunikáció mellett működött.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új biztonsági óvintézkedések következményeképpen kizárólag a TLS 1.2 (vagy az újabb, ha rendelkezésre áll) protokollt használó biztonságos kommunikáció támogatott. Az önkiszolgáló telepítő automatikusan konfigurálja a számítógépet ehhez a kommunikációs módhoz. |
| **Felváltotta másik szolgáltatás?**   | Szám Jelenleg csak a szabványos HTTPS által biztosított kommunikáció támogatott. |
| **Érintett területek**         | Retail Server  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában. |

### <a name="role-center-pages"></a>Szerepkör főoldalak lapjai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Szerepkör főoldalak lapjai a már megszűnt Enterprise Portal platformra épültek, amelynek helyét a Dynamics AX jelenlegi verziójában az új webes ügyfélplatform vette át. |
| **Felváltotta másik szolgáltatás?**   | Az új Munkaterület képernyőminta folyamatközpontú tervezése egyszerű hozzáférést biztosít az adott folyamaton belül gyakran használt feladatokhoz.                       |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában   |

### <a name="sales-tax-jurisdictions"></a>Áfailletékességek

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony vevői használat és korlátozott szolgáltatáskészlet. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                           |
| **Érintett területek**         | Amerikai áfa                                 |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.               |

### <a name="sites-services"></a>Sites Services

Az Oldal Szolgáltatások lehetővé teszik olyan weboldalak megalkotását, melyek kiterjesztik az üzleti folyamatokat az internetre informatikai segítség nélkül.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics AX által használt Microsoft Azure infrastruktúra új helyettesítő lehetőségekkel rendelkezik (például Azure oldalakkal). |
| **Felváltotta másik szolgáltatás?**   | Nincs   |
| **Érintett területek**         | HR-toborzás, esetkezelés, ajánlatkérés, szállítóregisztrálás, lehetőségekhez és kampányokhoz tartozó együttműködési munkaterületek  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.    |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS igény-előrejelzési szolgáltatások

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció kialakítása az új felhő architektúrában nem támogatható. |
| **Felváltotta másik szolgáltatás?**   | Azure gépi tanulási kereslet-előrejelzési stratégia                           |
| **Érintett területek**         | Alaptervezés                                                              |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Szállítói számlagyűjtő a feladási részletek nélkül

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat. Ezt a funkciót felváltotta a munkafolyamat funkcióval rendelkező Számlanapló. |
| **Felváltotta másik szolgáltatás?**   | A Számlanapló munkafolyamat funkciói.     |
| **Érintett területek**         | Kötelezettségek |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójában.    |


### <a name="virtual-company-accounts"></a>Virtuális vállalati számlák

A virtuális vállalatok funkció már nem támogatott a Dynamics AX rendszerben. A virtuális vállalatok funkció lehetővé tette a felhasználók számára, hogy vállalatok egy csoportja által közösen használható táblákat állítsanak be. A szolgáltatás leírása itt található: [Vállalati számlák és Virtuális vállalati számlák](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). A szolgáltatás úgy működik, hogy a táblákat gyűjteményekbe csoportosítja, ezeket pedig virtuális vállalatokhoz társítja. Utóbbiak létező, „valódi” vállalatok csoportjait jelentik. Lekérdezések jönnek létre, amelyek révén a virtuális vállalatban szereplő összes vállalat hozzáférhet a társított táblagyűjtemény tábláiban lévő adatokhoz.

|   |  | 
|------------|--------------------|
| **Elavulás/eltávolítás oka** | - A virtuális vállalatokat még az adatok táblákban való tárolása előtt be kell állítani. A virtuális vállalatok, már meglevő implementációra történő modernizálása nagyon nehézkes.<br><br>- Mivel a Microsoft Dynamics AX jelenlegi verziójában rengeteg adatnormalizáció történt, igen nehézkessé vált átlátni azt, hogy a táblagyűjteményekhez mit szükséges hozzáadni. Például nehéz megállapítani, mely táblák kerüljenek megosztásra. A virtuális vállalatokban lévő táblákból hivatkozott összes egyéb táblát is hozzá kell adni. A táblanormalizáció miatt, még egy több táblában szétszóródó egyszerű alapadatot is a virtuális vállalat részévé kell tenni. Bármilyen itt történő hiba működési diszfunkciókat okozhat.<br><br>- Egy virtuális vállalat részét képező táblában elvesznek az adatok eredetére vonatkozó információk, és csak a virtuális vállalat kerül rögzítésre.   |
| **Felváltotta másik szolgáltatás?** | Globális táblák használatával a táblákat elérhetővé teheti az összes vállalatból. Jelenleg nincs helyettesítés. |   
| **Érintett területek**       | Minden modul |   
| **Állapot**                       | Eltávolítva a Dynamics AX 7.0-s verziójában.   |   

### <a name="windows-8-tablet-app"></a>Windows 8 táblagépes alkalmazás

A Windows 8-ra készült táblagépes alkalmazás lehetővé tette a költségbeírást és a jóváhagyást.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Finance and Operations kompatibilis a táblagépekkel. A táblagépes alkalmazásra már nincs szükség.    |
| **Felváltotta másik szolgáltatás?**   | Szám          |
| **Érintett területek**         | Költséggazdálkodás   |
| **Állapot**                         | Eltávolítva: Ez a funkció csak a Dynamics AX 2012 R3 verzióban érhető el. |

### <a name="workplanner"></a>Munkatervező

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat |
| **Felváltotta másik szolgáltatás?**   | Nem, de a **Profilkapcsolat** lap (amely a **Profilcsoportok** oldalon nyitható meg), ugyan azt az üzleti forgatókönyvet támogatja, mint az elavult **Munkatervező** oldal. |
| **Érintett területek**         | Munkaidő és jelenlét     |
| **Állapot**                         | A kódot nem távolítottuk el. Azonban a JmgWorkPlanner űrlap nem lett áttelepítve.    |

### <a name="x-financial-statements"></a>X++ pénzügyi kimutatások

|                                                 |                                                                                                          |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Elavulás/eltávolítás oka</strong> |                         Ezt a szolgáltatást egy másik szolgáltatás váltotta fel.                         |
|  <strong>Felváltotta másik szolgáltatás?</strong>  | Felügyeleti jelentéskészítő (a Dynamics AX jelenlegi verziójában <strong>Pénzügyi jelentéskészítés</strong> megjelöléssel) |
|     <strong>Érintett területek</strong>     |                                              Főkönyv                                              |
|             <strong>Állapot</strong>             |                                      Eltávolítva a Dynamics AX 2012-s verziójában                                      |


