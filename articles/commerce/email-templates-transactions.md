---
title: E-mail-sablonok létrehozása a tranzakciók eseményeihez
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni, feltölteni és konfigurálni a Microsoft Dynamics 365 Commerce tranzakciós eseményeihez tartozó e-mail-sablonokat.
author: bicyclingfool
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ea484bfc1e9b293c53d7293c50630c4955000131
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412774"
---
# <a name="create-email-templates-for-transactional-events"></a>E-mail-sablonok létrehozása a tranzakciók eseményeihez

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet létrehozni, feltölteni és konfigurálni a Microsoft Dynamics 365 Commerce tranzakciós eseményeihez tartozó e-mail-sablonokat.

## <a name="overview"></a>Áttekintés

A(z) Dynamics 365 Commerce olyan e-mailek küldését teszi lehetővé, amelyek figyelmeztetik a vevőket a tranzakciós eseményekről (például egy megrendelés leadásáról, ha egy rendelés felvehető, vagy a rendelést leszállították). Ez a témakör a tranzakciós e-mailek küldésére használt e-mail-sablonok létrehozásához, feltöltéséhez és beállításához szükséges lépéseket mutatja be.

## <a name="create-an-email-template"></a>E-mail sablon létrehozása

Mielőtt egy konkrét tranzakciós eseményt hozzárendel egy e-mail-sablonhoz, létre kell hoznia a sablont.

E-mail-sablon létrehozásához kövesse az alábbi lépéseket.

1. A Commerce-központban válassza a **Szervezet e-mail sablonjai** elemet , amely a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Szervezeti e-mail sablonok** vagy **Szervezeti adminisztráció \> Beállítások \> Szervezeti e-mail-sablonok** helyen található.
1. Válassza az **Új** lehetőséget.
1. Az **Általános** lehetőség alatt állítsa be a következő mezőket:

    - **E-mail-azonosító** Az e-mail-azonosító egy sablon egyedi azonosítója, és az az érték, amely akkor jelenik meg, amikor kijelöl egy sablont az eseményhez való hozzárendeléshez.
    - **E-mail leírása** – Ezt a nem kötelező mezőt a sablon leírásának megadására használhatja. A megadott érték csak a Kereskedelmi központban jelenik meg.
    - **Feladó neve** – Az Ön által megadott név jelenik meg a legtöbb levelezőkliens „kezdő” mezőjében.
    - **Feladó e-mail-címe** – Adja meg az e-mail-címet, amelyet a sablon használatával küldött e-mailekhez kell használni.
    - **Alapértelmezett nyelvkód** – Ez a mező adja meg az alapértelmezettként elküldött e-mailek lokalizált változatát, ha a sablont hivatkozó csatorna nem szolgáltat nyelvet.

1. Az **E-mail-üzenet tartalma** alatt válassza az **Új** lehetőséget.
1. A **Nyelv** mezőbe írja be az e-mail-sablon nyelvét. Később több nyelvet és lokalizát sablont is hozzáadhat.
1. A **Tárgy** mezőbe írja be az e-mail tárgyát, amelynek meg kell jelennie az e-mail tárgya mezőjében.
1. Az e-mail-sablon feltöltéséhez válassza a **Szerkesztés** elemet.

## <a name="create-an-email-message-body-by-using-html"></a>E-mail-üzenet törzsének létrehozása HTML használatával

Az e-mail-üzenet törzse HTML-ben szerkesztett. Bármilyen elrendezést, stílust és védjegyezést használhat, amit a HTML és a szövegközti stíluslapok (CSS) lehetővé tesznek. A képek akkor is használhatók, ha egy nyilvánosan elérhető webes végponton tárolja azokat. Kép hozzáadásához írja be a kép URL-címét az **src**-attribútumba, ami a HTML **&lt;img&gt;**-címkéjébe tartozik.

> [!NOTE]
> Az e-mail kliensek olyan elrendezési és stílusbeli korlátozásokat írnak elő, amelyekhez HTML-kiigazítás szükséges, és CSS amit az üzenet törzséhez használhat. Azt ajánljuk, hogy ismerkedjen meg a legjobb megoldásokkal, amelyek a legnépszerűbb levelezőprogramok által támogatott HTML-létrehozási eljárásokat jelentik.

## <a name="add-placeholders-to-the-email-message-body"></a>Helyőrzők hozzáadása az e-mail-üzenet törzséhez

