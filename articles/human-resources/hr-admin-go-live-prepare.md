---
title: Felkészülés a Human Resources éles indításra
description: Ez az oldal útmutatást nyújt a Dynamics 365 Human Resources rendszer éles indítására való felkészüléshez.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df2c55a8a69efa20c6d8c41e97c9e1f80ee1640d
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892753"
---
# <a name="prepare-for-human-resources-go-live"></a>Felkészülés a Human Resources éles indításra

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan készülhet fel egy Dynamics 365 Human Resources-projekttel való élő indításra a Microsoft Dynamics Lifecycle Services (LCS) használatával. 

Ez az ábra az éles indítási folyamat fázisait mutatja. 

![Éles indítás folyamata](./media/hr-admin-go-live-prepare-process.png)

Az alábbi táblázat a folyamat összes lépését, a várható időtartamot és a műveletért felelős személyeket sorolja fel.

| Fázis | Művelet | Időtartam/Mikor | Ki | Jegyzetek |
| --- | --- | --- | --- |--- |
| 1 | Élő indítási dátum frissítése az LCS-ben | Legkésőbb 2-3 hónappal előre | Partner/vevő | A mérföldkövek dátumát folyamatosan naprakészen kell tartani. |
| 2 | Ellenőrzőlista teljesítése és elküldése | A felhasználói elfogadási tesztelés (UAT) befejezése után | Partner/vevő | Kövesse a [FastTrack élő indítási értékelés](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment) részben megadott útmutatást. |
| 3 | Projektértékelés (FastTrack) | FastTrack építész* | Az építész az ellenőrzőlista beérkezése után értékelést készít, és folytatja a felülvizsgálatot, amíg a kérdések tisztázásra és adott esetben a mérséklésre nem kerül sor. |
| 4 | Projektműhely (FastTrack) | FastTrack építész* | |
| 5 | Adatcsomag importálásai | A projekttől függ | Partner/vevő | Kövesse az [adatkezelés áttekintése](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md) című témakör utasításait.|
| 6 | Termelés kész | Az összes korábbi lépés befejezése után | Partner/vevő | A partner/ügyfél átveheti az éles környezet irányítását.|
| 7 | Átállási tevékenységek | A projekttől függ | Partner/vevő | |
| 8 | Éles indítás | A projekttől függ | Vevő | |

> [!IMPORTANT]
> *A 3. és 4. lépést csak azoknál a vevőknél kell kitölteni, akik megfelelnek a FastTrackhez.

## <a name="completing-the-lcs-methodology"></a>Az LCS-módszertan kitöltése

Az egyes megvalósítási projektek egyik fő mérföldköve az éles környezetre való átállás. A lépés befejezése folyamat két részből áll: 

- Végezze el a tényleges munkát, például a illeszkedési/hiányelemzést vagy a felhasználói elfogadási tesztelést (UAT). 
- Jelölje meg a megfelelő lépést az LCS-módszertanban befejezettként. 

Ez egy jó gyakorlat, hogy a lépéseket a módszertanban úgy töltse ki, ahogy előrehalad a végrehajtással. Ne várjon az utolsó pillanatig. Az ügyfél érdeke, hogy szilárd megvalósítása legyen. 

## <a name="uat-for-your-solution"></a>UAT az Ön megoldásához

Az UAT-fázisban a megvalósítási projekt tesztkörnyezetében tesztelnie kell az összes megvalósított üzleti folyamatot és az ön által végrehajtott testreszabásokat. A sikeres éles indítás érdekében az UAT-fázis befejezésekor vegye figyelembe a következőket: 

