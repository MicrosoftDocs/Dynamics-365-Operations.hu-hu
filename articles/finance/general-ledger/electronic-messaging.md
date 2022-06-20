---
title: Elektronikus üzenetküldés
description: Ez a cikk áttekintést és beállítási információkat tartalmaz a Microsoft Dynamics 365 Pénzügy elektronikus üzenetkezeléséhez.
author: liza-golub
ms.date: 01/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: cf9ee77b2588283f0b34f2099d6f8d78e15a5af5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8934717"
---
# <a name="electronic-messaging"></a>Elektronikus üzenetküldés

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt, és bemutatja **az Elektronikus üzenetek** (EM) funkció beállítási adatait.

Nemrég a világ számos országának és régiójának kormányai és törvényhozó hatóságai alkalmazni kezdték az adott országokban vagy régiókban regisztrált vállalatokkal szembeni jelentéskészítési előírásokat. A követelmények célja az, hogy ezektől a vállalatoktól elektronikus úton lehessen adatokat gyűjteni, közvetlenül a feljegyzésre, tárolásra és kezelésre használt rendszerből.

Microsoft Dynamics A 365 Pénzügy emfunkciói különféle folyamatokat támogatnak a Pénzügy és a szabályozó hatóságok által a hivatalos adatok jelentésére, elküldésére és fogadására vonatkozó elektronikus együttműködésre vonatkozó folyamatokban.

