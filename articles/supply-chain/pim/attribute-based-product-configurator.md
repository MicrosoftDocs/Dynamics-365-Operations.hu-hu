---
title: Attribútumalapú értékesítési árak a megszorításon alapuló termékkonfigurációhoz
description: Ez a témakör leírja, hogyan lehet értékesítési ármodelleket felépíteni, ahol az eladási árak összetevőkön és attribútumokon alapulnak, nem pedig a fizikai anyagjegyzéken és az útvonalon.
author: sorenva
manager: tfehr
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: c0f9c1bb94b4dcc3c3c1e7656868ef6e6bd903db
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429183"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Attribútumalapú értékesítési árak a megszorításon alapuló termékkonfigurációhoz

Ez a témakör leírja, hogyan lehet értékesítési ármodelleket felépíteni, ahol az eladási árak összetevőkön és attribútumokon alapulnak, nem pedig a fizikai anyagjegyzéken és az útvonalon. Minden egyes termékkonfigurációs modellhez több eladásiár-modellt lehet létrehozni.

## <a name="set-relevant-product-information-management-parameters"></a>Releváns termékinformáció-kezelési paraméterek beállítása

Az ármodellek összeállításának megkezdése előtt meg kell határoznia egy alapértelmezett pénznemet, amelyet az eladási ármodellek összeállításakor használ. Azt is beállíthatja, hogy csatol-e Microsoft Excel-fájlt az árak részletezésével az összes rendelésre vagy az árajánlati sorokra vonatkozóan. Az árbontás lehetővé teszi, hogy részleteket osszon meg az ügyfelekkel arról, hogyan jutott el egy konfigurált termék adott értékesítési árához.

Az alapértelmezett pénznem beállítása:

1. Lépjen a **Termékinformáció-kezelés \> Beállítás \> Termékinformáció-kezelés paraméterei** elemre.
1. Nyissa meg a **Megszorításon alapuló termékkonfigurációs modellek** lapot.
1. Nyissa meg az **alapértelmezett pénznem** legördülő listát, és válassza ki a kívánt pénznemet.

    ![A megszorításon alapuló termékkonfiguráció alapértelmezett pénznemének beállítása](media/prod-config-currency.png "A megszorításon alapuló termékkonfiguráció alapértelmezett pénznemének beállítása")

1. Ha szeretné csatolni az összes rendelési vagy árajánlati sor árának részletezését tartalmazó Excel-fájlt, akkor az **Ármodell** szakaszban a **Csatolás** elemet állítsa *Igen*-re.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Eladásiár-modell létrehozása

Eladásiár-modell létrehozása:

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Válassza ki a cél termékkonfigurációs modellt.
1. A Művelet panelen nyissa meg a **Modell** lapot, és a **Beállítások** csoportban válassza az **Ármodellek** elemet.
1. Megnyílik az **Ármodellek** lap.
1. Válasszon ármodellt, vagy adjon hozzá újat a rácshoz.
1. A **Szerkesztés** elem kiválasztásával nyissa meg a választott modell szerkesztési lapját, amely a következő lehetőségeket kínálja:
    - A fejléc megjeleníti az alapértelmezett pénznemet, és lehetőséget ad új pénznem hozzáadására az árbeállításnál.
    - A bal oldali ablakban látható a termékmodell minden összetevője és a felhasználói igények. A termékmodellfa minden csomópontja rendelkezhet egy alapár-kifejezéssel és tetszőleges számú kifejezésszabállyal. A kifejezésszabály egy feltételből és egy kifejezésből áll; a kifejezésszabályok olyan termékopciókra vonatkoznak, amelyek segítik a termék árának beállítását.
    - A feltételek és kifejezések összeállításánál ugyanazok a műveletek használhatók, mint a termékmodellek kalkulációjánál. A kifejezésszerkesztő is támogatja a feltételeket és a kifejezéseket.
1. Válassza ki a csomópontot a bal oldali oszlopban, majd az előző lépésben ismertetett szolgáltatások alapján határozza meg az árképzési szabályokat (lásd az eljárás után látható példát is). Szükség szerint ismételje meg ezt a lépést minden csomópontnál.

A következő példa egy 899,95 EUR értékű alapárat mutat be, amely a vevő által kiválasztott konfigurációtól függően a következő öt kifejezésszabály közül egy vagy több alkalmazásával módosítható:

