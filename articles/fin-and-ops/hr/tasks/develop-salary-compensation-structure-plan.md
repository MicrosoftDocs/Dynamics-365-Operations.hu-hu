---
title: Munkabér-/kompenzációs struktúra és terv kialakítása
description: Ez a feladat-útmutató végigvezeti a folyamaton, amely létrehozza a Fix kompenzációs konstrukciót és az alkalmazhatósági szabályok által engedélyezi alkalmazottaknak konstrukcióba való bevitelét.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f0732736736fdc87f3367f24b1d20b9fa6efc59
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/30/2019
ms.locfileid: "1794904"
---
# <a name="develop-salarycompensation-structure-and-plan"></a>Munkabér-/kompenzációs struktúra és terv kialakítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató végigvezeti a folyamaton, amely létrehozza a Fix kompenzációs konstrukciót és az alkalmazhatósági szabályok által engedélyezi alkalmazottaknak konstrukcióba való bevitelét. E feladat létrehozása az USMF bemutatócég segítségével történt, a feladat a Kompenzációkért és juttatásokért felelős vezetők részére készült.


## <a name="create-fixed-compensation-plan"></a>Fix kompenzációs konstrukció létrehozása
1. Kattintson a Kompenzációkezelés menüpontra.
2. Kattintson a Fix kompenzációs konstrukciók lehetőségre.
3. Kattintson az Új lehetőségre.
4. Érték beírása a Konstrukció mezőbe.
5. A Leírás mezőben adjon meg egy értéket.
6. Adja meg a dátumot az Érvényesség dátuma mezőben.
7. A Típus mezőben válassza ki, hogy a Fix kompenzációs konstrukció egy Sáv, egy Osztály vagy Lépés típusú terv legyen.
8. Az Ajánlás engedélyezve jelölőnégyzet alapértelmezett értékként viselkedik minden olyan műveletnél, amelyet ehhez konstrukcióhoz hozzáadtak a Feldolgozási eseményben.  Az ajánlások engedélyezése lehetővé teszi, hogy a kiszámított irányösszeget a kompenzációs feldolgozásakor felülbírálhassa.
9. Tartományon kívüliség tűréshatára lehetővé teszi, hogy megadja, hogyan szeretné kezelni a megadott kompenzációs struktúratartományon kívül eső kompenzációs összegeket.  A Nincs tartományon kívüliség tűréshatára bármely kompenzációs összeg használatát lehetővé teszi.  A Puha tűréshatár arra figyelmezteti a felhasználót, hogy a kompenzáció összege kisebb, mint a minimális hivatkozási pont összege, vagy nagyobb, mint a maximális összege, az adott szint esetében. A felhasználó figyelmen kívül hagyhatja a figyelmeztetést és folytathatja a folyamatot.  A Kemény tűréshatár hibát generál, ha az alkalmazott kompenzációja a minimális és maximális hivatkozási pontokon kívül van beállítva az adott szint esetében, és automatikusan korrigálja az alkalmazott kompenzációját, hogy az a tartományba essen.
10. A Felvételi szabály mező akkor kerül használatba, amikor egy Kompenzáció-feldolgozási esemény fut az alkalmazott kompenzációjának kiszámításához.  A Százalék Felvételi szabálya azt a növekedést számítja ki, amelyet arra az időszakra arányosítanak, amennyire a dolgozót a ciklusban alkalmazták.
11. Érték beírása a Pénznem mezőbe.
12. A Fizetési díjalap átalakítása mezőben adjon meg vagy válasszon ki egy értéket.
13. Bontsa ki a Tartomány-kihasználtsági mátrix szakaszt.
    * Tetszés szerint hozzáadhat tartománykihasználtsági rekordokat, hogy az alkalmazottak gyorsabban eljuthassanak a középső pontjukig, és lassabban érjék el tartományuk maximumát.  
