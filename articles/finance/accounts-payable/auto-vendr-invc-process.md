---
title: Automatizált szállítói számlázási folyamatok – áttekintés
description: Ez a témakör szállítói számla feldolgozásának automatizálási lehetőségét és az automatikus folyamat használatának előnyeit mutatja be.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 187b3c4f1a8b2c9ec6df95c19b261756ec4562dc
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905015"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Automatizált szállítói számlázási folyamatok – áttekintés

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör szállítói számla feldolgozásának automatizálási lehetőségét és az automatikus folyamat használatának előnyeit mutatja be. Ez a lehetőség a Funkciókezelés modulban bekapcsolt funkciókból áll. Ezek a funkciók csak a szállítói számlákra vonatkoznak, nem pedig a **Számlanapló** vagy a **Számlajegyzéknapló** oldalon feldolgozott számlákra.

Sok esetben a szervezetek a papíralapú számlák feldolgozását harmadik felekkel együttműködve, optikai karakterfelismerési (OCR) szolgáltató igénybevételével oldják meg. A szolgáltató géppel olvasható számlázási metaadatokat juttat vissza. Az automatizálás elősegítése érdekében a Kötelezettségek automatizálása funkciók segítségével ezeket az elemeket a Kötelezettségek modulból vonhatja be.

A Kötelezettségek szállítói számlázási folyamatait is automatizálhatók. E folyamatok közé tartozik az importált szállítói számlák munkafolyamat-rendszerbe történő beküldése és a feladott terméknyugta sorainak egyeztetése a függőben lévő szállítói számlák soraival. Az automatizált folyamat az adott szállítói számla egyes folyamatokon való áthaladásának állapotával kapcsolatos információkat jelenít meg. Ez a funkció segít Kötelezettségeket kezelő irodai dolgozók és vezetők számára hatékonyabban feldolgozni a szállítói számlákat. Emellett csökkenti azokat a hibákat és hiányosságokat, amelyek akkor fordulhatnak elő, ha az adatokat manuálisan rögzítik és dolgozzák fel.

Az automatizálási folyamatok a következő feladatok végrehajtásához használhatók:

- Importált számlák automatikus elküldése a munkafolyamat-rendszerbe.
- Terméknyugták egyeztetése a függőben lévő szállítói számlák soraival.
- A feladás szimulálása a szállítói számla feladását megelőzően.
- Munkafolyamat-előzmények gyors és hatékony áttekintése.
- A szállítói számlák feldolgozásának automatizálása eredményeinek megtekintése és elemzése.

## <a name="vendor-invoice-automation--submit-imported-vendor-invoices-to-the-workflow-system"></a>Szállítói számla automatizálása – Importált szállítói számlák elküldése a munkafolyamat-rendszerbe

Az érintés nélküli, Kötelezettségeken belüli számlázási folyamat részeként a rendszer automatikusan elküldhet importált számlákat a munkafolyamat-rendszerbe. A folyamat futtatása a háttérben történik, az Ön által megadott gyakorisággal (óránként vagy naponta). Az importált számláknak a munkafolyamat-rendszerbe történő automatikus elküldése képességhez szükséges, hogy a folyamat egy importált számlával kezdődjön. Ha azt szeretné, hogy a számla manuális beavatkozás nélkül is feldolgozható legyen az elejétől a végéig, akkor a munkafolyamat-konfigurációban szerepelnie kell egy automatikus feladási feladatnak.

„A vételi megbízásokhoz (PO-k) kapcsolódó számlák, valamint a nem PO-beszerzési kategóriát és nem raktározott sorokat tartalmazó számlák automatikusan elküldhetők a munkafolyamat-rendszerbe. A manuálisan bevitt számlákat és a **Szállítói együttműködés számlázási** munkaterületen keresztül létrehozott számlákat kézzel kell elküldenie a munkafolyamat-rendszerbe.

Az automatizálási funkció egy rugalmas keretet biztosít ahhoz, hogy vállalati szabályokat határozzon meg az importált szállítói számlák munkafolyamat-rendszerbe küldéséhez, és hogy a függőben lévő szállítói számla sorait a rendszer egyeztesse a feladott szállítólevél soraival.

## <a name="vendor-invoice-automation--match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Szállítói számla automatizálása – A terméknyugták sorainak egyeztetése olyan számlasorokkal, amelyekhez háromirányú egyeztetési irányelv tartozik.

A rendszer automatikusan egyezteti a feladott terméknyugtákat azokkal a számlasorokkal, amelyekhez háromirányú egyeztetési irányelvet határoztak meg. A folyamat addig fog futni, amíg az egyeztetett terméknyugták mennyisége nem egyezik meg a számla szerinti mennyiséggel. E folyamat részeként kiválaszthatja, hogy hány alkalommal próbálja meg a rendszer egyeztetni a terméknyugtákat egy adott számlasorral, mielőtt a folyamatot sikertelenként lezárná. A folyamat a háttérben fog futni, óránként vagy naponta. Az automatizált egyeztetési folyamat futtatható a számlák munkafolyamat-rendszerbe történő elküldéséhez kapcsolódó eljárás részeként. Azt is megteheti, hogy önálló folyamatként futtatja.

## <a name="vendor-invoice-automation--pre-validate-vendor-invoice-posting"></a>Szállítói számla automatizálása – A szállítói számla feladásának előzetes érvényesítése

A feladási szimuláció végrehajtja a szállítói számlák feladási folyamata során elvégzett ellenőrzési lépéseket, ekkor azonban nem frissülnek a számlák. A folyamat futtatásához akár egy számlát, akár több számlát is kiválaszthat a **Függőben lévő szállítói számlák** oldalon.

## <a name="vendor-invoice-automation--enhanced-experience-for-viewing-workflow-historical-information-for-vendor-invoices"></a>Szállítói számla automatizálása – A szállítói számlákra vonatkozó munkafolyamat-előzményinformációk megtekintésének továbbfejlesztett módja.

A szállítói számla munkafolyamat-előzményeinek könnyen olvasható nézete jeleníthető meg. A szállítói számla munkafolyamat-előzményeit közvetlenül a szállítói számláról lehet elérni. Ezért kevesebb kattintás szükséges az információ megtalálásához.

## <a name="vendor-invoice-automation--analytics-and-metrics"></a>Szállítói számla automatizálása – Elemzések és mérőszámok

A **Szállítói számla tétel** munkaterület lehetővé teszi, hogy az olyan szállítói számlákra összpontosítson, amelyek nem haladtak végig az automatikus folyamaton. A munkaterületen felsorolt csempék olyan szállítói számlákról tartalmaznak információkat, amelyeknek a munkafolyamat-rendszerbe küldése nem sikerült, importáltak vagy a terméknyugtákkal egyeztetettek. A Microsoft Power BI mérőszámokkal a Kötelezettségek vezetői áttekinthetik a szállítói számlák automatizálásának hatékonyságát is.