Az EM funkció integrálva van az **Elektronikus jelentéskészítés** (ER) modulban. Az ER formátumokat be lehet állítani az elektronikus üzenetekhez. További információ: [Elektronikus jelentéskészítés (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Az EM funkció alapfogalmai

Az EM funkció a következő entitásokon alapul:

- **Elektronikus üzenet** – Olyan jelentés vagy bevallás, amelyet belsőleg kell jelenteni vagy továbbítani, például az adóhatóságnak elküldendő jelentés.
- **Elektronikus üzenetcikkek** – Rekordok, amelyeket a jelentett üzenetbe kell szerepeltetni.
- **Elektronikus üzenetfeldolgozás** – Műveletek láncolata, amelyeket a szükséges adatok gyűjtésére, jelentések létrehozására, az Azure Storage Blob rendszerében az adatok tárolására, a jelentések rendszeren kívülre való továbbítására, a rendszeren kívülről származó válaszok fogadására, és a beérkezett információknak megfelelően az adatbázis frissítésére kell futtatni. A láncban található műveletek kapcsolódnak vagy nem kapcsolódnak egymáshoz.

A következő ábra ábrázolja az adatok áramlását az EM esetén.

![Elektronikus üzenetküldés adatfolyama.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Az EM funkció által támogatott helyzetek

Az EM funkció az alábbi eseteket támogatja:

- Üzenetek manuális létrehozása és jelentések generálása, amelyek a különböző típusú társított exportálási ER-formátumokon alapulnak. Ilyen típusok például a Microsoft Excel, az XML, a JavaScript Object Notation (JSON), a PDF, a szöveg és a Microsoft Word.
- Üzenetek automatikus létrehozása és feldolgozása, amelyeket egy hatóságtól kértek és érkeztettek be egy társított importálási ER-formátum használatával.
- Információk gyűjtése és feldolgozása adaforrásból üzenetelemként. Az adatforrás egy Finance tábla.
- További információk tárolása, és különböző értékek értékelése a specifikusan meghatározott osztályok lehívásával az üzenetekkel vagy üzenetelemekkel kapcsolatban.
- Információ aggregálása, amit az üzenetelemekben gyűjtött, az információ felosztása üzenet szerint, és jelentések létrehozása, amik a társított exportálási ER-formátumokban vannak.
- A létrehozott jelentések továbbítása egy webes szolgáltatónak az Azure Key Vault szolgáltatásban tárolt biztonsági információ segítségével.
- Válasz fogadása a webes szolgáltatótól, a válasz értelmezése, és szükség szerint az adatok frissítése a Finance szolgáltatásban.
- A létrehozott jelentések tárolása és áttekintése.
- A naplóadatok tárolása és áttekintése, amelyek egy üzenettel vagy üzenetelemhez kapcsolódóan futtatott műveletre vonatkoznak.
- A feldolgozás szabályozása különböző üzenetállapotok és üzenetelem-állapotok segítségével.

## <a name="security-privileges"></a>Biztonsági jogosultságok

Az elektronikus üzenetekhez a következő biztonsági jogosultságok állnak rendelkezésre.

| Biztonsági jogosultság           | Hozzáférési szint | Társítás |
|------------------------------|--------------|-------------|
| Elektronikus üzenetek kezelése | Ez a jogosultság teljes hozzáférést ad az EM-funkciókhoz. Ha rendelkezik ezzel a jogosultsággal, beállíthatja az elektronikus üzenetküldést, és futtathatja az összes feldolgozást. | Ez a jogosultság szerepel az **Értékesítésiadó-tranzakciók karbantartása** biztonsági feladatban. Ez a feladat továbbá szerepel a **Könyvelő** biztonsági szerepkörben. |
| Elektronikus üzenetek megtekintése     | Ez a jogosultság csak olvasási jogosultságot ad az EM-funkciókhoz. Ha rendelkezik ezzel a jogosultsággal, megtekintheti az elektronikus üzenetküldés beállításait és üzeneteit. Azonban nem állíthat be és nem futtathat semmit. | Ez a jogosultság szerepel az **Forgalmiadó-tranzakció státuszának lekérdezése** biztonsági feladatban. Ez a feladat továbbá szerepel a következő biztonsági szerepkörökben:<ul><li>Beszedési vezető</li><li>Kinnlevőség-adminisztrátor</li><li>Kinnlevőség-kezelő</li><li>Adókönyvelő</li><li>Könyvelő</li><li>Főkönyvelő</li><li>Számviteli felügyelő</li><li>Értékesítési igazgató</li><li>Kötelezettségkezelő adminisztrátor</li></ul> |
| Elektronikus üzenetek működtetése  | Ez a jogosultság csak az **Elektronikus üzenetek** és az **Elektronikus üzenetelemek** lapokhoz ad hozzáférést. Ha rendelkezik ezzel a jogosultsággal, az ilyen lapokon hívott összes feldolgozás futtatható. | Ez a jogosultság szerepel az **Elektronikus üzenetek kezelése** biztonsági feladatban. Ez a feladat továbbá szerepel az **Elektronikus üzenetek kezelője** biztonsági szerepkörben. |

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Az EM funkció által támogatott országspecifikus szabályozási funkciók

Az alábbi táblázat néhány, az EM funkció által támogatott országspecifikus szabályozási funkcióról nyújt tájékoztatást.

| Ország/régió     | Funkció neve | Funkcióbemutató rögzítése |
|-------------|--------------|------------------------|
| Spanyolország       | [Azonnali információbiztosítás az áfáról (Suministro Inmediato de Información del IVA, SII)](../localizations/emea-esp-sii.md) | |
| Magyarország     | [Online számlázási rendszer](../localizations/emea-hun-online-invoicing.md) | |
| Egyesült Királyság | [Adó digitalizálása (MTD) – áfakimutatás beküldése](../localizations/emea-gbr-mtd-vat-integration.md) | [Pénzügy és műveletek: EGYESÜLT Királyság digitális adója - áfabevallás a Dynamics 365-ben](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Litvánia   | [i.SAF-jelentés](../localizations/emea-ltu-isaf.md) | |
| Lengyelország      | [Áfabevallás jegyzékekkel (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Pénzügy: SAF/JPK áfavizsgálati jegyzékek](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Hollandia | [Áfabevallás Hollandiában](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Cseh Köztársaság | [Áfabevallás](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brazília      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Oroszország      | [Áfabevallás](../localizations/rus-vat-declaration.md) | |
| Oroszország      | [Könyveléssel kapcsolatos jelentéskészítés elektronikus formátumban](../localizations/rus-accounting-reporting.md) | |
| Oroszország      | [Nyereségadó-bevallása](../localizations/rus-profit-tax-declaration.md) | |
| Oroszország      | [Kiszabott adóbevallás](../localizations/rus-assessed-tax-declaration.md) | |
| Oroszország      | [Szállításiadó-bevallás](../localizations/rus-transport-tax-declaration.md) | |
| Oroszország      | [Földadó-bevallás](../localizations/rus-land-tax-declaration.md) | |
| Norvégia      | [Áfa-visszatérítés az Altinnba küldött közvetlen beküldéssel](../localizations/emea-nor-vat-return.md) | [Új áfa-visszaküldés közvetlen beküldéssel az Altinn programba a Dynamics 365 Pénzügy programban](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/new-vat-return-with-direct-submission-to-altinn-in-dynamics-365-finance-december-1-2021) |
| Franciaország      | [Áfabevallás (Franciaország)](../localizations/emea-fra-VAT-declaration-preview-France.md) | |
| Ausztria     | [Áfabevallás (Ausztria)](../localizations/emea-aut-vat-declaration-austria.md) | |
| Németország     | [Áfabevallás (Németország)](../localizations/emea-deu-vat-declaration-germany.md) | |
| Hollandia | [Áfabevallás Hollandiában](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Svédország      | [Áfabevallás (Svédország)](../localizations/emea-swe-VAT-declaration-Sweden.md) | |
| Svájc | [Áfabevallás (Svájc)](../localizations/emea-che-vat-declaration-switzerland.md) | |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

