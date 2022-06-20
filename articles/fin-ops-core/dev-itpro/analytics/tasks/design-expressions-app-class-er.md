---
title: ER-kifejezések tervezése az alkalmazásosztályú metódusok meghívására (ER)
description: Ez a témakör azt ismerteti, hogyan lehet újra felhasználni az elektronikus jelentési konfigurációk meglévő alkalmazáslogikát az alkalmazásosztályok szükséges metódusának hívhatók.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0fb0a9725d882fdc330d7adbb49bd3dcadf7805f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883625"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>ER-kifejezések tervezése az alkalmazásosztályú metódusok meghívására (ER)

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, [hogyan lehet újra felhasználni az elektronikus jelentési (ER)](../general-electronic-reporting.md) konfigurációk meglévő alkalmazáslogikát az ER-kifejezésekben szükséges alkalmazásosztály-metódusok hívhatók meg. Az osztályok hívása esetén az argumentumok értékei dinamikusan definiálhatók futásidőben. Az értékek például az elemzési dokumentumban található információkon alapulnak a helyesség biztosítása érdekében.

Ebben a példában egy olyan folyamatot tervez, amely a bejövő banki kivonatokat egy alkalmazásadat-frissítésre használja. A bejövő banki kivonatokat szöveges (.txt) fájlokként fogja kapni, amelyek nemzetközi bankszámlaszám -kódokat (International Bank Account Number – IBAN) tartalmaznak. A banki kivonatok importálásának részeként a már elérhető logika alkalmazásával ellenőrizni kell az IBAN-kód helyességét.

## <a name="prerequisites"></a>Előfeltételek

A következő eljárásokat olyan felhasználóknak **szántuk** **, akik be vannak osztva a Rendszergazda vagy az Elektronikus jelentéskészítés fejlesztői szerepkörrel.**

Az eljárás bármelyik adathalmazt be lehet állítani.