- Javasoljuk, hogy a UAT-folyamat olyan tiszta és új környezettel kezdődjon, ahol az ARANY konfiguráció adatait a UAT-folyamat megkezdése előtt átmásolja a környezetbe. Javasoljuk, hogy ARANY környezetként használja a működési környezetet, amíg az éles környezet el nem indul. Ezen a ponton a környezet termeléssé válik.
- A vizsgálati esetek a követelmények teljes körét lefedik. 
- Teszteljen az áttelepített adatok használatával. Ezeknek adatokat kell tartalmazniuk, például dolgozókat, feladatokat és beosztásokat. A nyitó egyenlegeket is tartalmazzák, például a szabadság és a távolléti időbeli elhatárolásokat. Végül tartalmazzák a nyitott tranzakciókat, például az aktuális juttatási beléptetéseket. Teljes tesztelés minden típusú adattal, még akkor is, ha az adatkészlet nincs véglegesítve. 
- Tesztelje a felhasználókhoz rendelt megfelelő biztonsági szerepkörök használatával (alapértelmezett és egyéni szerepkörökkel). 
- Győződjön meg arról, hogy a megoldás megfelel minden vállalat- és iparág-specifikus szabályozási követelménynek. 
- Dokumentálja az összes funkciót, és szerezze be az ügyfél jóváhagyását. 

## <a name="mock-go-live"></a>Szimulált éles indítás

Az éles indítás előtt szimulálnia kell az éles indítást az örökölt rendszerekből az új rendszerbe való átváltáshoz szükséges lépések teszteléséhez. A szimulált éles indítást tesztkörnyezetben tanácsos elvégezni, és minden lépést foglaljon bele az átállási tervbe.

- Javasoljuk, hogy a működési környezetet használja ARANY konfigurációs környezetként, amíg az éles környezet el nem indul.
- Győződjön meg arról, hogy hatékony cégirányítási folyamat legyen bevezetve, hogy védje a működési környezetet az éles környezet aktiválása előtti a véletlen tranzakcióktól vagy frissítésektől.
- Ha készen áll az UAT vagy a szimulált éles indítás végrehajtására, frissítse a tesztkörnyezetet a működési környezetből. További tudnivalókért lásd: [Példány másolása](hr-admin-setup-copy-instance.md).
- Az átállási terv mindegyik lépését tesztelje a tesztkörnyezetben, majd ellenőrizze a tesztkörnyezetet villámellenőrzésekkel vagy a környezetben az UAT-parancsfájlok alapján elvégzett tesztekkel.
  - A teszteknek minden adatáttelepítést, köztük az éles indítás számára szükséges átalakításokat is tartalmazniuk kell.
  - A folyamatnak tartalmaznia kell a korábbi rendszerek gyakorlati elzárását is.
  - Ügyeljen arra, hogy az integrációs átállási lépéseket vagy a külső rendszer lépéseit belefoglalja a szimulált átállásba.
- Ha a szimulált átállás során bármilyen problémát talál, előfordulhat, hogy szükség lesz egy második szimulált átállásra. Ezért javasoljuk, hogy a projekttervben két szimulált átállást határozzon meg.

## <a name="fasttrack-go-live-assessment"></a>FastTrack élő indítási értékelés

Azok az ügyfelek, akik jogosultak a FastTrack-re, és akik FastTrack-megoldásépítésszel foglalkoznak, a Microsoft FastTrack-kel élő indítási értékelést teljesítenek azokat. További információért lásd: [Microsoft FastTrack](/dynamics365/fasttrack/). 

Körülbelül nyolc héttel az éles indítás előtt a FastTrack csapata megfogja kérni, hogy töltsön ki egy [Éles indítási ellenőrzőlistát](https://go.microsoft.com/fwlink/?linkid=2146013).

A projektmenedzsernek vagy egy kulcsfontosságú projekttagnak ki kell töltenie az éles indítási ellenőrzőlistát a projekt előtti időszakban. Az ellenőrzőlista általában négy-hat héttel a javasolt élő indítási dátum előtt készül el, amikor az UAT befejeződött vagy majdnem befejeződött. 

Miután elvégezte az élő indítási ellenőrzőlistát, küldje el e-mailben a FastTrack-megoldásépítésznek. Mindig adja meg az e-mailben az ügyfél és a megvalósítási partner egyik legfontosabb résztvevőjét. 

Az ellenőrzőlista elküldése után a FastTrack-megoldásépítész áttekinti a projektet, és értékelést készít, amely ismerteti a lehetséges kockázatokat, ajánlott eljárásokat és javaslatokat a projekt sikeres éles indításához. Bizonyos esetekben a megoldás-tervező kiemelheti a kockázati tényezőket, és kockázatcsökkentési tervet kérhet. 

## <a name="see-also"></a>Lásd még

[Éles indítás GYIK](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