Az e-mailek tartalmazhatnak olyan helyőrzőket, amelyeket a rendszer az e-mail generálása alkalmával a vevőre jellemző és a tranzakcióra jellemző értékekkel cserél le. A helyőrzők mindig százalékjelekkel (%) vannak körülvéve, és közvetlenül a HTML-dokumentumba kerülnek beszúrásra.

Íme, egy példa.

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Rendelés helyőrzői (értékesítési rendelés szintje)

A következő helyőrzők az értékesítési rendelés szintjén megadott adatokat kérdezik le és jelenítik meg (szemben az értékesítési sor szintjével).

| Helyőrző neve    | Helyőrző értéke                                                |
|---------------------|------------------------------------------------------------------|
| customername        | A rendelést küldő vevő neve.                   |
| salesId             | A rendelés értékesítési azonosítója.                                       |
| deliveryaddress     | A kiszállított rendelések szállítási címe.                         |
| customeraddress     | A vevő címe.                                     |
| deliverydate        | A kiszállítás dátuma.                                               |
| shipdate            | A szállítás dátuma.                                                   |
| modeofdelivery      | A rendelés szállítási módja.                                  |
| KÖLTSÉGEK             | A rendelés teljes költsége.                                 |
| adó                 | A rendelést terhelő teljes adó.                                     |
| összesen               | A rendelés teljes összege.                                  |
| ordernetamount      | A rendelés teljes összege, mínusz a teljes adó.             |
| engedmény            | A rendelés teljes engedménye.                                |
| StoreName           | Az üzlet neve, ahonnan a rendelést a vevő küldte.                |
| storeaddress        | A rendelést küldő üzlet címe.                  |
| storeopenfrom       | A rendelést küldő üzlet nyitvatartási ideje.             |
| storeopento         | A rendelést küldő üzlet zárási ideje.             |
| pickupstorename     | Az üzlet neve, ahol a rendelést felveszik.         |
| pickupstoreaddress  | Az üzlet címe, ahol a rendelést felveszik.      |
| pickupopenstorefrom | Az üzlet nyitvatartási ideje, ahol a rendelést felveszik. |
| pickupopenstoreto   | Az üzlet zárási ideje, ahol a rendelést felveszik. |

### <a name="order-line-placeholders-sales-line-level"></a>Rendelési sor helyőrzői (értékesítési sor szintje)

A következő helyőrzők az értékesítési rendelés egyes termékeinek (sorainak) adatait kérdezik le és jelenítik meg.

| Helyőrző neve               | Helyőrző értéke |
|--------------------------------|-------------------|
| productid                      | A sor termékazonosítója. |
| lineproductname                | A termék neve. |
| lineproductdescription         | A termék leírása. |
| linequantity                   | A sorhoz rendelt egységek száma, valamint a mértékegység (például **db** vagy **pár**). |
| lineunit                       | A sor mértékegysége. |
| linequantity_withoutunit       | A sorhoz rendelt egységek száma a mértékegység nélkül. |
| linequantitypicked             | A **PickOrder** esemény használatakor a kiválasztott egységek száma. Ellenkező esetben **0** (nulla). |
| linequantitypicked_withoutunit | A **PickOrder** esemény használatakor a kiválasztott egységek száma a mértékegység nélkül. Ellenkező esetben **0** (nulla). |
| linequantitypacked             | Amikor a **PackOrder** és a **Rendelés készen áll a felvételre** eseményeket használja, a csomagolt egységek száma. Ellenkező esetben **0** (nulla). |
| linequantitypacked_withoutuom  | Amikor a **PackOrder** és a **Rendelés készen áll a felvételre** eseményeket használja, a csomagolt egységek száma a mértékegység nélkül. Ellenkező esetben **0** (nulla). |
| linequantityshipped            | Mindig **0** kivéve bizonyos események alkalmazásakor a következő sorban leírtak szerint. |
| linequantityshipped_withoutuom | A **ShipOrder** esemény használatakor a kiválasztott egységek száma a mértékegység nélkül. Ellenkező esetben **0** (nulla). |
| lineprice                      | Az adott egység ára. |
| linenetamount                  | A sor ára az egységek és az engedmények számának alkalmazása után. |
| linediscount                   | Az adott egységhez tartozó engedmény. |
| lineshipdate                   | A sor szállítási dátuma. |
| linedeliverydate               | A sor kiszállítási dátuma. |
| linedeliverymode               | A sor kiszállítási módja. |
| linedeliveryaddress            | A sor kiszállítási címe. |
| giftcardnumber                 | Az ajándékutalvány száma az ajándékutalvány-típus termékei esetében. |
| giftcardbalance                | Az ajándékutalvány egyenlege az ajándékutalvány-típus termékei esetében. |
| giftcardmessage                | Az ajándékutalvány üzenete az ajándékutalvány-típus termékei esetében. |
| giftcardpin                    | Az ajándékutalvány személyes azonosító száma (PIN) az ajándékutalvány-típus termékei esetében. (Ez a helyőrző a külső ajándékutalvány-kártyákra vonatkozik.) |
| giftcardexpiration             | Az ajándékutalvány lejárati dátuma az ajándékutalvány-típus termékei esetében. (Ez a helyőrző a külső ajándékutalvány-kártyákra vonatkozik.) |
| giftcardrecipientname          | Az ajándékutalvány címzettjének neve az ajándékutalvány-típus termékei esetében. |
| giftcardbuyername              | Az ajándékutalvány vásárlójának neve az ajándékutalvány-típus termékei esetében. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Rendelési sor helyőrzőinek formátuma az e-mail üzenet törzsében

