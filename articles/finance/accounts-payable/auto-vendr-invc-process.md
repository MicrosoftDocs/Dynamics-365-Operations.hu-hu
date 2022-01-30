---
title: Automatizált szállítói számlázási folyamatok – áttekintés
description: Ez a témakör szállítói számla feldolgozásának automatizálási lehetőségét és az automatikus folyamat használatának előnyeit mutatja be.
author: abruer
ms.date: 02/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4fef5011ead69028a7f667835fd5e5ba2401408d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985656"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Automatizált szállítói számlázási folyamatok – áttekintés

[!include [banner](../includes/banner.md)]

Ez a témakör szállítói számla feldolgozásának automatizálási lehetőségét és az automatikus folyamat használatának előnyeit mutatja be. Ez a lehetőség a Funkciókezelés modulban bekapcsolt funkciókból áll. Ezek a funkciók csak a szállítói számlákra vonatkoznak, nem pedig a **Számlanapló** vagy a **Számlajegyzéknapló** oldalon feldolgozott számlákra.

Sok esetben a szervezetek a papíralapú számlák feldolgozását harmadik felekkel együttműködve, optikai karakterfelismerési (OCR) szolgáltató igénybevételével oldják meg. A szolgáltató géppel olvasható számlázási metaadatokat juttat vissza. Az automatizálás elősegítése érdekében a Kötelezettségek automatizálása funkciók segítségével ezeket az elemeket a Kötelezettségek modulból vonhatja be.

A Kötelezettségek szállítói számlázási folyamatait is automatizálhatók. E folyamatok közé tartozik az importált szállítói számlák munkafolyamat-rendszerbe történő beküldése és a feladott terméknyugta sorainak egyeztetése a függőben lévő szállítói számlák soraival. Az automatizált folyamat az adott szállítói számla egyes folyamatokon való áthaladásának állapotával kapcsolatos információkat jelenít meg. Ez a funkció segít Kötelezettségeket kezelő irodai dolgozók és vezetők számára hatékonyabban feldolgozni a szállítói számlákat. Emellett csökkenti azokat a hibákat és hiányosságokat, amelyek akkor fordulhatnak elő, ha az adatokat manuálisan rögzítik és dolgozzák fel.

Az automatizálási folyamatok a következő feladatok végrehajtásához használhatók:

- Előlegek automatikus alkalmazása a szállítói számlákra
- Importált számlák automatikus elküldése a munkafolyamat-rendszerbe.
- Terméknyugták egyeztetése a függőben lévő szállítói számlák soraival.
- A feladás szimulálása a szállítói számla feladását megelőzően.
- Munkafolyamat- és automatizálási előzmények gyors és hatékony áttekintése.
- A szállítói számlák feldolgozásának automatizálása eredményeinek megtekintése és elemzése.
- Folytassa az automatikus feldolgozást több számla esetében.

## <a name="submit-imported-vendor-invoices-to-the-workflow-system"></a>Importált szállítói számlák elküldése a munkafolyamat-rendszerbe

Az érintés nélküli, Kötelezettségeken belüli számlázási folyamat részeként a rendszer automatikusan elküldhet importált számlákat a munkafolyamat-rendszerbe. A folyamat futtatása a háttérben történik, az Ön által megadott gyakorisággal (óránként vagy naponta). Az importált számláknak a munkafolyamat-rendszerbe történő automatikus elküldése képességhez szükséges, hogy a folyamat egy importált számlával kezdődjön. Ha azt szeretné, hogy a számla manuális beavatkozás nélkül is feldolgozható legyen az elejétől a végéig, akkor a munkafolyamat-konfigurációban szerepelnie kell egy automatikus feladási feladatnak.


A vételi megbízásokhoz (PO-k) kapcsolódó számlák, valamint a nem PO-beszerzési kategóriát és nem raktározott sorokat tartalmazó számlák automatikusan elküldhetők a munkafolyamat-rendszerbe. A manuálisan bevitt számlákat és a **Szállítói együttműködés számlázási** munkaterületen keresztül létrehozott számlákat kézzel kell elküldenie a munkafolyamat-rendszerbe. A fennmaradó előleg feldolgozását manuálisan kell végrehajtani az importált számlák esetében. Az előlegeket kézzel alkalmazhatja az importált számla feladása előtt vagy után. A fel nem adott normál számlákra manuálisan lehet előlegeket alkalmazni a **Szállítói számlák** oldalon. A feladást követően a kiegyenlített előleg elérhető lesz manuálisan az adott szállító egyéb számláira való alkalmazásra a **Szállítók** oldalon (**Kötelezettségek \> Közös \> Szállítók \> Minden szállító \> Számla lap \> Alkalmazás**).

Az automatizálási funkció egy rugalmas keretet biztosít ahhoz, hogy vállalati szabályokat határozzon meg az importált szállítói számlák munkafolyamat-rendszerbe küldéséhez, és hogy a függőben lévő szállítói számla sorait a rendszer egyeztesse a feladott szállítólevél soraival.

## <a name="match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>A terméknyugták sorainak egyeztetése olyan számlasorokkal, amelyekhez háromirányú egyeztetési irányelv tartozik