14. Ezen a ponton el kell mentenie a Fix kompenzációs konstrukció, hogy engedélyezni tudja a Kompenzációs gomb beállítását, valamint folytathassa a konstrukcióhoz tartozó kompenzációs struktúrájának meghatározását.  Kattintson a Mentés gombra.
15. Kattintson a Kompenzáció beállítása gombra.
    * Háromféleképpen hozhat létre a kompenzációs struktúrát. 1: teljesen új struktúra létrehozása hivatkozási pontok sorozatának kiválasztásával és a szintek hozzáadásával saját struktúra létrehozásához. 2: kompenzációs szerkezet másolása egy kiindulási pontként szolgáló meglévő tervből, majd annak egy új tervre történő módosítása. 3: egy meglévő kompenzációs rács kiválasztása. Ha a kompenzációs rácsot már használja egy másik terv, a rácson végzett módosítások is megjelennek a másik tervben.  
16. Válassza ki az Új kompenzációs mátrix létrehozása egy meglévőből beállítást.
17. A Másolás rácsból mezőben adjon meg vagy válasszon ki egy értéket.
    * Az új kompenzációs rács nevét tetszés szerint módosíthatja, ami a kiválasztott rács másolataként jön majd létre.  
18. Kattintson az OK gombra.
19. Kattintson a Tömeges módosítás elemre.
    * A tömeges módosítás az egy vagy több szinthez és/vagy hivatkozási pontokhoz tartozó százalék- vagy fixösszegnövelés alkalmazása által lehetővé teszi a kompenzációs mátrix összegek karbantartását.  
20. A Kiigazítás összege mezőben adjon meg egy számot.
21. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
22. Kattintson az Alkalmazás a rácsra elemre.
23. Zárja be a lapot.
    * A kompenzációs struktúra létrehozása vagy kiválasztása után kiválaszthatja, hogy mely hivatkozási pontokat használja a Fix kompenzációs konstrukció Ellenőrzőpontjaként.  Az Ellenőrzőpont az alkalmazott Kompenzációs arányának kiszámítására szolgál.  
24. Az Ellenőrzőpont mezőben adjon meg vagy válasszon ki egy értéket.
25. Zárja be a lapot.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Hozzon létre egy alkalmazhatósági szabályt az új Fix kompenzációs konstrukcióhoz
    * Az új Fix kompenzációs konstrukció nem rendelhető alkalmazotthoz, amíg az Alkalmazhatósági szabályokat nem határoztak meg a konstrukcióhoz.  
1. Kattintson a Jogosultsági szabályok elemre
2. Kattintson az Új lehetőségre.
3. Érték beírása az Alkalmazhatósági mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Adja meg a dátumot az Érvényesség dátuma mezőben.
    * Az Alkalmazhatósági szabályok mind a Fix, mind pedig a Változó kompenzációs konstrukciókra vonatkoznak.  A Típus mezőben jelölje ki, hogy ezek az alkalmazhatósági szabályok milyen típusú konstrukcióra vonatkoznak.  
6. A Terv mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki azokat a feltételeket, amelyeknek egy alkalmazottnak meg kell felelnie annak érdekében, hogy a kompenzációs konstrukció érvényes legyen rá. A feltételek közé tartozhat a Részleg, a Szakszervezet, a Hely (Kompenzációs régió), a Feladat, a Funkció, a Feladattípus vagy a Kompenzációs szint. Az alkalmazottnak minden megadott feltételt teljesítenie kell ahhoz, hogy a kompenzációs konstrukció érvényes legyen rá. Ha nincs megadva feltétel, minden alkalmazottra érvényes a kompenzációs konstrukció. Ha egy alkalmazott nem felel meg az alkalmazhatósági szabályban megadott feltételeknek, vagy egy alkalmazhatósági szabály nem volt megadva a kompenzációs konstrukcióhoz, a kompenzációs konstrukció nem fog megjelenni a Keresésben az alkalmazotthoz tartozó Fix kompenzációs rekord létrehozásakor.  
7. Zárja be a lapot.
8. Zárja be a lapot.

