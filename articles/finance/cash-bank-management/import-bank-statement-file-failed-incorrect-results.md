---
title: Banki kivonatfájl importálása – hibaelhárítás
description: Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14f0e480b93e663f81db5a1edb2ae71b559bb05e
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188560"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Banki kivonatfájl importálása – hibaelhárítás

[!include [banner](../includes/banner.md)]

Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.

## <a name="what-is-the-error"></a>Mi a hiba?

Miután megpróbál importálni egy bankszámlakivonat fájlt, a hiba megkereséséhez ugorjon az Adatok kezelése munkaelőzményekre és a végrehajtás részleteire. A hiba a kimutatható a kivonat, egyenleg vagy kivonatsor választásával. Azonban, nem valószínű, hogy segítségével azonosíthatja a mezőt vagy a problémát okozó elemet.

> [!NOTE]
> Az importált banki kivonatok csak egy időpontban fedhetik át egymást.  Ha például a kivonat 2021. január 1-jén 12:00 órakor ér véget, akkor a következő kivonat kezdő dátuma lehet de. 12:00 óra, 2021. de. 12:00:00 időpontban.

## <a name="what-are-the-differences"></a>Mik a különbségek?
Hasonlítsa össze a bankfájl elrendezésdefinícióját a Finance importdefiníciójával és vegye figyelembe a mezők és elemek esetleges eltéréseit. Hasonlítsa össze a banki kivonatfájlt a Finance kapcsolódó mintafájljával. A ISO20022 fájlokban az esetleges különbségeket elvileg könnyen látni lehet.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Az importált banki kivonatok időzónabeli eltérései
Az importfájl dátum- és időértékei eltérhetnek a Finance and Operations modulban megjelenített dátum-idő értéktől. Ha meg szeretné akadályozni ezt az eltérést, adja meg az időzóna-beállítást az **Adatforrások konfigurálása** lapon. Az [Továbbfejlesztett banki egyeztetés importálási folyamata](set-up-advanced-bank-reconciliation-import-process.md) rész további tudnivalókat nyújt az időzóna-beállítások megadásához.

## <a name="transformations"></a>Átalakítások
A változtatást általában a három átalakítás egyikében kell végezni. Minden egyes átalakítás meghatározott szabványhoz van írva.

| Erőforrás neve                                         | Fájlnév                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Hibakeresés az átalakításokban
### <a name="adjust-the-bai2-and-mt940-files"></a>Módosítsa a BAI2 és MT940 fájlokat

A BAI2 és MT940 fájlok szöveges fájlok, ezek módosítása szükséges a hibakeresés engedélyezéséhez a stíluslap transzformáción (XSLT). A program ezt a módosítást hajtja végre egy fájl importálásakor.

1.  Hozzon létre XML-fájlt és másolja be a következő szöveget.

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  Másolja a bankszámlakivonat-fájl tartalmát és illessze be az XML-fájlba, hogy pótolja **KIVONATFÁLJ BEILLESZTÉSE**.

### <a name="debug-the-xslt"></a>Hibakeresés XSLT

További tájékoztatást a következő témakörben talál: <https://msdn.microsoft.com/library/ms255605.aspx>.

1.  Indítsa el a Microsoft Visual Studio programot.
2.  Hozzon létre konzol alkalmazást.
3.  Nyissa meg a megfelelő XSLT-fájlt.
4.  Kattintson az XSLT-fájlra és annak tulajdonságlapjára.
5.  Állítsa be a bemenetet bankszámlakivonat-fájl helyére.
6.  Adja meg a kimenet helyét és nevét.
7.  Állítsa be a szükséges töréspontokat.
8.  A menüben kattintson az **XML** &gt; **XSLT-hibakeresés Indítása** elemre.

### <a name="format-the-xslt-output"></a>XSLT-kimenet formázása

Az átalakítás futtatásakor kimeneti fájl készül, amelyet meg lehet tekinteni a Visual Studio alkalmazásban. Használja a Ctrl + A, Ctrl + K és a Ctrl + D billentyűkombinációkat a kimeneti fájl gyors formázásához.

### <a name="adjust-the-transformation"></a>Állítsa be az átalakítást

Állítsa be az átalakítást, a megfelelő mező vagy elem megkereséséhez a bankszámlakivonat fájlban. Ezután rendelje hozzá azt a mezőt vagy elemet a Finance elemhez.

### <a name="debitcredit-indicator"></a>Tartozás/követelés jelzése

Bizonyos esetekben kötelezettségeket kintlevőségekként lehet importálni, és kintlevőségeket kötelezettségekként lehet importálni. A probléma megoldásához módosítania kell a megfelelő XSLT fájlt. Ha a banki kivonatok több bankból származnak, ha győződjön meg róla, hogy ugyanazon tartozási/követelési módszert használják, vagy külön átalakításokat hoznak létre.

-   BAI2XML–Reconciliation.xlst GetAmountCreditDebitIndicator sablon
-   ISO20022XML–Reconcilation.xslt GetCreditDebit sablon
-   MT940XML–Reconcilation.xslt GetCreditDebitIndicator sablon

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>A banki kivonat formátumainak és a technikai elrendezések példái
A következő táblázat felsorolja a továbbfejlesztett banki egyeztetés importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja. A példa fájlokat és műszaki elrendezéseket itt töltheti le: [Importfájl-példák](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Technikai elrendezésdefiníció                             | Banki kivonat példafájl          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