A rendszer automatikusan egyezteti a feladott terméknyugtákat azokkal a számlasorokkal, amelyekhez háromirányú egyeztetési irányelvet határoztak meg. A folyamat addig fog futni, amíg az egyeztetett terméknyugták mennyisége nem egyezik meg a számla szerinti mennyiséggel. E folyamat részeként kiválaszthatja, hogy hány alkalommal próbálja meg a rendszer egyeztetni a terméknyugtákat egy adott számlasorral, mielőtt a folyamatot sikertelenként lezárná. A folyamat a háttérben fog futni, óránként vagy naponta. Az automatizált egyeztetési folyamat futtatható a számlák munkafolyamat-rendszerbe történő elküldéséhez kapcsolódó eljárás részeként. Azt is megteheti, hogy önálló folyamatként futtatja.

## <a name="pre-validate-vendor-invoice-posting"></a>Szállítói számla feladásának előzetes ellenőrzése

A feladási szimuláció végrehajtja a szállítói számlák feladási folyamata során elvégzett ellenőrzési lépéseket, ekkor azonban nem frissülnek a számlák. A folyamat futtatásához akár egy számlát, akár több számlát is kiválaszthat a **Függőben lévő szállítói számlák** oldalon.

## <a name="enhanced-experience-for-viewing-workflow-and-automation-historical-information-for-vendor-invoices"></a>A szállítói számlákra vonatkozó munkafolyamat-előzményinformációk megtekintésének és automatizálásának továbbfejlesztett módja

A szállítói számla munkafolyamat-előzményeinek könnyen olvasható nézete jeleníthető meg. A szállítói számla munkafolyamat-előzményeit közvetlenül a szállítói számláról lehet elérni. Ezért kevesebb kattintás szükséges az információ megtalálásához. Ha a szervezet lehetővé tette az importált szállítói számlák automatikus elküldésének lehetőségét a munkafolyamatba, az importált számlák automatizálási előzményei meg vannak adva. Az automatizálási előzmények segítségével azonosíthatja az aktuális folyamatlépést, valamint a már elvégzett lépéseket. Ha egy lépés sikertelen, a rendszer részletes információkat nyújt a hiba okának megértéséhez.

## <a name="analytics-and-metrics"></a>Analitika és metrikák

A **Szállítói számla tétel** munkaterület lehetővé teszi, hogy az olyan szállítói számlákra összpontosítson, amelyek nem haladtak végig az automatikus folyamaton. A munkaterületen felsorolt csempék olyan szállítói számlákról tartalmaznak információkat, amelyeknek a munkafolyamat-rendszerbe küldése nem sikerült, importáltak vagy a terméknyugtákkal egyeztetettek. A Microsoft Power BI mérőszámokkal a Kötelezettségek vezetői áttekinthetik a szállítói számlák automatizálásának hatékonyságát is.


## <a name="resume-automation-processing-for-multiple-invoices"></a>Az automatizált feldolgozás folytatása több számla esetében

Ha egy importált számlát nem küld el sikeresen a munkafolyamatnak az automatizált folyamat használatával, a rendszer eltávolítja azt a további automatizált feldolgozásból. A kötelezettségek ügyintézője áttekintheti és szerkesztheti a számlát, mielőtt az automatikus folyamat újra beküldi azt a munkafolyamatba. Ha egy hiba oka több számla esetében is megoldható, újraindíthatja az automatikus folyamatot az **Automatikus számlafeldolgozás folytatása** lapon. 

## <a name="tracking-the-invoice-received-date-value"></a>A számla megérkezési dátumértékének nyomon követése

A **Számla megérkezési dátuma** érték azt a dátumot jelzi, amikor a vállalat megkapta a számlát a szállítótól. Kiindulópontként szolgál a számla automatizálási folyamatokon keresztüli előrehaladásának nyomon követéséhez. Ez az érték szerepelhet a szállítói számla importált adatai között. A manuálisan létrehozott számlákhoz megadhatja a dátumot. Ha nincs megadva érték, a program alapértelmezés szerint az aktuális dátumot használja.


## <a name="tracking-the-imported-invoice-amount-and-imported-sales-tax-amount-values"></a>Az Importált számla összegének és az Importált áfaösszeg értékének nyomon követése

A szállítói számlák importálási fájljában megadhatja az **Importált számla összege** és az **Importált áfaösszeg** értékét. Ezek az értékek általában olyan számláról származnak, amelyet egy külső szolgáltató beszkennelt és megtalálhatók az importfájlban. Mivel a számla feldolgozása a Kötelezettségek pontban történik, a rendszer a számlaadatok alapján számítja ki az értékeket. A számla csak akkor adható fel, ha az importált értékek megegyeznek a számított értékekkel. Az egyező értékek garantálják, hogy a számla pontosan megegyezzen a szállítónak fizetendő esedékes összeggel. Ha a szervezet lehetővé teszi az importált számlák automatikus elküldését a munkafolyamat-rendszerbe, akkor opcionálisan előírhatja, hogy az importált összegek megegyezzenek a kiszámított összegekkel, és csak ezt után lehessen a számlát benyújtani a munkafolyamat-rendszerbe.

## <a name="vendor-invoice-automation---resume-automation-processing-for-multiple-invoices"></a>Szállítói számla automatizálása – Több számla automatizálásának folytatása
Ha egy importált számlát nem küld el sikeresen a munkafolyamatnak az automatizált folyamaton keresztül, a rendszer eltávolítja azt a további automatizált feldolgozásból. A kötelezettségek ügyintézője áttekintheti és szerkesztheti a számlát, mielőtt az automatikus folyamat újra beküldi azt a munkafolyamatba. Ha egy hiba oka több számla esetében is megoldható, újraindíthatja az automatikus folyamatot az **Automatikus számlafeldolgozás folytatása** lapon. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
