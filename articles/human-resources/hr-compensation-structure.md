---
title: Kompenzációs struktúra kialakítása
description: Ez a cikk végigvezeti a fix kompenzációs konstrukció létrehozásának és az alkalmazottak konstrukcióba való regisztrálásának folyamatán alkalmazhatósági szabályokon keresztül.
author: andreabichsel
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abdca618aa544e32b68f4bbf2578afb9ef1a5905
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052889"
---
# <a name="develop-a-compensation-structure"></a>Kompenzációs struktúra kialakítása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk végigvezeti a fix kompenzációs konstrukció létrehozásának és az alkalmazottak konstrukcióba való regisztrálásának folyamatán alkalmazhatósági szabályokon keresztül. Ez a cikk a USMF bemutató adatait használja, és a kompenzációs és juttatási vezetőket érinti.

## <a name="create-a-fixed-compensation-plan"></a>Fix kompenzációs konstrukciók létrehozása

1. Válassza a **Kompenzációkezelés** pontot.

2. Válassza a **Fix kompenzációs konstrukciók** elemet.

3. Válassza az **Új** lehetőséget.

4. A **Konstrukció** mezőben adjon meg egy értéket.

5. A **Leírás** mezőben adjon meg egy értéket.

6. Adja meg a dátumot az **Érvényesség dátuma** mezőben.

7. A **Típus** mezőben válassza ki, hogy a Fix kompenzációs konstrukció **Sáv**, **Osztály** vagy **Lépés** típusú konstrukció legyen.

8. Az **Ajánlás engedélyezve** jelölőnégyzet alapértelmezett értékként viselkedik minden olyan műveletnél, amelyet ehhez konstrukcióhoz hozzáadtak a Feldolgozási eseményben. Az ajánlások engedélyezése lehetővé teszi, hogy a kiszámított irányösszeget a kompenzációs feldolgozásakor felülbírálhassa.

9. **Tartományon kívüliség tűréshatára** mező lehetővé teszi, hogy megadja, hogyan szeretné kezelni a megadott kompenzációs struktúratartományon kívül eső kompenzációs összegeket. A **Tartományon kívüliség tűréshatár** mező **Egyik sem** értékre való állításával bármely kompenzációs összeget használhatja. A **Puha tűréshatár** figyelmezteti a felhasználót, ha a kompenzáció összege kisebb, mint a minimális hivatkozási pont összege, vagy nagyobb, mint a maximális összege, az adott szint esetében. A felhasználók figyelmen kívül hagyhatják a figyelmeztetést és folytathatják a folyamatot. A **Kemény tűréshatár** hibát generál, ha az alkalmazott kompenzációja a minimális és maximális hivatkozási pontokon kívül van beállítva az adott szint esetében, és automatikusan korrigálja az alkalmazott kompenzációját, hogy az a tartományba essen.

10. A **Felvételi szabály** mező egy alkalmazott kompenzációját számítja ki a feldolgozási esemény során. A **Százalék** **Felvételi szabály** azt a növekedést számítja ki, amelyet arra az időszakra arányosítanak, amennyire a dolgozót a ciklusban alkalmazták.

11. Érték beírása a **Pénznem** mezőbe.

12. A **Fizetési díjalap átalakítása** mezőben adjon meg vagy válasszon ki egy értéket.

13. Bontsa ki a **Tartomány-kihasználtsági mátrix** szakaszt. Tetszés szerint hozzáadhat tartománykihasználtsági rekordokat, hogy az alkalmazottak gyorsabban eljuthassanak a középső pontjukig, és lassabban érjék el tartományuk maximumát.

14. Válassza a **Mentés** lehetőséget. Ez lehetővé teszi a **Kompenzáció beállítása** gombot, és folytathatja a kompenzációs struktúra definiálását a konstrukcióhoz.

15. Válassza a **Kompenzáció beállítása** lehetőséget. Kompenzációs struktúrát az alábbi három módszer egyikével hozhat létre:

    - Teljesen új struktúra létrehozása hivatkozási pontok csoportjának kiválasztásával és a szintek hozzáadásával saját struktúra létrehozásához.
    - Kompenzációs struktúra másolása egy kiindulási pontként szolgáló meglévő tervből, majd annak egy új tervre történő módosítása.
    - Egy meglévő kompenzációs rács kiválasztása. Ha a kompenzációs rácsot már használja egy másik terv, a rácson végzett módosítások is megjelennek a másik tervben.

16. Válassza az **Új kompenzációs mátrix létrehozása egy meglévőből** elemet.

17. A **Másolás rácsból** mezőben adjon meg vagy válasszon ki egy értéket. Az új kompenzációs rács nevét tetszés szerint módosíthatja, amit a kiválasztott rács másolataként hoz létre.

18. Válassza ki az **OK** lehetőséget.

19. Válassza a **Tömeges módosítás** lehetőséget. A **Tömeges módosítás** az egy vagy több szinthez vagy hivatkozási pontokhoz tartozó százalék- vagy fixösszegnövelés alkalmazása által lehetővé teszi a kompenzációs mátrix összegek karbantartását.

20. A **Kiigazítás összege** mezőben adjon meg egy számot.

21. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.

22. Kattintson az **Alkalmazás a rácsra** elemre.

23. Zárja be a lapot. A kompenzációs struktúra létrehozása után kiválaszthatja, hogy mely hivatkozási pontokat használja a Fix kompenzációs konstrukció Ellenőrzőpontjaként. Az ellenőrzőpont az alkalmazott Kompenzációs arányának kiszámítására szolgál.

24. Az **Ellenőrzőpont** mezőben adjon meg vagy válasszon ki egy értéket.

25. Zárja be a lapot.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Hozzon létre egy alkalmazhatósági szabályt az új fix kompenzációs konstrukcióhoz

Az új fix kompenzációs konstrukció nem rendelhető alkalmazotthoz, amíg az alkalmazhatósági szabályokat nem határoztak meg a konstrukcióhoz.  

1. Válassa az **Alkalmazhatósági szabályok** pontot.

2. Válassza az **Új** lehetőséget.

3. Az **Alkalmazhatóság** mezőben adjon meg vagy válasszon ki egy értéket.

4. A **Leírás** mezőben adjon meg egy értéket.

5. Adja meg a dátumot az **Érvényesség dátuma** mezőben. Az alkalmazhatósági szabályok mind a fix, mind pedig a változó kompenzációs konstrukciókban használhatók. A **Típus** mezőben válassza ki a konstrukció típusát.

6. A **Terv** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki azokat a feltételeket, amelyeknek egy alkalmazottnak meg kell felelnie annak érdekében, hogy a kompenzációs konstrukció érvényes legyen rá. A feltételek a következők lehetnek:

    - **Részleg**
    - **Szakszervezet**
    - **Hely** (**Kompenzációs régió**)
    - **Munka**
    - **Funkció**
    - **Feladattípus**
    - **Kompenzációs szint**
    
    Az alkalmazottnak minden megadott feltételt teljesítenie kell ahhoz, hogy a kompenzációs konstrukció érvényes legyen rá. Ha nem ad meg feltétel, minden alkalmazottra érvényes a kompenzációs konstrukció. Ha egy alkalmazott nem felel meg az alkalmazhatósági szabályban megadott feltételeknek, vagy egy alkalmazhatósági szabály nem volt megadva a kompenzációs konstrukcióhoz, a kompenzációs konstrukció nem fog megjelenni a keresésben az alkalmazotthoz tartozó Fix kompenzációs rekord létrehozásakor.

7. Zárja be a lapot.

8. Zárja be a lapot.



[!INCLUDE[footer-include](../includes/footer-banner.md)]