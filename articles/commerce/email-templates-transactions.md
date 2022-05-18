---
title: E-mail-sablonok létrehozása a tranzakciók eseményeihez
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni, feltölteni és konfigurálni a Microsoft Dynamics 365 Commerce tranzakciós eseményeihez tartozó e-mail-sablonokat.
author: bicyclingfool
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 08e247bac577dc0bb8a4635d61f0082793380da9
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722519"
---
# <a name="create-email-templates-for-transactional-events"></a>E-mail-sablonok létrehozása tranzakciós eseményekhez

[!include [banner](includes/banner.md)]


Ez a témakör azt mutatja be, hogyan lehet létrehozni, feltölteni és konfigurálni a Microsoft Dynamics 365 Commerce tranzakciós eseményeihez tartozó e-mail-sablonokat.

A Dynamics 365 Commerce gyári megoldást kínál olyan e-mailek küldésére, amelyek figyelmeztetik az ügyfeleket a tranzakciós eseményekre. E-maileket lehet például küldeni a rendelés leadásakor, ha a rendelés készen áll a felvételre, vagy már leszállították. Ez a témakör a tranzakciós e-mailek küldésére használt e-mail-sablonok létrehozásához, feltöltéséhez és beállításához szükséges lépéseket mutatja be.

## <a name="notification-types"></a>Értesítési típusok

Az értesítések konfigurálhatók arra, hogy értesítsék a vevőket e-mailben, ha a rendelés és a vevő életciklusának részeként bizonyos események történnek. Az értesítések konfigurálásához egy Commerce e-mail értesítési profil létrehozásával egy e-mail sablont kell leképeznie az értesítési típusra. További információt az e-mailes értesítési profilok beállításáról az [E-mailes értékesítési profil beállítása](email-notification-profiles.md) című témakörben talál.

A Dynamics 365 Commerce következő értesítéstípusokat támogatja.

### <a name="order-created"></a>Rendelés létrehozva

A *rendelés létrehozva* értesítési típus akkor jelenik meg, amikor a Commerce Headquarters alkalmazásban új értékesítési rendelést hoznak létre.

