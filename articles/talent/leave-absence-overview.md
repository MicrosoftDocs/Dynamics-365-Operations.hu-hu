---
title: Szabadság és távollét kezelése
description: Ez a témakör a Szabadság- és távollét kezelési modulról ad áttekintést.
author: andreabichsel
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3376a9aec5c0003e9cc7c076c4d221a697df61ce
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461427"
---
# <a name="leave-and-absence-management"></a>Szabadság és távollét kezelése

A **Szabadság- és távollét kezelése** modul rugalmas keretrendszert biztosít a távollétet kezelő folyamat meghatározásához. Szabadság- és távolléti tervek hozhatók létre annak meghatározásához, hogyan történik az alkalmazottak elhatárolása vagy szabadságolása. Amint regisztrálnak egy tervbe, az alkalmazottak távolléti kérelmeket nyújthatnak be a vezetőkhöz jóváhagyásra. A szabadság nyomon követése lehetővé teszi, hogy az első szintű vezető és az emberi erőforrás (HR) vezető egyaránt megtekinthessék, ki van szabadságon, és mennyi ideje van még hátra.  

A Szabadság és távollét kezelése a következő funkciókkal rendelkezik: 

- **Szabadság- és távolléttípusok meghatározása**

    A Szabadságtípusok meghatározzák az alkalmazottak számára elérhető különböző típusú távolléteket. Mivel ezek a típusok a felhasználó által definiáltak, testreszabhatóak a szervezet számára. Néhány jellemző Szabadságtípus a fizetett szabadság (PTO), szabadság, rövid távú fogyatékosság, esküdtszéki kötelezettség (ez a szabadságtípus csak az Egyesült Államokra jellemző) és gyász. 

- **Határozza meg a vállalkozásához illeszkedő szabadság- és távolléti terveket.**

    A szabadság- és távolléti tervek úgy határozhatók meg, hogy a könyvelés meghatározott gyakorisággal történjen, például éves, havi vagy félhavi gyakorisággal. A tervek meghatározhatók támogatásként, ahol egyetlen könyvelés történik egy meghatározott dátumon. 

    A szabadságtervek gyakran tartalmaznak rétegeket, ahol bizonyos alkalmazottcsoportok további juttatásokat kapnak a vállalatnál eltöltött idejük alapján. A felhasználó által definiált rétegek lehetővé teszik a további juttatási órákba történő automatikus beléptetést a meghatározott dátumfeltételek alapján. A szabadságtervek beállíthatók úgy is, hogy maximális átviteli összeget vagy minimális egyenleget érvényesítsenek, megakadályozva, hogy az alkalmazottak az összegyűjtött juttatási órákat meghaladó juttatási óraszámot használjanak. 

    A tipikus szabadságtervek közé tartoznak a többszintű tervek, amelyek az új alkalmazottaknak 80 órás fizetett szabadságot adnak, és 60 hónapos munkavégzés után 120 órát. A további tervek mozgatható szabadságolást vagy a pozícióalapú juttatásokat tartalmazhatnak, például csak az ügyvezetőknek járó juttatási órákat.

- **Vegye fel az alkalmazottakat a szabadság- és távolléti tervekbe egyénileg vagy a feladatfeltételek alapján történő tömeges hozzárendeléssel.**

    Több feladattal kapcsolatos szűrő használható egy alkalmazotti csoport szabadságtervhez történő hozzárendeléséhez. A HR-vezetők megtekintheti, hogy az alkalmazott milyen szabadság- és távolléti tervbe van felvéve. Alternatív megoldásként a HR-vezetők megtekinthetik az összes tervet és a kapcsolódó alkalmazotti jogosultságokat.

- **Szabadság- és távolléti tervek felfüggesztése**

    A szabadság- és távolléti tervek felfüggeszthetők ezek inaktívvá tétele és a további könyvelések megakadályozása érdekében. A könyvelést a rendszer az alkalmazott munkaviszonyának befejeződésekor felfüggeszti.  

- **Jogosultságok és támogatások állíthatók be.**

    Az alkalmazott magasabb tervszintbe vehető fel egy dolgozóspecifikus dátum segítségével, amely felülírja az alkalmazott alapértelmezett ajánlatát. Az alkalmazottak manuálisan módosíthatják szabadság- és távolléti egyenlegüket a felvétel időpontjában, vagy a HR-es tetszőleges időpontban manuálisan helyesbítheti az adatokat. 

- **Használjon munkafolyamatot a távolléti kérésekre.**

     A munkafolyamatot testre szabhatja és a távolléti kérelmekre alkalmazhatja a szervezete követelményeinek megfelelően.  

- **Kövesse nyomon az alkalmazottak távolléti egyenlegét.**

    Az alkalmazottak, a felettesük és a HR-es megtekinthetik a szabadság- és távolléti egyenlegeket. A HR-vezető interaktív jelentések segítségével nyomon követheti a tervbe való belépés és távollét egyenlegét típus szerint. 

- **Távolléti kérelmek beadása.**

    Az alkalmazottak távolléti kérelmeket nyújthatnak be a rendelkezésre álló órák számához képest. A kérelmek egyszerű egynapos kérelmek vagy több napos kérelmek lehetnek, amelyek többféle szabadság- és távolléti típust tartalmaznak. Ha a munkafolyamat nincs engedélyezve, a rendszer automatikusan jóváhagyja a kéréseket. Ha munkafolyamat engedélyezve van, a jóváhagyás lehet automatikus vagy be lehet állítani egy láttamozást a munkafolyamat-konfigurációjától függően.


[!INCLUDE[footer-include](../includes/footer-banner.md)]