A letöltéshez le kell töltenie és mentenie kell a következő fájlt: [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

Ebben a cikkben létrehozhatja a szükséges ER-konfigurációkat a Litware, Zrt. mintavállalat számára. Ezért mielőtt a ebben a cikkben eljárást végrehajtania kell, ezeket a lépéseket kell végrehajtania.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A honosítási **konfigurációs** lapon ellenőrizze, **hogy a Litware, Inc.** mintavállalat konfigurációszolgáltatója elérhető-e és aktívként van-e megjelölve. Ha nem látja ezt a konfigurációs szolgáltatót, először végre kell hoznia a Konfigurációszolgáltató létrehozása lépést, [és aktívként kell megjelölnie őket](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció importálása

1. A Honosítási **konfigurációk** lapon **·**, a Konfigurációszolgáltatók szakaszban válassza ki **a Microsoft** konfigurációs szolgáltató csempeit.
2. Válassza ki a **Tárházak** lehetőséget.
3. A Honosítási **tárház oldalon** válassza a Szűrők **megjelenítése lehetőséget**.
4. A globális tárházrekord kiválasztásához adjon hozzá egy **Név szűrőmezőt**.
5. A Név **mezőben** adja meg a Globális **mezőt**. Ezután válassza a szűrő **operátort**.
6. Válassza az **Alkalmazás** lehetőséget.
7. A **[kijelölt](../er-download-configurations-global-repo.md#open-configurations-repository)** tárházban található ER-konfigurációk listájának ellenőrzéshez válassza a Megnyitás lehetőséget.
8. Válassza ki **a Kifizetési modellt a konfigurációs tárház** oldalon, a **konfigurációs fán**.
9. Ha elérhető **az Importálás gomb,** **válassza ki a Verziók gyorsgombot, majd válassza az Igen** lehetőséget **.**

    Ha az **Importálás** gomb nem érhető el, **akkor már importálta a fizetési modell ER konfigurációjának kiválasztott** verzióját.

10. Zárja be **a Konfigurációs tárház lapot**, majd **zárja be a Honosítási tárház lapját**.

## <a name="add-a-new-er-format-configuration"></a>Új ER-formátum hozzáadása

Adjon hozzá egy új ER-formátumot a TXT formátumú bejövő banki kivonatok elemzéséhez.

1. Válassza a **Honosítási konfigurációk lapon** a Jelentéskészítési **konfigurációk csempe** lehetőséget.
2. Válassza ki **a Fizetésmodellt** a Konfigurációk lap bal oldali konfigurációs **fájában**.
3. Válassza a **Konfiguráció létrehozása** lehetőséget. 
4. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Az **Új** mezőbe írja be a **PaymentModel modellen alapuló formátum** kifejezést.
    2. A Név **mezőben** adja **meg a Banki kivonat importálási formátumát (minta)**.
    3. Az Adatok importálását **támogató mezőben** válassza az Igen **lehetőséget**.
    4. A konfiguráció **létrehozásának befejezéséhez** válassza a Konfiguráció létrehozása lehetőséget.

## <a name="design-the-er-format-configuration--format"></a>Az ER-formátum konfigurációjának tervezése – formátum

A külső fájl txt formátumú várható szerkezetének megfelelő ER-formátum megtervezése.

1. A Hozzáadott **banki kivonat importálási formátuma (mintaformátum)** beállításához válassza a Tervező **lehetőséget**.
2. Válassza a **Gyökér hozzáadása** lehetőséget a Formátumtervező lapon a bal oldali ablak formázási szerkezetének **fájában**.
3. A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A fában válassza ki a Szövegsorozat **\\ lehetőséget** a Szekvenciaformátum-összetevő **hozzáadásához**.
    2. A Név **mezőben** adja meg a gyökér **nevét**.
    3. A Speciális karakterek **mezőben** válassza az **Új sor – Windows (CR CRE) lehetőséget**. E beállítás alapján az elemzési fájl minden sorát külön rekordnak fogja tekinteni a rendszer.
    4. Válassza ki az **OK** lehetőséget.

4. Válassza a **Hozzáadás** lehetőséget.
5. A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A fán válassza ki a Szövegsorozat **\\ lehetőséget**.
    2. A Név **mezőben** adja meg a **sorokat**.
    3. A **Multiplicitás** mezőben válassza ki az **Egy a többhöz** értéket. E beállítás alapján legalább egy sornak jelen kell lennie az elemzési fájlban.
    4. Válassza ki az **OK** lehetőséget.

6. Válassza ki a gyökérsorokat **\\** a fán, majd válassza a Szekvencia **hozzáadása lehetőséget**.
7. A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A Név **mezőben** adja meg a **mezőket**.
    2. A Többszörösség **mezőben** válassza a **Pontosan egyet**.
    3. Válassza ki az **OK** lehetőséget.

8. A fában válassza ki a gyökérsorok **\\ mezőit\\**, majd válassza a Hozzáadás **lehetőséget**.
9. A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Válassza ki a fán a Szöveg **karakterláncot\\**.
    2. A Név **mezőben** adja meg az **IBAN-t**.
    3. Válassza ki az **OK** lehetőséget.

10. Válassza a **Mentés** lehetőséget.

A konfiguráció ezzel úgy van beállítva, hogy az elemzőfájl minden sora csak az IBAN-kódot tartalmazza.

![Banki kivonat importálási formátuma (mintaformátum) a Formátumtervező lapon.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>ER-formátumkonfiguráció tervezése – hozzárendelés adatmodellhez

AZ elemzési fájlból származó adatokat használó ER-formátum-leképezés megtervezése az adatmodell kitöltéséhez.

1. A Formátumtervező **lap** munkaablakában válassza **a Leképezés formátuma a modellhez lehetőséget**.
2. A Modell adatforráshoz **hozzárendelési lapon** válassza az Új lehetőséget a **munkaablakban**.
3. A Definíció **mezőben** válassza a **BankToCustomerDebitCreditNotificationInitiation lehetőséget**.
4. A Név **mezőben** adja **meg a Leképezés az adatmodellhez való hozzárendelést**.
5. Válassza a **Mentés** lehetőséget.
6. Válassza a **Tervező** lehetőséget.
7. A modellleképezés **tervezőlapján**, az **Adatforrástípusok fában** válassza az Osztály **Dynamics 365 for Operations\\ lehetőséget**.
8. Az Adatforrások **szakaszban** válassza a Gyökér hozzáadása lehetőséget egy olyan adatforrás hozzáadásához, **amely** az IBAN-kódok érvényesség-ellenőrzésének meglévő alkalmazáslogikát hívja meg.
9. A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A Név **mezőben** adja meg az Ellenőrzőkódokat **\_**.
    2. Az Osztály **mezőben** adja meg vagy válassza ki az **ISO7064 szabványt**.
    3. Válassza ki az **OK** lehetőséget.

10. Az Adatforrástípusok **fában** kövesse az alábbi lépéseket:

    1. Bontsa ki **a formátum-adatforrást**.
    2. Gyökérformátum **kibontása\\: Sequence(Root)**.
    3. Gyökérformátum kibontása **: Sequence(Root)\\ Sorok: 1. sorozat (\\ sorok)\*.**
    4. Gyökérformátum kibontása **: Sequence(Root)\\ Sorok: 1. sorozat.\\ (Sorok)\* Mezők: 1..1. sorozat (mezők)\\.**

11. Az adatmodellfában **kövesse** az alábbi lépéseket:

    1. Bontsa ki **az** adatmodell Kifizetések mezőjét.
    2. Bontsa **ki\\ a kifizetések hitelezői számláját (CreditorAccount)**.
    3. Bontsa **ki\\ a kifizetések hitelezői számlájának (CreditorAccount)\\ azonosítóját**.
    4. Bontsa **ki\\ a kifizetések hitelezői számláját (CreditorAccount)\\ Identification\\ IBAN**.

12. A következő lépések szerint lehet a konfigurált formátum összetevőit az adatmodellmezőkhöz kötni:

    1. Gyökérformátum **\\ kiválasztása: Sequence(Root)\\ Sorok: 1. sorozat (\* sorok)**.
    2. Válassza ki a **kifizetéseket**.
    3. Válassza a **Bind** elemet. E beállítás alapján az elemzési fájl minden sorát egyetlen kifizetésnek fogja tekinteni a rendszer.
    4. Gyökérformátum **\\ kiválasztása: Sequence(Root)\\ Sorok: 1. sorozat.\* (Sorok)\\ Mezők: 1..1. sorozat (mezők)\\ IBAN: String(IBAN)**.
    5. Válassza ki **a kifizetések\\ hitelezői számláját (CreditorAccount)\\ Identification\\ IBAN**.
    6. Válassza a **Bind** elemet. E beállítás alapján az **adatmodell IBAN-mezője** ki lesz töltve az elemzési fájlban található értékkel.

    ![A formátumösszetevők kötése a Modellleképezés tervezőlapján található adatmodell-mezőkhöz.](../media/design-expressions-app-class-er-02.png)

13. Az Ellenőrzések **lapon** kövesse az alábbi lépéseket egy olyan érvényesítési szabály hozzáadásához, [amely](../general-electronic-reporting-formula-designer.md#Validation) hibaüzenetet tartalmaz az érvénytelen IBAN-kódot tartalmazó elemzőfájl bármelyik sora esetén:

    1. Válassza az **Új**, majd a Feltétel **szerkesztése lehetőséget**.
    2. A Képlettervező **lap** **adatforrásfában** bontsa ki az ISO7064 **alkalmazásosztálynak megfelelő Csekk kódok adatforrását,\_** **hogy** megtekintse az osztály elérhető metódusát.
    3. Jelölje ki **a VerifyMOD1271\_\\\_ 36 ellenőrző kódokat**.
    4. **Adatforrás hozzáadása** lehetőség választása.
    5. A Receptúra **mezőbe** írja be a következő [kifejezést](../general-electronic-reporting-formula-designer.md#Binding): **Csekkkódok.verifyMOD1271\_\_ 36(format). Root.Rows.Fields.IBAN)**.
    6. Válassza a **Mentés** gombot, majd zárja be az oldalt.
    7. Válassza az Üzenet **szerkesztése lehetőséget**.
    8. A Képlettervező **lap** Receptúra **·** **mezőjében adja meg a CONCATENATE("Érvénytelen IBAN-kód található:&nbsp;", formátumot). Root.Rows.Fields.IBAN)**.
    9. Válassza a **Mentés** gombot, majd zárja be az oldalt.

    Ezen beállítások alapján *[...](../er-formula-supported-data-types-primitive.md#boolean)* az ellenőrzési feltétel hamis értéket ad vissza érvénytelen IBAN-kódok **esetén az ISO7064\_ alkalmazásosztály meglévő verifyMOD1271** 36 **metódusának** hívásával. Ne feledje, hogy futásidőben dinamikusan definiálja az IBAN-kód értékét a hívó metódus argumentumaként, az elemző szövegfájl tartalma alapján.

    ![Ellenőrzési szabály a modellleképezés tervezőlapján.](../media/design-expressions-app-class-er-03.png)

14. Válassza a **Mentés** lehetőséget.
15. Zárja be a Modellleképezés **tervezőlapját**, majd **zárja be a Modell adatforrás-hozzárendelési lapot**.

## <a name="run-the-format-mapping"></a>Formátum-hozzárendelés futtatása

Tesztelés céljából futtassa a formátum-hozzárendelést a korábban letöltött SampleIncomingMessage.txt fájl használatával. A létrehozott kimenet a kijelölt szövegfájlból importált adatokat fogja tartalmazni, és a valódi importálás során át lesz portálva az egyéni adatmodellbe.

1. A Modell adatforráshoz **hozzárendelési lapon** válassza a Futtatás **lehetőséget**.
2. Az Elektronikus **jelentés paraméterei** oldalon válassza **a Tallózás** lehetőséget, **tallózással keresse meg a letöltött SampleIncomingMessage.txt** fájlt, és válassza ki azt.
3. Válassza ki az **OK** lehetőséget.
4. A Modell adatforráshoz **hozzárendelése** lapon egy hibaüzenet jelenik meg az érvénytelen IBAN-kódról.

    ![A formátum-hozzárendelés futtatásának eredménye a modell és az adatforrás megfeleltetési lapján.](../media/design-expressions-app-class-er-04.png)

5. Tekintse át az XML-formátumú kimenetet, amely azokat az adatokat jelöli, amelyeket a kiválasztott fájlból importált, és az adatmodellbe portolt a rendszer. Ne figyelje meg, hogy az importált szövegfájlnak csak három sorát feldolgozása történt hiba nélkül. Az online 4-es IBAN-kód érvénytelen, ezért a rendszer kihagyta.

    ![XML-kimenet.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
