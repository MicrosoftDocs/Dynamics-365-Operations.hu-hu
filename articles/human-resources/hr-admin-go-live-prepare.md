---
title: Felkészülés a Human Resources éles indításra
description: Ez az oldal útmutatást nyújt a Dynamics 365 Human Resources rendszer éles indítására való felkészüléshez.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 59d7274c3b40e78209d90960c4514321b736876a
ms.sourcegitcommit: b40d6ce45aeb07724fc41d1a41923970b007fbcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/14/2020
ms.locfileid: "4418925"
---
# <a name="prepare-for-human-resources-go-live"></a>Felkészülés a Human Resources éles indításra

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
| 5 | Adatcsomag importálásai | A projekttől függ | Partner/vevő | Kövesse az [adatkezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages) című témakör utasításait.|
| 6 | Termelés kész | Az összes korábbi lépés befejezése után | Partner/vevő | A partner/ügyfél átveheti az éles környezet irányítását.|
| 7 | Átállási tevékenységek | A projekttől függ | Partner/vevő | |
| 8 | Éles indítás | A projekttől függ | Vevő | |

> [!IMPORTANT]
> *A 3. és 4. lépést csak azoknál a vevőknél kell kitölteni, akik megfelelnek a FastTrackhez.

## <a name="completing-the-lcs-methodology"></a>Az LCS-módszertan kitöltése

Az egyes megvalósítási projektek egyik fő mérföldköve az éles környezetre való átállás. 

Annak érdekében, hogy az éles környezet élő műveletekhez való használható legyen, a Microsoft csak akkor biztosítja az éles példányt, ha a megvalósítás közeledik az **Üzemeltetés** fázishoz, miután az LCS-módszertanban szükséges tevékenységek befejeződtek. Az előfizetés környezeteiről a  [Dynamics 365 licencelési útmutatójában](https://go.microsoft.com/fwlink/?LinkId=866544) talál további információt. 

Az ügyfeleknek teljesíteniük kell az LCS módszertan **Elemzés**, **Tervezés és fejlesztés** és **Tesztelés fázisát**, mielőtt elérhetővé válik a  **Konfigurálás**  gomb az éles környezet kéréséhez. Az LCS fázisának befejezéséhez először be kell fejeznie minden szükséges lépést ebben a fázisban. Ha egy fázis összes lépése befejeződött, befejezheti az egész fázist. Ha módosításokat kell végrehajtania, később bármikor újra megnyithatja a fázist. További információért tekintse át a  [Lifecycle Services (LCS) a Finance and Operations alkalmazások ügyfeleihez](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs) szolgáltatáshoz. 

A lépés befejezése folyamat két részből áll: 

- Végezze el a tényleges munkát, például a illeszkedési/hiányelemzést vagy a felhasználói elfogadási tesztelést (UAT). 
- Jelölje meg a megfelelő lépést az LCS-módszertanban befejezettként. 

Ez egy jó gyakorlat, hogy a lépéseket a módszertanban úgy töltse ki, ahogy előrehalad a végrehajtással. Ne várjon az utolsó pillanatig. Ne csak kattintsa végig az összes lépést, hogy eljusson az éles környezethez. Az ügyfél érdeke, hogy szilárd megvalósítása legyen. 

## <a name="uat-for-your-solution"></a>UAT az Ön megoldásához

Az UAT-fázisban a megvalósítási projekt tesztkörnyezetében tesztelnie kell az összes megvalósított üzleti folyamatot és az ön által végrehajtott testreszabásokat. A sikeres éles indítás érdekében az UAT-fázis befejezésekor vegye figyelembe a következőket: 

- A vizsgálati esetek a követelmények teljes körét lefedik. 
- Teszteljen az áttelepített adatok használatával. Ezeknek az adatoknak törzsadatokat kell tartalmazniuk, például dolgozókat, feladatokat és beosztásokat. A nyitó egyenlegeket is tartalmazzák, például a szabadság és a távolléti időbeli elhatárolásokat. Végül tartalmazzák a nyitott tranzakciókat, például az aktuális juttatási beléptetéseket. Teljes tesztelés minden típusú adattal, még akkor is, ha az adatkészlet nincs véglegesítve. 
- Tesztelje a felhasználókhoz rendelt megfelelő biztonsági szerepkörök használatával (alapértelmezett és egyéni szerepkörökkel). 
- Győződjön meg arról, hogy a megoldás megfelel minden vállalat- és iparág-specifikus szabályozási követelménynek. 
- Dokumentálja az összes funkciót, és szerezze be az ügyfél jóváhagyását. 

## <a name="fasttrack-go-live-assessment"></a>FastTrack élő indítási értékelés

Azok az ügyfelek, akik jogosultak a FastTrack-re, és akik FastTrack-megoldásépítésszel foglalkoznak, a Microsoft FastTrack-kel élő indítási értékelést teljesítenek azokat. További információért lásd: [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Körülbelül nyolc héttel az éles indítás előtt a FastTrack csapata megfogja kérni, hogy töltsön ki egy [Éles indítási ellenőrzőlistát](https://go.microsoft.com/fwlink/?linkid=2146013).

A projektmenedzsernek vagy egy kulcsfontosságú projekttagnak ki kell töltenie az éles indítási ellenőrzőlistát a projekt előtti időszakban. Az ellenőrzőlista általában négy-hat héttel a javasolt élő indítási dátum előtt készül el, amikor az UAT befejeződött vagy majdnem befejeződött. 

Miután elvégezte az élő indítási ellenőrzőlistát, küldje el e-mailben a FastTrack-megoldásépítésznek. Mindig adja meg az e-mailben az ügyfél és a megvalósítási partner egyik legfontosabb résztvevőjét. 

Az ellenőrzőlista elküldése után a FastTrack-megoldásépítész áttekinti a projektet, és értékelést készít, amely ismerteti a lehetséges kockázatokat, ajánlott eljárásokat és javaslatokat a projekt sikeres éles indításához. Bizonyos esetekben a megoldás-tervező kiemelheti a kockázati tényezőket, és kockázatcsökkentési tervet kérhet. 

## <a name="see-also"></a>Lásd még

[Éles indítás GYIK](hr-admin-go-live-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]