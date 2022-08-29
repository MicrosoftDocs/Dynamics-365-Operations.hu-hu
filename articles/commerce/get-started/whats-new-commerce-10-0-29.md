---
title: A Dynamics 365 Commerce 10.0.29 előzetes verziója (2022. október)
description: Ez a témakör olyan funkciókat ismertet, amelyek újak Microsoft Dynamics 365 Commerce vagy módosulnak a 10.0.29-es dokumentumban.
author: josaw1
ms.date: 08/17/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 1e05f53f9ecb0a1994828172f6999a0bd5c208bc
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306232"
---
# <a name="preview-of-dynamics-365-commerce-10029-october-2022"></a>A Dynamics 365 Commerce 10.0.29 előzetes verziója (2022. október)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek újak Microsoft Dynamics 365 Commerce vagy módosulnak a 10.0.29-es verzió előnézetében. Ennek a verziónak a buildszáma több 10.0.1326, és a következő ütemezésben érhető el:

- **Előzetes kiadás:** 2022. augusztus
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. szeptember
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. október

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---------|------------------|----------------|--------------| 
| B2B | [Értékesítési szerződések csatornákon keresztüli támogatásának engedélyezése](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Ez a funkció lehetővé teszi a vállalkozások közötti (B2B) eladó szervezetek számára, hogy a Commerce Headquarters értékesítési szerződésekkel határozza meg a vevők szerződésen alapuló árképzését. Ha az e-commerce webhelyen egy B2B beszerző vásárol, akkor a B2B beszerzői szervezethez beállított szerződésalapú árképzést automatikusan alkalmazza a rendszer a teljes termékfelfedezési, beszerzési és pénztári tapasztalatra. | Funkció kezelése<p>*Értékesítési szerződés támogatása a kereskedelmi csatornákon keresztül* |
| Ügyfélszolgálat | [Az Ügyfélszolgálat engedélyezése a Dynamics 365Channel for Customer Service szolgáltatásban](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | Az elsőosztályú ügyféltámogatási tapasztalat fontos a vevők számára személyre szabott és kiváló kereskedelmi tapasztalat biztosítása érdekében. Jelenleg több kereskedelmi kapcsolati pont létezik, például a fizikai üzletek, az online csatornák és a közösségi csatornák. A ügyfelek személyre szabott támogatási tapasztalatra számítanak minden ilyen szempontból. Ez a funkció a Dynamics 365Channel for Customer Service integrálásával növelheti az értékesítések bevásárlókocsira konvertálását, személyre szabhatja a ügyfelekkel való személyre szabható együttműködését, és javíthatja az ügyfélszolgálati funkciókat. | A rendszergazdák/döntéshozók engedélyezték |
| E-kereskedelem | Termék-összehasonlítás támogatása e-kereskedelemben | A termékek kategóriákon keresztüli összehasonlításának engedélyezése a vásárlók számára, hogy a helyes beszerzési döntést hozják saját maguk számára. Ez a funkció a vállalkozások és a vállalkozások között (B2C) és a B2B webhelyeken is elérhető. | Webhelyszerkesztő | 
| Ajándékutalványok | Kiskereskedelmi ajándékutalvány-táblák támogatása több vállalatot átívelő adatmegosztáshoz | A Dynamics Headquarters lehetővé teszi a vállalatközi adatmegosztást a Dynamics architektúra meghatározott tábláiban. Ebben a funkcióban a kiskereskedelmi Dynamics 365 Commerce ajándékutalvány-táblák vállalatközi adatmegosztását támogatja. Így az egyik vállalat ajándékutalványának adatai a környezetben egy másik vállalatba másolhatja az adatokat. Az eredeti vállalat ajándékutalvány-tábláján végrehajtott módosításokat a rendszer el fogja osztani az ismétlődő vállalati ajándékutalvány-táblával. | Fejlesztők |
| Globalizáció | [Commerce honosítási funkciók engedélyezése az új Commerce SDK számára](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-commerce-localization-features-new-commerce-sdk) | Az új funkció lehetőséget nyújt a Commerce Headquarters rendszerbeli honosítási funkciók engedélyezésére a szolgáltatáskezelési keretrendszer vagy a paraméterek segítségével. A pénzügyi integrációs mintákat most már az új Commerce SDK tartalmazza, és támogatják a független csomagolást. Ez a funkció lehetővé teszi a Store Commerce alkalmazásnak a globális Commerce vevők által való alkalmazását is.<p><p>Ez a kiadás tartalmazza a Commerce rendszer honosítási funkcióit [és pénzügyi integrációs mintáit Ausztriához, a](../localizations/emea-aut-fi-sample.md) Cseh Köztársasághoz, [Franciaországhoz](../localizations/emea-cze-fi-sample.md), [Németországhoz](../localizations/emea-fra-cash-registers.md), [...](../localizations/emea-deu-fi-sample.md)[Olaszországhoz](../localizations/emea-ita-fpi-sample.md), [Norvégiához](../localizations/emea-nor-cash-registers.md) és Lengyelországhoz.[...](../localizations/emea-pol-fpi-sample.md) | A rendszergazdák/döntéshozók engedélyezték |
| Teljesítmény | RtS-függőség eltávolítása a "Vevő szerkesztése" helyzetekből | A magas rendelkezésre állás és a magas teljesítmény az alapértelmezett várakozás a pénztári (POS) és az e-commerce csatornák számára. A csatornáknak már nem kell a vevői Dynamics 365 Commerce adatok szerkesztésekor a Commerce Headquarters valós idejű kommunikációját igénybe vevői igényeket teljesíteniük. Az aszinkron és nem aszinkron vevőkre vonatkozó aszinkron vevői adatok aszinkron szerkesztésének lehetősége a Commerce Headquarters valós idejű hívásának csökkentésére is képes. | A rendszergazdák/döntéshozók engedélyezték |

## <a name="feature-state-changes-in-this-release"></a>Funkcióállapot-változások ebben a verzióban

Az alábbi táblázat felsorolja azokat a funkciókat, amelyek kötelezővé vagy alapértelmezés szerint a 10.0.29-es verzióba lettek beállítva. Ezeket a funkciókat automatikusan bekapcsolja a rendszer, amint a 10.0.29-es verzióra frissít. A kötelező szolgáltatások nem kikapcsolhatók, [de az alapértelmezés szerint bekapcsolt funkciók a Funkciókezelés segítségével továbbra is kikapcsolhatóak](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A táblázat felsorolja azokat a funkciókat is, amelyek korábban nyilvános előnézetben voltak, de a 10.0.29-es verzióban általánosan elérhetővé váltak. Ez a módosítás arra utal, hogy a funkciók használata éles környezetben már ajánlott. Ezek a funkciók alapértelmezés szerint ki vannak kapcsolva, hacsak nincs jelezve más. Ezért használatukhoz a [Funkciókezelést](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) kell használnia ahhoz, hogy engedélyezze azokat.

| Szolgáltatás | Beosztás | Új funkcióállapot |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brazília) Brazíliára jellemző Commerce-funkció | Alapértelmezés szerint be |
| RetailAdvancedGTETaxAdjustmentFeature | (India) A Retail POS szolgáltatásban a kiskereskedelmi tranzakciókhoz kiszámított GST alkalmazása a kiskereskedelmi kimutatásokhoz | Alapértelmezés szerint be |
| RetailChronologicalInvoicePostingFeature_IT | (Olaszország) Időrendi sorrend nélkül feladott kiskereskedelmi számlák engedélyezése | Alapértelmezés szerint be |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (Mexikó) Engedmény kiigazítása a Retail CFDI globális rendszerben | Alapértelmezés szerint be |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Pénzügyi integráció, technikai profilok felülbírálása | Alapértelmezés szerint be |
| RetailFiscalIntegrationConnectorLocationFeature | Közvetlen pénzügyi integráció POS-pénztárgépből | Alapértelmezés szerint be |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Pénzügyi integráció helyi tárhelyének biztonsági másolata | Alapértelmezés szerint be |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Dokumentumok elhalasztott regisztrációja | Alapértelmezés szerint be |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | A POS-pénztárgépek pénzügyi nyilvántartásának állapota | Alapértelmezés szerint be |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (India) GST kiszámítása az e-kereskedelmi rendelések számlacíme alapján | Alapértelmezés szerint be |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Lengyelország) Kiskereskedelmi számlák értékesítési bizonylatának alapértelmezett állapota | Alapértelmezés szerint be |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (Mexikó) Az adóalapösszegek újraszámításának kerekítése a Retail CFDI globális rendszerben. | Alapértelmezés szerint be |
| RetailSupplementaryInvoiceFeature | A kiskereskedelmi üzletekben végrehajtott készpénzben fizetett és azonnal átvett tranzakciók kiegészítő számláinak engedélyezése | Alapértelmezés szerint be |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Készletpufferek és készletszintek engedélyezése    |  Alapértelmezés szerint be|
|RetailInboundOutboundInventoryValidationFeature|   Ellenőrzés engedélyezése a POS bejövő és kimenő készletműveletében   |   Alapértelmezés szerint be   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Továbbfejlesztett e-kereskedelmi csatornaoldali készletszámítási logika |   Alapértelmezés szerint be   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Készlethelyesbítések a pénztárban   |  Alapértelmezés szerint be  |
| RetailMultiplePickupDeliveryModeFeature |  Több felvételi szállítási mód támogatása     |   Kötelező    |
|  RetailProductAvailabilityOptimizationFeature |   Optimalizált termékelérhetőség kiszámítása  |  Kötelező |
|   RetailPricingDataManagerV2Feature   |   A Commerce árképzési motor teljesítményének javítása |   Kötelező |
|  RetailPricingPreventUnintendedRecalculationFeature   | Kereskedelmi rendelések nem tervezett árszámításának megakadályozása    |  Kötelező  |
| RetailTeamsIntegration    |   Microsoft Teams-integráció engedélyezése| Kötelező   |  
| ConsumerEFDSyncProcessFeature_BR | (Brazília) RIG - e szinkron feldolgozás | Alapértelmezés szerint be |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Belső és külső összekötők támogatása a pénzügyi integrációs keretrendszerben | Kötelező |
| RetailTaxRegistrationIdEnableFeature_BR | (Brazília) Vevők keresése a Retail POS rendszerben adószámok szerint | Kötelező |
| RetailTaxRegistrationIdEnableFeature_IN | (India) Vevők keresése a Retail POS rendszerben adószámok szerint | Kötelező |
| RetailTaxRegistrationIdEnableFeature_IT | (Olaszország) Vevői adatok kezelése a Retail POS rendszerben | Kötelező |
| RetailTaxRegistrationIdEnableFeature_PL | (Lengyelország) Vevői adatok kezelése a Retail POS rendszerben | Kötelező |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (Kiskereskedelmi GST India esetében) Jóváírások frissítése az eredeti számlákra mutató referenciákkal | Kötelező |
| RetailUserDefinedCertificateProfileFeature | A kiskereskedelmi üzletek felhasználó által megadott tanúsítványprofiljai | Kötelező |
  

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Commerce 10.0.29 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és műveletalkalmazások platformfrissítései a 10.0.29-es verzióhoz (október 2022.).](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md) 

### <a name="bug-fixes"></a>Hibajavítások

A 10.0.29-es verzióba bekerülő frissítések hibajavításával kapcsolatos információk megtekintéséhez jelentkezzen be a Lifecycle Services (LCS) [alkalmazásba, és tekintse meg a tudásbáziscikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag](/dynamics365-release-plan/2022wave2/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-features"></a>Eltávolított és elavult funkciók

A [cikk Eltávolított vagy elavult Dynamics 365 Commerce](removed-deprecated-features-commerce.md) funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva vagy el vannak távolítva a Commerce rendszerből.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Commerce](removed-deprecated-features-commerce.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
