---
title: Aszinkron rendelésszinkronizálási problémák
description: Ez a témakör az aszinkron Microsoft Dynamics 365 Commerce rendelés-létrehozási hibák gyakori okait írja le, és hibaelhárítási lépésekkel segít a rendszer felhasználóinak és partnerének annak érdekében, hogy jobban megértsük, mi történt.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815756"
---
# <a name="asynchronous-order-synchronization-issues"></a>Aszinkron rendelésszinkronizálási problémák

[!include [banner](../../includes/banner.md)]

Ez a témakör az aszinkron Microsoft Dynamics 365 Commerce rendelés-létrehozási hibák gyakori okait írja le, és hibaelhárítási lépésekkel segít a rendszer felhasználóinak és partnerének annak érdekében, hogy jobban megértsük, mi történt.

## <a name="symptom"></a>Tünet

Az e-kereskedelemből Dynamics 365 Commerce vagy pénztárból létrehozott aszinkron rendelések nem jelennek meg a Commerce Headquarters rendszerében.

## <a name="troubleshooting"></a>Hibaelhárítás

A rendelés létrehozása különböző okok miatt sikertelen lehet a központban attól függően, hogy a rendelés-létrehozási folyamat a folyamat során milyen fokozatban sikertelenül működik. Az alábbi hibaelhárítási lépések a lehetséges gyökérokokokat követik végig.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Annak ellenőrzése, hogy az aszinkron rendeléshez kapcsolódó tranzakció elérte-e a központot

A központi e-commerce rendelések **esetén menjen a Retail and Commerce \> Lekérdezések \> és jelentések online áruházi tranzakcióihoz**. Ha van visszaigazolási száma a rendeléshez, **a visszaigazolási szám megadásával szűrje a tranzakciókat a Csatornahivatkozás azonosítója mezőben** . Ha nincs meg a visszaigazolási szám, a vevő számlaszámának megadásával szűrje a tranzakciókat.

POS-rendelések esetén nyissa meg az **Üzlet** tranzakcióit, és szűrje a rekordokat a nyugtaszám vagy a vevő számlaszáma szerint. Ha a tranzakció nem található, futtassa **a P-0001 csatornatranzakciós** feladatot, amely a csatornákból a központba szinkronizálja a tranzakciókat. Ha a **P-0001** feladat sikertelen, nyisson meg egy támogató jegyet a sikertelen feladathoz. Ha sikerült **a P-0001** feladat, de a tranzakciók továbbra sem jelennek meg a központban, nyisson meg egy támogatási jegyet, amely tartalmazza a megfelelő adatokat.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>A szinkronizálás állapotának ellenőrzése, ha a tranzakció jelen van a központban, de nincs értékesítési rendeléshez kapcsolva.

Ha a tranzakció jelen van a központban, de az értékesítési rendelés még nincs létrehozva, **nyissa meg az online** áruház tranzakciós lapját, **és válassza a Szinkronizálás állapot** gyorslapját. Ha a **Rendelések szinkronizálása** feladat szinkronizálni próbálta ezt a tranzakciót, **a** Függő rendelés állapota mezőnek Sikeres vagy **Sikertelen** állapotot kell **mutatnia**. Ha az állapot **Sikeres**, az értékesítési rendelés mezőnek jelen kell lennie a tranzakcióban. Ha az állapot **sikertelen**, **·**  **a** hiba részleteit a Szinkronizálási állapot gyorsjelentés Rendelési hiba részletei mezőjében lehet megtekinteni. Ha egyik állapot sem látható, nem történt kísérlet a tranzakció feldolgozására. Ebben az esetben a szinkronizálási **feladat** futtatásához a lap tetején a Rendelés szinkronizálása lehetőséget választhatja.

Győződjön meg arról, hogy **a** Rendelések szinkronizálása feladat rendszeres időközönkénti futásra van ütemezve, hogy az aszinkron tranzakciók rendelésként a központból rendelésként is létre tudjanak hozatni.

A következő szakaszok néhány gyakori hibával és a javasolt javításokkal kapcsolatban tartalmaznak tájékoztatást.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>A Rendelési hiba részletei mezőben a következő hibaüzenet látható: "Számsorozat túllépve"

A számsorozatok az értékesítési rendelések központi létrehozásához használhatók. Ha egy számsorozathoz engedélyezett összes szám csak egyetlen szám, akkor a rendszer ezt a hibaüzenetet generálja. Az értékesítési rendelések **\>  \>** létrehozásához használt számsorozat a Kinnlevőségek paramétereinél található meg. A hiba kijavíthatja, kijavíthatja a meglévő számsorozatot, vagy lecserélheti egy új számsorozatra.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>A Rendelési hiba részletei mezőben a következő hibaüzenet látható: "A hitelkártyás tranzakciók feldolgozásához szükség van egy alapértelmezett fizetési szolgáltatásra"

A hiba kijavításánál győződjön meg arról, hogy meg van adva alapértelmezett kifizetés a központban. Ha nincs megadva alapértelmezett kifizetés, meg kell határoznia egyet. Menjen a Kinnlevőségek – Fizetés beállítása fizetési szolgáltatásokhoz, és győződjön meg arról, **\>  \>** hogy az új hitelkártyák alapértelmezett feldolgozója beállítás Igen beállítású egy fizetési szolgáltatásnál. **·**  **·** 
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>A Rendelési hiba részletei mezőben egy számlastruktúra hibaüzenete látható.

A számlastruktúra hibaüzenetének szövege a következő példákban is látható lehet. A hibák ugyanakkor közös gyökérrel kapcsolatosak, ami a számlastruktúra-konfigurációval kapcsolatos.

- "A vállalati rendelésben szereplő bizonylatszámhoz 0009656328 ARP-000959899 1,00 bizonylatszámú napló ARP-000959899 túlfizetésként vagy alulfizetésként lesz feladva."
- "A(z) 0009656328 bizonylatszámú napló ARP-000959899 feladási eredményei ARP-000959901 számlastruktúra esetében a 618160 kombináció esetében nem érvényes a főkönyvi főkönyvi főszámla megosztott számlája esetében."
- "A napló kötegszámának feladási eredményei 0009656328 bizonylatszámhoz ARP-000959899, ARP-000959901 a vállalati számlákból származó adatokból."
- "A napló kötegszámának feladási 0009656328 bizonylatszámaARP-000959899 a feladást visszavonták."
    
A hibák kijavítása érdekében ellenőrizze a számlastruktúrák pontosságát. A további tudnivalókat lásd: Számlastruktúrák [konfigurálása](/dynamics365/finance/general-ledger/configure-account-structures).
    
A hiba kijavítás után jelölje ki a sikertelen tranzakciót, **majd** a szinkronizálási feladat futtatásához válassza a Szinkronizálás rendelés lehetőséget az oldal tetején.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Egyéb típusú hibák, amelyek a tranzakcióadatok rögzített típusát követelhetik meg

Ha ki szeretné javítani az egyéb olyan hibákat, amelyek a tranzakcióadatok javítását kérhetik, a "tranzakciók szerkesztése és naplózása" lehetőség használható. A további tudnivalókat lásd [: Tranzakciók szerkesztése és naplózása](../edit-order-trans.md).