- Fehér doboz esetén 59,95 eurót le kell vonni.
- A sarokvédelem esetén 35,95 eurót hozzá kell adni.
- Ha az előlapi rács fém, 89,95 eurót hozzá kell adni.
- Rózsafa dobozborítás esetén 119,95 eurót hozzá kell adni.
- 12,95 euró hozzáadása, hangszóró-magasságegységenként.

![Példa ármodellre](media/prod-config-rules-example.png "Példa ármodellre")

## <a name="add-support-for-multiple-currencies"></a>Több pénznem támogatásának hozzáadása

Egy konfigurálható termék értékesítésekor a rendszer ellenőrzi, hogy az árak a vevő pénznemében lettek-e beállítva. Ha igen, akkor a program a megadott értékeket használja. Ha nem, akkor a rendszer az értékesítési vállalathoz meghatározott árfolyamokat használja az alapértelmezett pénznemben kifejezett értéknek a vevő pénznemére történő átváltására.

Explicit árak megadása más pénznemben:

1. Nyissa meg az ármodell szerkesztési oldalát, az [Eladásiár-modell létrehozása](#build-price-model) részben leírtak szerint.
1. Válassza ki a **Hozzáadás** gombot az ármodell fejlécében a rendelkezésre álló pénznemeket megjelenítő **Pénznemek** legördülő párbeszédpanel megnyitásához.
1. Válassza ki a **Pénznemek** legördülő párbeszédpanelen azt a pénznemet, amelyet hozzá szeretne adni, majd kattintson az **OK** gombra.
1. Az **Aktuális pénznem** legördülő lista tartalmazza a most hozzáadott pénznemet, valamint minden korábban már hozzáadott pénznemet. Válassza ki az új pénznemet, és figyelje meg, hogy a **Kifejezésszabályok** szakaszban levő rács két kifejezésmezőt tartalmaz:
    - **Kifejezés** – az **Aktuális pénznemnek** éppen kiválasztott pénznemben megadott ár létrehozásánál használt kifejezés (vagy konstans érték).
    - **Alapértelmezett kifejezés** – Az alapértelmezett pénznemben (ez az **Alapértelmezett pénznem** mezőben található) megadott ár létrehozásánál használt kifejezés (vagy konstans érték).

    > [!NOTE]
    > A kifejezésszabályok **Feltétel** mezője az alapértelmezett pénznemé, ami azt jelenti, hogy nem lehet módosítani a feltételt más pénznemekre. Nem adhat hozzá új kifejezésszabályt, míg az alapértelmezettől eltérő pénznem a kijelölt **Aktuális pénznem**.
1. Szükség szerint módosítsa a **Kifejezés** oszlop értékeit az aktuális pénznemnek megfelelően.

A következő példában az _EUR_ az alapértelmezett pénznem, az _USD_ pedig a „további pénznem”.

![Példa több pénznemet tartalmazó modellre](media/prod-config-rules-currency-example.png "Példa több pénznemet tartalmazó modellre")

> [!NOTE]
> Nem adható hozzá olyan kifejezésszabály, amely csak a nem alapértelmezett pénznemben érvényes. Ha olyan kifejezést szeretne létrehozni, amely csak az alapértelmezett pénznemtől eltérő pénznemre vonatkozik, akkor az alapértelmezett pénznem árkifejezését állítsa nullára. Ezt követően állítsa be a megfelelő kifejezést a nem alapértelmezett pénznemre.

## <a name="test-your-price-model"></a>Az ármodell ellenőrzése

Az eladási árak konfigurációs munkamenetben való működésének ellenőrzéséhez nyissa meg az ármodell szerkesztési oldalát az [Eladásiár-modell létrehozása](#build-price-model) alatt leírtak szerint, majd válassza a **Teszt** elemet a Művelet panelen. Megnyílik a **Termékmodell tesztelése** párbeszédpanel, ahol a következők elvégzése lehetséges:

- Az itt felajánlott konfigurációs beállításokkal válassza ki a termékopciókat, majd vizsgálja meg, hogyan hatnak az **Ár és szállítási dátum** feltüntetett értékeire.
- Válassza **Az árbontás megtekintése** lehetőséget egy olyan Excel-dokumentum letöltéséhez, amely az ár számítási részleteit tartalmazza.

![A termékmodell ellenőrzése](media/prod-config-test.png "A termékmodell ellenőrzése")

A letöltött táblázat az ár minden aktív elemét megjeleníti abszolút értékben és a teljes ár százalékában is. Ha beállította a **Csatolás** ármodellopciót a **Termékinformáció-kezelés paraméterei** lapon, , akkor ez az Excel-munkalap hozzákapcsolódik a rendeléshez vagy az ajánlati sorhoz.

![Árbontást tartalmazó Excel-táblázat](media/prod-config-excel-example.png "Árbontást tartalmazó Excel-táblázat")

## <a name="set-up-selection-criteria-for-price-models"></a>Ármodellek kiválasztási kritériumainak beállítása

Ha az ármodelljei használatban vannak, akkor legalább egy kiválasztási kritériumot meg kell határoznia az ármodell felvételéhez, amikor árajánlatot vagy megrendelést állít be. Ezt egy vagy több lekérdezés beállításával teheti meg. A megfelelő eladásiár-modellekkel együtt a lekérdezések nagy rugalmasságot biztosítanak a vevők, régiók, időszakok és egyéb szempontok szerinti célárak elkészítésénél.

Ármodellek kiválasztási kritériumainak beállítása:

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Válassza ki a cél termékkonfigurációs modellt.
1. A Művelet panelen nyissa meg a **Modell** lapot, és a **Beállítások** csoportban válassza az **Ármodellfeltételek** elemet. Megnyílik az **Ármodellfeltételek** lap.
1. Ha a keresett sor még nem létezik, akkor a Művelet panelen válassza az **Új** parancsot, ha új sort szeretne hozzáadni a rácshoz, és végezze el a következő beállításokat:
    - **Név** – Írja be a sor nevét.
    - **Leírás** – Röviden írja le a lekérdezést, és azt, hogy mire használható.
    - **Ármodell** – Válasszon [ármodellt](#build-price-model) (az aktuális konfigurációs modellből), amelyet a lekérdezés az aktiváláskor alkalmazni fog.
    - **Rendelés típusa** – Válassza ki a rendeléstípust, amelyre a lekérdezés vonatkozik.
    - **Érvényesség kezdő dátuma** – Adja meg a lekérdezés első napját.
    - **Érvényesség vége** – Adja meg a lekérdezés utolsó napját.

    ![Ármodellfeltételek](media/prod-config-price-model-criteria.png "Ármodellfeltételek")

1. Válassza ki a sort a meghatározni kívánt lekérdezéshez, majd válassza a **Szerkesztést** a **Művelet panelen**. Megnyílik a lekérdezéstervező párbeszédpanel. Úgy működik, mint a legtöbb lekérdezéstervező a Supply Chain Managementben. Használatával meghatározható, hogy milyen feltételek mellett kell alkalmazni a kiválasztott sor ármodelljét.

1. Ismételje meg a 4–5. lépést minden lekérdezésnél.
    > [!TIP]
    > Időt takaríthat meg, ha egy meglévő sort másol, amely hasonlít az újhoz, amelyet hozzá kell adnia. Ehhez válasszon ki egy célsort, majd válassza a **Másolás** elemet a Művelet panelen.

1. Ha befejezte a feltételek beállítását, rendezze azokat megfelelő sorrendbe az **Ármodellfeltételek** listában. Egy sor áthelyezéséhez válassza ki a sort, majd válassza a **Fel** vagy **Le** lehetőséget a Művelet panelen.

    > [!IMPORTANT]
    > A konfiguráláskor a rendszer a listában felülről kezd keresni, és az első lekérdezést használja, amelynél egyeznek az adatok az ajánlat vagy a rendelési sor adataival. Emiatt a legrészletesebb lekérdezések legyenek felül. Ha egy általános lekérdezést helyez a lista elejére, akkor ezt alkalmazza a rendszer még akkor is, ha a lista végén van olyan lekérdezés, amely a konfiguráció pontos ügyfelét vagy potenciális vevőjét kérdezi le.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Attribútumalapú eladási árak megadása a termékmodell-verzióhoz

Az utolsó lépés az attribútumalapuló eladási árak megadása a termékmodell-verzióhoz. Megvalósítás:

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Válassza ki a cél termékkonfigurációs modellt.
1. A Művelet panelen nyissa meg a **Modell** lapot, és a **Termékmodell részletei** csoportban válassza a **Verziók** elemet.
1. Megnyílik a **Verziók** lap. Az **Árképzési mód** beállítása legyen **Attribútumalapú**.
    ![Az árképzési mód beállítása attribútumalapúra](media/prod-config-versions.png "Az árképzési mód beállítása attribútumalapúra")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]