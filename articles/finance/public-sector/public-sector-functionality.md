---
title: Állami szektor – kezdőlap
description: A Dynamics 365 Finance támogatja az állami szektorban gyakran használt üzleti folyamatokat. Ezen folyamatok között költségvetés-tervezési, beszerzési, kötelezettség- és követeléskezelési feladatok egyaránt találhatók.
author: v-kiarnd
ms.date: 06/20/2017
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "20691"
- intro-internal
ms.assetid: 391a6899-7011-40bc-b54b-5665b06bcecb
ms.search.region: Global
ms.search.industry: Public sector
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d190329b46a235625493cd04b405f74768fc52f
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565819"
---
# <a name="public-sector-home-page"></a>Állami szektor – kezdőlap

[!include [banner](../includes/banner.md)]

Olyan üzleti folyamatokat engedélyezhet, amelyek mind az állami, mind a privát szektorban gyakoriak (például a költségvetés-készítéssel, a beszerzéssel, vagy a kötelezettségekkel és kinnlevőségekkel kapcsolatos feladatok). 

Az Állami szektor funkció segítségével megfelelhet meg a közösséget szolgáló szervezetekre érvényes szabályoknak, szabályozásoknak és jelentési kötelezettségeknek. Az érintett üzleti folyamatok a következők: 

- Alapok könyvelése, származtatott pénzügyi hierarchiák, valamint a kinnlevőségekre és a főkönyvre vonarkotó feladásdefiníciók.
- Előzetes költségvetések, arányosítások és kötelezettségek.
- Számlázási kódok, számlázási osztályok, kereskedelmi partnerkódok és a szabadszöveges számlák egyéni mezői.
- Főkönyvi év végi feldolgozási folyamata, amelyhez hozzátartoznak a beszerzési rendeléseken szereplő kötelezettségvállalások és kötelezettségek.
- Elektronikus kifizetések szállítóknak, kifizetési jelentések aláírási oldalai, valamint számlák kifizetésének várakoztatása.

  További információért tekintse át az alábbi témaköröket:

- [Az Állami szektor funkció tervezése](plan-public-sector-functionality.md)
- [Kötelezettségek az állami szektorban – áttekintés](accounts-payable-public-sector.md)
- [Kinnlevőségek az állami szektorban – áttekintés](accounts-receivable-public-sector.md)
- [Költségvetés-készítés az állami szektorban – áttekintés](budgeting-public-sector.md)
- [Tárgyi eszközök az állami szektorban](fixed-asset-public-sector.md)
- [Könyvelés a franciaországi állami szektorban](../localizations/emea-fra-public-sector-accounting.md)
- [Főkönyv az állami szektorban – áttekintés](general-ledger-public-sector.md)
- [Beszerzés és forráskeresés az Állami szektorban](procurement-sourcing-public-sector.md)
- [Biztonsági szerepkörök az állami szektorban](security-roles-public-sector.md)

\* Csak a Franciaországban található szervezetekre vonatkozik.

## <a name="why-do-i-need-the-public-sector-configuration-key"></a>Miért van szükség az Állami szektor konfigurációs kulcsra?
Az **Állami szektor** konfigurációs kulcs engedélyezi azokat az oldalakat és vezérlőket, amelyek kiegészítik a központi alkalmazásokat. A kulcsot a **Licenckonfiguráció** oldalon engedélyezheti vagy tilthatja le.

## <a name="how-does-the-public-sector-configuration-key-relate-to-other-configuration-keys"></a>Milyen kapcsolatban áll az Állami szektor konfigurációs kulcsa a többi konfigurációs kulccsal?
Az alábbi táblázatban arról talál információt, hogy ez a konfigurációs kulcs milyen kapcsolatban áll a többi konfigurációs kulccsal.

|   **Részletek**         |              **Leírás**                                                                                                                                                                                        |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szülőkulcs | Egyik sem                                                                                                                                                                                                                |
| Gyermekkulcs | **Speciális főkönyvi bejegyzés** konfigurációs kulcs (AdvancedLedgerEntry) **Állami szektor 1099G** konfigurációs kulcs (Tax1099G) **Állami szektor 1099S** konfigurációs kulcs (Tax1099S) **Francia jogszabályok** konfigurációs kulcs |


## <a name="additional-resources"></a>További erőforrások

[Az Állami szektor funkció tervezése](plan-public-sector-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