Amikor az e-mail-üzenet törzsében létrehozza az egyes rendeléssorok HTML-jét, vegye körbe az ismétlődő HTML-blokkokat és a sorra vonatkozó helyőrzőket a HTML-megjegyzések címkéibe ágyazott különböző helyőrzőkkel.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

Íme, egy példa.

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Sablon létrehozása e-mailben kapott nyugták számára

A kiskereskedelmi pénztárnál (POS) vásárló vevőknek e-mailben elküldhető a nyugtájuk. Az e-mailben küldendő nyugta sablonjának létrehozási lépései általában megegyeznek a más tranzakciós események sablonjainak létrehozási lépéseivel. A következő változtatások azonban kötelezőek:

- Az e-mail-sablon e-mail-azonosítójának **emailRecpt** értéknek kell lennie.
- A nyugta szövegét a **%message%** helyőrzővel kell beilleszteni az e-mailbe. Ha biztosítani szeretné, hogy a nyugta törzse helyesen legyen megjelenítve, akkor a **%message%** helyőrzőt vegye körbe HTML **&lt;pre&gt;** és **&lt;/pre&gt;** címkékkel.
- Az e-mail fejlécének és élőlábának HTML-jében lévő sortörések HTML **&lt;br /&gt;** címkékre alakulnak, így a nyugta törzse helyesen jelenik meg. Ha meg szeretné szüntetni a nyugták e-mailjeiben a nem kívánt függőleges helyet, távolítsa el a sortöréseket a HTML-fájl bármely olyan helyéről, ahol nem szükséges a függőleges hely.

Az e-mail-nyugták konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail-nyugták beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts).

## <a name="upload-the-email-html"></a>Az e-mail-HTML feltöltése

Miután létrehozta és tesztelte az üzenet törzsének HTML-jét, fel kell töltenie a Kereskedelmi központba. Jelenleg az e-mail-HTML nem exportálható. Ennek megfelelően fenn kell tartania a HTML-en kívüli Kereskedelmi központ főpéldányát.

Új vagy szerkesztett e-mail-sablon HTML-jének feltöltéséhez hajtsa végre az alábbi lépéseket.

1. A Kereskedelmi központban nyissa meg a **Kiskereskedelem és kereskedelem \> Központ beállítási \> Szervezeti e-mail-sablonok** lehetőséget.
1. Válassza ki annak a nyelvnek a sorát, amelyhez HTML-t szeretne hozzáadni vagy helyettesíteni azt. Vagy az **Új** opció kiválasztásával egy sort hozhat létre az új nyelvhez.
1. Válassza ki a **Szerkesztés** opciót.
1. A megjelenő párbeszédpanelen jelölje be a **Tallózás** lehetőséget. Tallózással keresse meg a feltölteni kívánt HTML-dokumentumot, jelölje ki, majd kattintson a **Megnyitás** gombra.
1. Válassza a **Feltöltés** elemet.
1. Miután az e-mail-HTML megjelenik az előnézeti ablakban, kattintson az **OK** gombra.
1. Győződjön meg arról, hogy a **Van törzse** jelölőnégyzet a sor esetében be van jelölve.

Ha már konfigurálta a Kereskedelmi központot e-mailek küldésére, akkor az új vagy frissített e-mailt elküldi az összes olyan vevőnek, aki olyan tranzakciót hajt végre, amely a sablonhoz hozzárendelt eseményt használ.

A(z) Dynamics 365 Commerce e-mailjeinek konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>További erőforrások 

[E-mail-értesítési profil beállítása](email-notification-profiles.md)

[E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[E-mail nyugták beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[E-mailes nyugták küldése a Modern POS szolgáltatásból ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]