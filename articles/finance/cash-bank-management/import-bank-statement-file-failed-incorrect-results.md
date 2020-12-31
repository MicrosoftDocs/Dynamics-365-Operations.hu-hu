---
title: Banki kivonatfájl importálása – hibaelhárítás
description: Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.
author: panolte
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09b24b88ee5f8104aabd11397d5bd2745e846cb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443858"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Banki kivonatfájl importálása – hibaelhárítás

[!include [banner](../includes/banner.md)]

Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.

<a name="what-is-the-error"></a>Mi a hiba?
------------------

Miután megpróbál importálni egy bankszámlakivonat fájlt, a hiba megkereséséhez ugorjon az Adatok kezelése munkaelőzményekre és a végrehajtás részleteire. A hiba a kimutatható a kivonat, egyenleg vagy kivonatsor választásával. Azonban, nem valószínű, hogy segítségével azonosíthatja a mezőt vagy a problémát okozó elemet.

## <a name="what-are-the-differences"></a>Mik a különbségek?
Hasonlítsa össze a bankfájl elrendezésdefinícióját a Finance importdefiníciójával és vegye figyelembe a mezők és elemek esetleges eltéréseit. Hasonlítsa össze a banki kivonatfájlt a Finance kapcsolódó mintafájljával. A ISO20022 fájlokban az esetleges különbségeket elvileg könnyen látni lehet.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Az importált banki kivonatok időzónabeli eltérései
Az importfájl dátum- és időértékei eltérhetnek a Finance and Operations modulban megjelenített dátum-idő értéktől. Ha meg szeretné akadályozni ezt az eltérést, adja meg az időzóna-beállítást az **Adatforrások konfigurálása** lapon. Az [Továbbfejlesztett banki egyeztetés importálási folyamata](set-up-advanced-bank-reconciliation-import-process.md) további tudnivalókat nyújt az időzóna-beállítások megadásához.

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
A következő táblázat felsorolja a továbbfejlesztett banki egyeztetés importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja. A példa fájlokat és műszaki elrendezéseket itt töltheti le: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Technikai elrendezésdefiníció                             | Banki kivonat példafájl          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |





