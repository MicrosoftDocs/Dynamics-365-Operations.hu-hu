---
title: ER-kifejezések tervezése az alkalmazásosztályú metódusok meghívására (ER)
description: Ez az útmutató azzal kapcsolatban tartalmaz tájékoztatást, hogy hogyan használhatja fel újra a meglévő alkalmazáslogikát az elektronikus jelentéskészítési (ER-) konfigurációkban az ER-kifejezések alkalmazásosztályainak szükséges metódusainak lehívásával.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fdacd852eeed33b443a3c79b96fc4c4af04bb6b2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "357243"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>ER-kifejezések tervezése az alkalmazásosztályú metódusok meghívására (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató azzal kapcsolatban tartalmaz tájékoztatást, hogy hogyan használhatja fel újra a meglévő alkalmazáslogikát az elektronikus jelentéskészítési (ER-) konfigurációkban az ER-kifejezések alkalmazásosztályainak szükséges metódusainak lehívásával. A hívóosztályok argumentumértékeit dinamikusan lehet futásidőben definiálni: például az elemző dokumentumban lévő információk alapján az információk helyességének biztosítása érdekében. Ebben az útmutatóban létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. 

Ezek a lépések bármely adathalmazzal végrehajthatók. Le kell töltenie és helyileg mentenie kell következő fájlt: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése (ER)” eljárás lépéseit.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.   
    * Tegyük fel, hogy egy alkalmazásadat-frissítéshez tervez egy folyamatot a beérkező banki kivonatok elemzésére. Az IBAN-kódokat tartalmazó bejövő banki kivonatokat TXT-fájlként fogja megkapni. A banki kivonat importálási folyamatának részeként ellenőriznie kell az IBAN-kódok helyességét a Dynamics 365 for Finance and Operations már elérhető logikáját használva.   

## <a name="import-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció importálása
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a Microsoft lapot.  
2. Kattintson a Tárházak gombra.
3. Kattintson a Szűrők megjelenítése pontra.
4. Adjon hozzá egy Típusnév szűrőmezőt. Írja be az „erőforrások” szűrőértéket a Név mezőbe a „tartalmazza” szűrési operátor használatával, majd kattintson az Alkalmazás lehetőségre.
5. Kattintson a Megnyitás gombra.
6. A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.
    * Ha a Verziók gyorslapon az Importálás gomb még nincs engedélyezve, az azt jelenti, hogy már importálta a Fizetési modell ER-konfiguráció 1. verzióját. Az alfeladat többi műveletét kihagyhatja.   
7. Kattintson az Importálás gombra.
8. Kattintson az Igen gombra.
9. Zárja be a lapot.
10. Zárja be a lapot.

## <a name="add-a-new-er-format-configuration"></a>Új ER-formátum hozzáadása
1. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
    * Adjon hozzá egy új ER-formátumot a TXT formátumú bejövő banki kivonatok elemzéséhez.  
2. A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.
3. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédmenüt.
4. Az Új mezőbe írja be a „PaymentModel modellen alapuló formátum” kifejezést.
5. A Név mezőbe írja be a következőt: A banki kivonat importálási formátuma (minta).
    * A banki kivonat importálási formátuma (minta)  
6. A Támogatja az adatimportálást mezőben válassza az Igen lehetőséget.
7. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="design-the-er-format-configuration---format"></a>ER-formátumú konfiguráció kialakítása – formázás
1. Kattintson a Tervező pontra.
    * A tervezett formátum a külső fájl várt struktúráját jelöli TXT formátumban.  
2. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédmenü megnyitásához.
3. A fastruktúrában válassza ki ezt: „Szöveg\Sorozat”.
4. A Név mezőbe írja be a következőt: „Gyökér”.
    * Gyökér  
5. A Különleges karakterek mezőben válassza ki az „Új sor – Windows (CR LF)” lehetőséget.
    * A Különleges karakterek mezőben ki van választva az „Új sor – Windows (CR LF)” lehetőség. Ezen beállítás alapján az elemzési fájl minden sora külön nyilvántartásnak minősül.  
6. Kattintson az OK gombra.
7. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
8. A fastruktúrában válassza ki ezt: „Szöveg\Sorozat”.
9. A Név mezőbe írja be a Sorok szöveget.
    * Sorok  
10. A Multiplicitás mezőben válassza ki ezt: 'Egy a többhöz'.
    * A Multiplicitás mezőben kiválasztotta az „Egy a többhöz” lehetőséget. Ezen beállítás alapján valószínű, hogy legalább egy sor fog szerepelni az elemzési fájlban.  
11. Kattintson az OK gombra.
12. A fastruktúrában válassza ki a Gyökér\Sorok csomópontot.
13. Kattintson a Számsorozat hozzáadása lehetőségre.
14. A Név mezőbe írja be a Mezők lehetőséget.
    * Mezők  
15. A Multiplicitás mezőben válassza ki ezt: 'Pontosan egy'.
16. Kattintson az OK gombra.
17. A fastruktúrában válassza ki ezt: Gyökér\Sorok\Mezők.
18. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
19. A fában válassza ki ezt: „Text\String”.
20. A Név mezőbe írja be az „IBAN” szöveget.
    * IBAN  
21. Kattintson az OK gombra.
    * A konfiguráció szerint az elemzési fájl minden sora csak az IBAN-kódot tartalmazza.  
22. Kattintson a Mentés gombra.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>ER-formátumú konfiguráció kialakítása – adatmodell leképezése
1. Kattintson a Formátum hozzárendelése modellhez lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Definíció mezőbe írja be a „BankToCustomerDebitCreditNotificationInitiation” szöveget.
    * BankToCustomerDebitCreditNotificationInitiation  
4. ResolveChanges meghatározása.
5. A Név mezőbe írja be a következőt: „Adatmodell leképezése”.
    * Adatmodell leképezése  
6. Kattintson a Mentés gombra.
7. Kattintson a Tervező pontra.
8. A fastruktúrában válassza ki ezt: „Dynamics 365 for Operations\Osztály”.
9. Kattintson a Gyökér hozzáadása gombra.
    * Adjon hozzá egy új adatforrást a meglévő alkalmazáslogika hívására az IBAN-kódok ellenőrzése érdekében.  
10. A Név mezőbe írja be a „kódok ellenőrzése” szöveget.
    * ellenőrző_kódok  
11. Az Osztály mezőbe írja be az ISO7064 értéket.
    * ISO7064  
12. Kattintson az OK gombra.
13. A fastruktúrában bontsa ki ezt: „format”.
14. A fában bontsa ki a „format\Root: Sequence(Root)” elemet.
15. A fán válassza a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)” lehetőséget.
16. Kattintson a Kötés gombra.
17. A fán bontsa ki a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)” lehetőséget.
18. A fán bontsa ki a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)” lehetőséget.
19. A fán válassza a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)” lehetőséget.
20. A fában bontsa ki a „Payments = format.Root.Rows” elemet.
21. A fában bontsa ki a következőt: „Payments = format.Root.Rows\Creditor Account(CreditorAccount)”.
22. A fában bontsa ki a következőt: „Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification”.
23. A fában válassza a következőt: „Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification\IBAN”.
24. Kattintson a Kötés gombra.
25. Kattintson az Ellenőrzések fülre.
26. Kattintson az Új lehetőségre.
    * Adjon hozzá egy új ellenőrzési szabályt, amely hibaüzenetet jelenít meg az érvénytelen IBAN-kódot tartalmazó elemzési fájl hiba minden sorához.  
27. Kattintson a Feltétel szerkesztése elemre.
28. A fában bontsa ki a „check_codes” csomópontot.
29. A fán válassza a check_codes\verifyMOD1271_36 pontot.
30. Kattintson az Adatforrás hozzáadása pontra.
31. A Képlet mezőbe írja be a „check_codes.verifyMOD1271_36(” szöveget.
    * check_codes.verifyMOD1271_36(  
32. A fastruktúrában bontsa ki ezt: „format”.
33. A fában bontsa ki a „format\Root: Sequence(Root)” elemet.
34. A fán bontsa ki a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)” lehetőséget.
35. A fán bontsa ki a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)” lehetőséget.
36. A fán válassza a „format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)” lehetőséget.
37. Kattintson az Adatforrás hozzáadása pontra.
38. A képlet mezőbe írja be a „check_codes.verifyMOD1271_36 (formátuma. Root.Rows.Fields.IBAN)” szöveget.
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Kattintson a Mentés gombra.
40. Zárja be a lapot.
    * Az érvényességi feltétel úgy van konfigurálva, hogy minden érvénytelen IBAN-kód esetén HAMIS választ adjon az ISO7064 alkalmazásosztály „verifyMOD1271_36” meglévő módszerét előhívva. Vegye figyelembe, hogy az IBAN-kód értéke dinamikusan van megadva futásidőben az elemző TXT-fájl tartalmán alapuló hívásmódszer argumentumaként.   
41. Kattintson az Üzenet szerkesztése lehetőségre.
42. A Receptúra mezőbe írja be a következőt: CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN).
    * CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)  
43. Kattintson a Mentés gombra.
44. Zárja be a lapot.
45. Kattintson a Mentés gombra.
46. Zárja be a lapot.

## <a name="run-the-format-mapping"></a>Formátum-hozzárendelés futtatása
Tesztelési célokra hajtsa végre a letöltött SampleIncomingMessage.txt fájllal formátumleképezést. A létrehozott kimenet olyan adatokat tartalmaz, amelyek importálása a kijelölt TXT-fájlból történik, és a valós importáláskor tölti fel az egyéni adatmodellt.   
1. Kattintson a Futtatás elemre.
    * Kattintson a Böngészés lehetőségre, és a navigáljon a korábban letöltött SampleIncomingMessage.txt fájlhoz.  
2. Kattintson az OK gombra.
    * Tekintse át az XML-formátumú kimenetet, amely azokat az adatokat jelöli, amelyeket a kiválasztott fájlból importált, és az adatmodellbe portolt a rendszer. Vegye figyelembe, hogy az importált TXT-fájlnak csak 3 sora került feldolgozásra. A rendszer kihagyta a 4. sorban található érvénytelen IBAN-kódot, és hibaüzenetet hagyott az információs naplóban.  