> [!NOTE]
> A rendelés létrehozott értesítési típusa indul el Készpénzzel fizetett, azonnal átvett tranzakciókra, amelyek a pénztári terminálon következnek be. Ebben az esetben egy e-mailben küldött és/vagy nyomtatott nyugta jön létre helyette. A további tudnivalókat lásd: [E-mail nyugták küldése a Modern pénztárból (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Rendelés visszaigazolva

A *rendelés megerősítve* értesítési típus akkor jelenik meg, amikor a Commerce központban rendelés-visszaigazolási dokumentumot hoznak létre egy értékesítési rendeléshez.

### <a name="picking-completed"></a>Kitárolás befejezve

A *kitárolás befejezve* értesítési típus akkor jelenik meg, ha egy rendelés kitárolási listája készként van megjelölve a Commerce központban.

> [!NOTE]
> A kitárolás befejezve értesítési típus nem aktiválódik, ha egy cikk kitárolásként van megjelölve egy POS terminálon.

### <a name="packing-completed"></a>Csomagolás befejezve

A *csomagolás befejezve* értesítési típus akkor jelenik meg, ha egy rendeléshez szállítólevél dokumentum jön létre Commerce központban egy POS terminálnál.

A csomagolás befejeződött értesítéstípus a következő további e-mail helyőrzőket támogatja, hogy megkönnyítse a "rendelés felvételre kész" és rendeléskeresés funkciókat a tranzakciós e-mailekből.

| Helyőrző neve    | Alkalmazás célja |
| ------------------- | ------- |
| `pickupstorename`     | Annak az üzletnek a neve, ahol a rendelés felvételre elérhető. |
| `pickupstoreaddress`  | Annak az üzletnek a címe, ahol a rendelés felvételre elérhető. |
| `pickupstoreopenfrom` | A felvételi üzlet nyitási ideje. |
| `pickupstoreopento` | A felvételi üzlet zárásának időpontja. |
| `pickupchannelid`     | A felvételi üzlet üzletcsatorna-azonosítója. |
| `packingslipid`      | A rendelés csomagjegyzékének azonosítója, amely fel lesz véve. |
| `confirmationid`      | A rendelés megerősítésének azonosítója, amely fel lesz véve. (Ezt az azonosítót nevezik csatornahivatkozás-azonosítónak.) |

A vevői bejelentkezési és rendeléskeresési szolgáltatásokkal kapcsolatos további tudnivalókat lásd: [A földrajzi hely észlelés és az átirányítás beállítása](geo-detection-redirection.md) és [Rendelés keresésének engedélyezése vendég pénztárak részére](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Átvételre kész rendelés

A *rendelés felvételre kész* eseménytípus akkor indul, amikor egy rendelés csomagoltként van megjelölve, és a szállítás módja **Vevői felvétel** értékre van állítva egy vagy több rendelési sorban.

> [!NOTE]
> A felvételre kész rendelés értesítési típus avultatva lett a csomagolás befejezve értesítéstípus következtében. Ezt az értesítési típust a szállítási mód szabja testre.

### <a name="order-shipped"></a>Rendelés leszállítva

A *rendelés leszállítva* értesítési típusa akkor indul, ha a rendeléshez nem üzletben történő átvétel van számlázva.

> [!NOTE]
> A rendelés leszállítva értesítési típus avultatva lett a rendelés szállítva értesítéstípus következtében. Ezt az értesítési típust a szállítási mód szabja testre.

### <a name="order-invoiced"></a>Rendelés számlázva

A *rendelés számlázva* értesítési típus akkor jelenik meg, amikor egy rendelést számláznak a pénztárban vagy a Commerce központban.

### <a name="issue-gift-card"></a>Ajándékutalvány kibocsátása

Az *Ajándékutalvány kibocsátása* értesítéstípus akkor jelenik meg, amikor egy ajándékutalvány típusú terméket tartalmazó értékesítési rendelést számláznak.

> [!NOTE]
> A rendszer elküldi az ajándékutalvány kibocsátása e-mailt az ajándékutalvány címzettjének. Az ajándékutalvány címzettje a Commerce központ alkalmazásában van megadva, a **Csomagolás** lapon a **Sor részletei** alatt. Manuálisan vagy programozva is meg lehet adni.

Az ajándékutalvány kibocsátása értesítési típus a következő további helyőrzőket támogatja.

| Helyőrző neve      | Alkalmazás célja |
| --------------------- | ------- |
| `giftcardnumber`        | Az ajándékutalvány száma az ajándékutalvány-típus termékei esetében. |
| `availablebalance` | Az ajándékutalvány fennmaradó egyenlege |
| `giftcardmessage`       | Az ajándékutalvány üzenete az ajándékutalvány-típus termékei esetében. |
| `giftcardpin`         | Az ajándékutalvány személyes azonosító száma (PIN) az ajándékutalvány-típus termékei esetében. (Ez a helyőrző a külső ajándékutalvány-kártyákra vonatkozik.) |
| `giftcardexpiration`    | Az ajándékutalvány lejárati dátuma az ajándékutalvány-típus termékei esetében. (Ez a helyőrző a külső ajándékutalvány-kártyákra vonatkozik.) |
| `giftcardrecipientname` | Az ajándékutalvány címzettjének neve az ajándékutalvány-típus termékei esetében. |
| `giftcardbuyername`     | Az ajándékutalvány vásárlójának neve az ajándékutalvány-típus termékei esetében. |

Az ajándékutalványokkal kapcsolatos további tudnivalókat lásd: [E-kereskedelmi digitális ajándékkártyák](digital-gift-cards.md) és [Külső ajándékutalványok támogatása](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Rendelés érvénytelenítése

A *rendelés törölve* értesítési típus akkor jelenik meg, amikor egy rendelést törölnek a pénztárban vagy a Commerce központban.

### <a name="customer-created"></a>Vevő létrehozva

Az *ügyfél létrehozva* értesítési típus akkor jelenik meg, amikor a Commerce központ alkalmazásban új ügyfélentitást hoznak létre.

### <a name="b2b-prospect-approved"></a>B2B potenciális vevő jóváhagyva

A *B2B potenciális vevő jóváhagyva* értesítési típus akkor jelenik meg, ha egy potenciális vevő onboarding kérését jóváhagyják a Commerce központban. A B2B potenciális vevők jóváhagyásáról vagy elutasításáról a [Rendszergazda felhasználó beállítása új üzleti partnerhez](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner) rész tartalmaz további tájékoztatást. 

A B2B potenciális vevő jóváhagyva értesítési típus a következő további helyőrzőket támogatja.

| Helyőrző neve | Alkalmazás célja                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | A B2B potenciális vevőnek az alkalmazásban megadott keresztneve. |
| `lastname`         | A B2B potenciális vevőnek az alkalmazásban megadott vezetékneve. |
| `company`          | A jelentkező vállalatának az alkalmazásban megadott neve. |
| `email`            | A potenciális vevőnek az alkalmazásban megadott e-mail-címe.   |
| `zipcode`          | A potenciális vevő elsődleges címének postai irányítószáma. |
| `comments`         | A potenciális vevő által az alkalmazásban megadott megjegyzés. |
| `storename`        | Annak a csatornának a neve, amelyben a potenciális vevő létrejött. |
| `storeurl`         | Alapértelmezés szerint üres. A helyőrző csak akkor használható, ha egyéni bővítményt hoznak létre. |

### <a name="b2b-prospect-rejected"></a>B2B potenciális vevő elutasítva

A *B2B potenciális vevő elutasítva* értesítési típus akkor jelenik meg, ha egy potenciális vevő onboarding kérését elutasítják a Commerce központban. A B2B potenciális vevők jóváhagyásáról vagy elutasításáról a [Rendszergazda felhasználó beállítása új üzleti partnerhez](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner) rész tartalmaz további tájékoztatást. 

A B2B potenciális vevő elutasítva értesítési típus a következő további helyőrzőket támogatja.

| Helyőrző neve | Alkalmazás célja                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | A B2B potenciális vevőnek az alkalmazásban megadott keresztneve. |
| `lastname`         | A B2B potenciális vevőnek az alkalmazásban megadott vezetékneve. |
| `company`          | A jelentkező vállalatának az alkalmazásban megadott neve. |

## <a name="create-an-email-template"></a>E-mail sablon létrehozása

Mielőtt egy konkrét tranzakciós eseményt hozzárendel egy e-mail-sablonhoz, létre kell hoznia a sablont.

E-mail-sablon létrehozásához kövesse az alábbi lépéseket.

1. A Commerce-központban válassza a Szervezet e-mail sablonjai elemet , amely a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Szervezeti e-mail-sablonok** vagy **Szervezeti adminisztráció \> Beállítások \> Szervezeti e-mail-sablonok** helyen található.
1. Válassza az **Új** lehetőséget.
1. Az **Általános** lehetőség alatt állítsa be a következő mezőket:

    - **E-mail azonosító** – Az e-mail azonosító a sablon egyedi azonosítója. Ez az az érték, amely akkor jelenik meg, amikor kiválaszt egy eseményhez leképezni kívánt sablont.
    - **E-mail leírása** – Ezt a nem kötelező mezőt a sablon leírásának megadására használhatja. A megadott érték csak a Kereskedelmi központban jelenik meg.
    - **Feladó neve** – Az Ön által megadott név jelenik meg a legtöbb levelezőkliens „kezdő” mezőjében.
    - **Feladó e-mail-címe** – Adja meg az e-mail-címet, amelyet a sablon használatával küldött e-mailekhez kell használni.
    - **Alapértelmezett nyelvkód** – Ez a mező adja meg az alapértelmezettként elküldött e-mailek lokalizált változatát, ha a sablont hivatkozó csatorna nem határoz meg nyelvet.

1. Az **E-mail-üzenet tartalma** alatt válassza az **Új** lehetőséget.
1. A **Nyelv** mezőbe írja be az e-mail-sablon nyelvét. Később több nyelvet és lokalizát sablont is hozzáadhat.
1. A **Tárgy** mezőbe írja be az e-mail tárgyát, amelynek meg kell jelennie az e-mail tárgya mezőjében.
1. Az e-mail-sablon feltöltéséhez válassza a **Szerkesztés** elemet.

## <a name="create-an-email-message-body-by-using-html"></a>E-mail-üzenet törzsének létrehozása HTML használatával

Az e-mail-üzenet törzse HTML-ben szerkesztett. Bármilyen elrendezést, stílust és védjegyezést használhat, amit a HTML és a szövegközti stíluslapok (CSS) lehetővé tesznek. A képek akkor is használhatók, ha egy nyilvánosan elérhető webes végponton tárolja azokat. Kép hozzáadásához írja be a kép URL-címét az **src**-attribútumba, ami a HTML **&lt;img&gt;**-címkéjébe tartozik.

> [!NOTE]
> Az e-mail kliensek olyan elrendezési és stílusbeli korlátozásokat írnak elő, amelyekhez HTML-kiigazítás szükséges, és CSS amit az üzenet törzséhez használhat. Javasoljuk, hogy ismerkedjen meg a HTML létrehozásának legjobb gyakorlataival, amelyeket a legnépszerűbb e-mail kliensek támogatnak.

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

| Helyőrző neve     | Alkalmazás célja                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | A rendelést küldő vevő neve.               |
| `customeraddress`      | A vevő címe.                                 |
| `customeremailaddress` | A vevő által a pénztárnál megadott e-mail-cím.     |
| `salesid`              | A rendelés értékesítési azonosítója.                                   |
| `orderconfirmationid`  | A megrendelés létrehozásakor generált keresztcsatornás azonosító.   |
| `channelid`            | Annak a kiskereskedelmi vagy online csatornának az azonosítója, amelyen keresztül a megrendelés leadásra került. |
| `deliveryname`         | A szállítási címhez megadott név.         |
| `deliveryaddress`      | A kiszállított rendelések szállítási címe.                     |
| `deliverydate`         | A kiszállítás dátuma.                                           |
| `shipdate`             | A szállítás dátuma.                                               |
| `modeofdelivery`       | A rendelés szállítási módja.                              |
| `ordernetamount`       | A rendelés teljes összege, mínusz a teljes adó.         |
| `discount`            | A rendelés teljes engedménye.                            |
| `charges`              | A rendelés teljes költsége.                             |
| `tax`                  | A rendelést terhelő teljes adó.                                 |
| `total`                | A rendelés teljes összege.                              |
| `storename`            | Az üzlet neve, ahonnan a rendelést a vevő küldte.            |
| `storeaddress`         | A rendelést küldő üzlet címe.              |
| `storeopenfrom`        | A rendelést küldő üzlet nyitvatartási ideje.         |
| `storeopento`          | A rendelést küldő üzlet zárási ideje.         |
| `pickupstorename`      | Az üzlet neve, ahol a rendelést felveszik.\*   |
| `pickupstoreaddress`   | Az üzlet címe, ahol a rendelést felveszik.\* |
| `pickupopenstorefrom`  | Az üzlet nyitvatartási ideje, ahol a rendelést felveszik.\* |
| `pickupopenstoreto`    | Az üzlet zárási ideje, ahol a rendelést felveszik.\* |
| `pickupchannelid`     | A felvételi típusú szállítási módhoz megadott áruház csatornaazonosítója.\* |
| `packingslipid`        | Annak a szállítólevélnek az azonosítója, amelyet a rendelés sorainak csomagolásakor generáltak.\* |

\* Ezek a helyőrző elemek csak akkor adnak vissza adatokat, ha a **Rendelés átvételre kész** értesítés típushoz használják őket. 

### <a name="order-line-placeholders-sales-line-level"></a>Rendelési sor helyőrzői (értékesítési sor szintje)

A következő helyőrzők az értékesítési rendelés egyes termékeinek (sorainak) adatait kérdezik le és jelenítik meg.

| Helyőrző neve               | Alkalmazás célja |
|--------------------------------|-------------------|
| `productid`                      | <p>A termék azonosítója. Ez az azonosító figyelembe veszi a változatokat.</p><p><strong>Megjegyzés</strong>: Ezt a helyőrzőt már nem használják a `lineproductrecid` helyett.</p> |
| `lineproductrecid`               | A termék azonosítója. Ez az azonosító figyelembe veszi a változatokat. Egyedileg azonosít egy tételt a változat szintjén. |
| `lineitemid`                     | A termék termékszintű azonosítója. (Ez az azonosító nem veszi figyelembe a változatokat.) |
| `lineproductvariantid`           | A termékváltozat azonosítója. |
| `lineproductname`                | A termék neve. |
| `lineproductdescription`         | A termék leírása. |
| `linequantity`                   | A sorhoz rendelt egységek száma, valamint a mértékegység (például **db** vagy **pár**). |
| `lineunit`                       | A sor mértékegysége. |
| `linequantity_withoutunit`       | A sorhoz rendelt egységek száma a mértékegység nélkül. |
| `linequantitypicked`             | A **PickOrder** esemény használatakor a kiválasztott egységek száma. Ellenkező esetben **0** (nulla). |
| `linequantitypicked_withoutunit` | A **PickOrder** esemény használatakor a kiválasztott egységek száma a mértékegység nélkül. Ellenkező esetben **0** (nulla). |
| `linequantitypacked`             | Amikor a **PackOrder** és a **Rendelés készen áll a felvételre** eseményeket használja, a csomagolt egységek száma. Ellenkező esetben **0** (nulla). |
| `linequantitypacked_withoutuom`  | Amikor a **PackOrder** és a **Rendelés készen áll a felvételre** eseményeket használja, a csomagolt egységek száma a mértékegység nélkül. Ellenkező esetben **0** (nulla). |
| `linequantityshipped`            | Mindig **0** kivéve bizonyos események alkalmazásakor a következő sorban leírtak szerint. |
| `linequantityshipped_withoutuom` | A **ShipOrder** esemény használatakor a kiválasztott egységek száma a mértékegység nélkül. Ellenkező esetben **0** (nulla). |
| `lineprice`                      | Az adott egység ára. |
| `linenetamount`                  | A sor ára az egységek és az engedmények számának alkalmazása után. |
| `linediscount`                   | Az adott egységhez tartozó engedmény. |
| `lineshipdate`                   | A sor szállítási dátuma. |
| `linedeliverydate`               | A sor kiszállítási dátuma. |
| `linedeliverymode`               | A sor kiszállítási módja. |
| `linedeliveryaddress`            | A sor kiszállítási címe. |
| `linepickupdate`                 | A vevő által megadott átvételi dátum egy átvételi módot használó megrendelések esetében. |
| `linepickuptimeslot`             | A vevő által megadott átvételi időintervallum egy átvételi módot használó megrendelések esetében. |
| `giftcardnumber`                 | Az ajándékutalvány száma az ajándékutalvány-típus termékei esetében. |
| `giftcardbalance`                | Az ajándékutalvány egyenlege az ajándékutalvány-típus termékei esetében. |
| `giftcardmessage`                | Az ajándékutalvány üzenete az ajándékutalvány-típus termékei esetében. |
| `giftcardpin`                    | Az ajándékutalvány PIN-kódja az ajándékutalvány-típus termékei esetében. (Ez a helyőrző a külső ajándékutalvány-kártyákra vonatkozik.) |
| `giftcardexpiration`             | Az ajándékutalvány lejárati dátuma az ajándékutalvány-típus termékei esetében. (Ez a helyőrző a külső ajándékutalvány-kártyákra vonatkozik.) |
| `giftcardrecipientname`          | Az ajándékutalvány címzettjének neve az ajándékutalvány-típus termékei esetében. |
| `giftcardbuyername`              | Az ajándékutalvány vásárlójának neve az ajándékutalvány-típus termékei esetében. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Rendelési sor helyőrzőinek formátuma az e-mail üzenet törzsében

Amikor az e-mail-üzenet törzsében létrehozza az egyes rendeléssorok HTML-jét, vegye körbe az ismétlődő HTML-blokkokat és a sorra vonatkozó helyőrzőkkel. A helyőrzők HTML-megjegyzéscímkékben vannak.

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

- A nyugta szövegét a **%message%** helyőrzővel lehet beilleszteni az e-mailbe. Ha biztosítani szeretné, hogy a nyugta törzse helyesen legyen megjelenítve, akkor a **%message%** helyőrzőt vegye körbe HTML **&lt;pre&gt;** és **&lt;/pre&gt;** címkékkel.
- A **%receiptid%** helyőrző a nyugtaazonosítónak megfelelő QR-kód vagy vonalkód megjelenítésekor használható. (A QR-kódokat és a vonalkódokat egy külső szolgáltatás generálja dinamikusan és biztosítja.) Ha további tájékoztatást szeretne kapni arról, hogyan jeleníthet meg QR-kódot vagy vonalkódot egy e-mailben küldött nyugtán, lásd: [QR-kód vagy vonalkód hozzáadása a tranzakciós és bevételezési e-mailekhez](add-qr-code-barcode-email.md).

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

[E-mail nyugták beállítása](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[E-mailes nyugták küldése a Modern POS szolgáltatásból ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
