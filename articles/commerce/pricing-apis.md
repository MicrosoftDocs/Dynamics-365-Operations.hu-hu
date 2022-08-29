---
title: Commerce pricing API-k
description: Ez a témakör az árképzési motor által biztosított különféle árképzési API-król Microsoft Dynamics 365 Commerce nyújt részletes információkat.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2022
ms.locfileid: "9293649"
---
# <a name="commerce-pricing-apis"></a>Commerce pricing API-k

[!include [banner](../includes/banner.md)]

Ez a témakör az árképzési motor által biztosított különféle árképzési API-król Microsoft Dynamics 365 Commerce nyújt részletes információkat.

Az Dynamics 365 Commerce árképzési motor a következő Retail Server API-kat szolgáltatja, amelyek a külső alkalmazások által a különböző árképzési helyzetek támogatása érdekében használhatók fel:

- **GetActivePrices** – ez az API egy termék számított árát kapja meg, egyszerű engedményekkel együtt.
- **CalculateSalesDocument** – ez az API kiszámítja az árakat és engedményeket a termékekhez adott mennyiségekben, ha együtt vásárolják őket.
- **GetAvailablePromotions – ez** az API a kosárba kerül termékekre vonatkozó engedményeket kapja. 
- **AddMarinpons** – ez az API hozzáadja az utalványokat a kosárhoz.
- **RemoveMarinpons** – ez az API eltávolítja az utalványokat egy kosárból.

A Retail Server API-k [külső alkalmazásokban történő alkalmazáson történő alkalmazáson keresztüli alkalmazáson történő alkalmazásról a Retail Server API-k külső alkalmazásokban való alkalmazáson keresztül történő alkalmazáson keresztüli alkalmazáson keresztüli alkalmazáson történő alkalmazáson keresztül történő alkalmazásról nyújt további tájékoztatást](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

A *GetActivePrices* API-t a Commerce 10.0.4-es verziójának kiadása is bevezette. Ez az API egy termék számított árát, beleértve az egyszerű engedményeket is. Nem számít ki többsoros engedményeket, és abból indul ki, hogy az API-kérésben szereplő mindegyik terméknek 1 a mennyisége. Ez az API a termékek listáját is figyelembe veszi bemenetként, és lekérdezheti az egyes termékek tömeges árát.

A *GetActivePrices* API támogatja az **Alkalmazott**, a Vevő **,** **a Névtelen** **és az Alkalmazás commerce** szerepköreit.

*A GetActivePrices* API fő esete a termék részletező lapja (PDP), ahol a kiskereskedők le szeretné árazni a termék legjobb árát, az esetleges engedményekkel együtt.

Az alábbi táblázat bemutatja a *GetActivePrices* API bemeneti paramétereit.

| Név                                    | Alnév | Típus | Kötelező/nem kötelező | Leírás |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | Előrejelzési tartomány | Kötelező | |
|                                         | Csatornaazonosító | Hosszú | Kötelező | |
|                                         | Katalógusazonosító | Hosszú | Kötelező | |
| termékazonosítók                              | | IEnumerable\<long\> | Kötelező | Azon termékek listája, amelyekhez ki kell számítani az árakat. |
| activeDate                              | | DateTimeOffset | Kötelező | Az árak számításának dátuma. |
| Vevőkód                              | | karakterlánc | Választható | A vevő számlaszáma. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Választható | A hűségszintek és a hűségszintek. |
|                                         | AffiliationId | Hosszú | Kötelező | A kapcsolat azonosítója. |
|                                         | Hűségazonosító | Hosszú | Választható | A hűségszint azonosítója |
| includeSimpleDiscountsInContextualPrice | | Bool | Választható | Állítsa igazra ezt a **paramétert**, hogy az egyszerű engedmények szerepeljenek az árszámításban. Az alapértelmezett érték a **hamis**. |
| includeVariantPriceRange                | | Bool | Választható | Állítsa be ezt a paramétert **igazra**, hogy a minimális és maximális árakat az alaptermék minden változatában megveszi. Az alapértelmezett érték a **hamis**. |
| includeAttainablePricesAndDiscounts     | | Bool | Választható | Állítsa be ezt a paramétert **igazra**, hogy elérhető árakat és engedményeket kap. Az alapértelmezett érték a **hamis**. |

**Minta kérelem törzse**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Minta válasz törzse**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

A *CalculateSalesDocument* API a Commerce 10.0.25-ös verziójában lett bevezetve. Ez az API kiszámítja adott mennyiségekben a termékek árait és engedményét, ha együttesen vásárolják meg őket egy megrendelésben. *A CalculateSalesDocument* API mögötti árkalkuláció az egysoros engedményeket és a többsoros engedményeket egyaránt figyelembe veszi.

*A CalculateSalesDocument* API fő felhasználási esete az árképzési számítás olyan helyzetekben, amikor nem marad meg a teljes kosár környezete (például értékesítési ajánlatok). Ebben az esetben a pénztári (POS) és a Commerce e-commerce helyzet is előnyös lehet. A bevásárlókocsiban lévő cikkek készletként (például különálló kötegek, csatolt vagy javasolt termékek, illetve a kosárhoz már hozzáadott termékek) esetén alacsonyabb összár előfordulhat, hogy a vevők learatják a termékeket a kosárba.

A CalculateSalesDocument *API* kérésének és válaszának adatmodellja a **Kosár**. Az API kontextusában azonban az adatmodell **neve SalesDocument**. Mivel a tulajdonságok nagy része nem kötelező, és csak a tulajdonságok egy része befolyásolja az árképzési számítást, a következő táblázatban csak az árképzéshez kapcsolódó mezők jelennek meg. Nem ajánljuk, hogy az API-kérelemben más mezők is részt vesznek.

*A CalculateSalesDocument* API hatóköre csak az árak és az engedmények számítása. Nincsenek benne adók és költségek.

Az alábbi táblázat bemutatja a salesDocument nevű objektumon **belüli bemeneti paramétereket**.

| Név             | Alnév | Típus | Kötelező/nem kötelező | Leírás |
|------------------|----------|------|-------------------|-------------|
| Azonosító               | | karakterlánc | Kötelező | Az értékesítési dokumentum azonosítója. |
| CartLines        | | Lista\<CartLine\> | Választható | Azon sorok listája, amelyekhez ki kell számítani az árakat és engedményeket. |
|                  | ProductId | Hosszú | A CartLine hatókörében kötelező | A termékrekord azonosítója. |
|                  | ItemId | karakterlánc | Választható | A cikk azonosítója. Ha meg van adva érték, meg kell egyeznie a Termékazonosító paraméter **értékével**. |
|                  | InventoryDimensionId | karakterlánc | Választható | A készletdimenzió azonosítója. Ha meg van adva érték, **az ItemId** **és a InventoryDimensionId** **értékek kombinációjának meg kell egyeznie a ProductId paraméter értékével**. |
|                  | Mennyiség | Decimális | A CartLine hatókörében kötelező | A termék mennyisége. |
|                  | UnitOfMeasureSymbol | karakterlánc | Választható | A termék egysége. Alapértelmezés szerint, ha nincs megjelölve érték, az API a termék értékesítési egységét használja. |
| CustomerId       | | karakterlánc | Választható | A vevő számlaszáma. |
| Hűségkártyaazonosító    | | karakterlánc | Választható | A hűségkártya azonosítója A hűségkártyához társított vevői fiókoknak meg **kell egyezniük a CustomerId** paraméter értékével (amennyiben meg van adva). A hűségkártya nem lesz figyelembe véve, ha nem található, vagy az állapota Zárolva **.** |
| AffiliationLines | | Lista\<AffiliationLoyaltyTier\> | Választható | A hűségszint sorai a kapcsolati rétegben. Ha **CustomerId** és/vagy **LoyaltyCardId** értékeket ad meg, a rendszer egyesíteni fogja a **kapcsolódó hűségszint-sorokat az AffiliationLines** értékben megadott sorokkal. |
|                  | AffiliationId | Hosszú | Az AffiliationLoyaltyTier hatókörében kötelező | A kapcsolat rekordazonosítója |
|                  | Hűségazonosító | Hosszú | Az AffiliationLoyaltyTier hatókörében kötelező | A hűségszint rekordazonosítója |
|                  | AffiliationTypeValue | Int | Az AffiliationLoyaltyTier hatókörében kötelező | Ez az érték jelzi, hogy a **kapcsolati** sor általános típusú (**0**) **vagy hűség típusú** (**1**). Ha a paraméter értéke **0**, az API **az AffiliationId** **értéket veszi azonosítóként, és figyelmen kívül hagyja a LoyaltyTierId** értékét. **Ha 1-re** van állítva, az API **a LoyaltyTierId** **értéket veszi azonosítóként, és figyelmen kívül hagyja az AffiliationId** értékét. |
|                  | ReasonCodeLines | Beszedés\<ReasonCodeLine\> | Az AffiliationLoyaltyTier hatókörében kötelező | Okkódsorok. Ez a paraméter nincs hatással az árszámításra, **de az AffiliationLoyaltyTier objektum részeként szükség van rá**. |
|                  | CustomerId | karakterlánc | Az AffiliationLoyaltyTier hatókörében kötelező | A vevő számlaszáma. |
| Utalványok          | | Lista\<Coupon\> | Választható | Az nem alkalmazható (inaktív, lejárt vagy nem található) utalványok nem lesznek figyelembe véve az árképzési számításban. |
|                  | Kód | karakterlánc | Az utalvány hatókörében kötelező | Az utalvány kódja |
|                  | Kódazonosító | karakterlánc | Választható | Az utalványkód azonosítója Ha meg van adva érték, meg kell egyeznie a Kód paraméter **értékével**. |
|                  | DiscountOfferId | karakterlánc | Választható | Az engedmény azonosítója. Ha meg van adva érték, meg kell egyeznie a Kód paraméter **értékével**. |

**Minta kérelem törzse**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

A teljes kosár objektum válasz törzseként ad vissza. Az árak és engedmények ellenőrzéséhez az alábbi táblázatban található mezőkre kell fókuszálni.

| Név           | Alnév | Típus | Leírás |
|----------------|----------|------|--------------|
| Nettó ár       | | Decimális | A teljes értékesítési dokumentum nettó ára engedmények alkalmazása előtt. |
| Kedvezmény összegének | | Decimális | A teljes értékesítési dokumentum teljes engedményösszege. |
| Összeg összesen    | | Decimális | A teljes értékesítési dokumentum teljes összege. |
| CartLines      | | Lista\<CartLine\> | Számított sorok, amelyek tartalmazzák az ár- és engedményadatokat. |
|                | Ár | Decimális | A termék egységára. |
|                | Nettó ár | Decimális | A sor nettó ára az engedmények alkalmazása előtt (= *Ármennyiség*&times;*·*). |
|                | Kedvezmény összegének | Decimális | Az engedmény összege. |
|                | Összeg összesen | Decimális | A sor végleges teljes árképzési eredménye. |
|                | PriceLines | Lista\<PriceLine\> | Ár részletei, beleértve az ár forrását (alapár, árkorrekció vagy kereskedelmi megállapodás) és az összeget. |
|                | DiscountLines | Lista\<DiscountLine\> | Az engedmény részletei. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

Ha egy kosárban több kosársor van, *akkor a GetAvailablePromotions* API a bevásárlókocsisorokra vonatkozó összes alkalmazható engedményt visszaadja. 

*A GetAvailablePromotions* API fő esete a bevásárlókocsi lap, ahol a kiskereskedők az alkalmazott engedményeket vagy az aktuális kosárhoz rendelkezésre álló utalványokat szeretnék megszüntetni.

Az alábbi táblázat bemutatja a *GetAvailablePromotions* API bemeneti paramétereit.

| Név        | Típus | Kötelező/nem kötelező | Leírás |
|-------------|------|-------------------|-------------|
| kulcs         | karakterlánc | Kötelező | A bevásárlókocsi azonosítója. |
| cartLineIds | IEnumerable\<string\> | Választható | Állítsa be ezt a paramétert, ha csak a kiválasztott bevásárlókocsisorok engedményét adja vissza. |

**Minta válasz törzse**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddPons

Az *AddPonpons* API támogatja az utalványok listájának kosárba való felvételét. A bevásárlókocsi objektumát adja vissza az utalványok hozzáadása után.

Az alábbi táblázat bemutatja az *AddPonpons* API bemeneti paramétereit.

| Név                 | Típus | Kötelező/nem kötelező | Leírás |
|----------------------|------|-------------------|-------------|
| kulcs                  | karakterlánc | Kötelező | A bevásárlókocsi azonosítója. |
| utalványkódok          | IEnumerable\<string\> | Kötelező | A kosárhoz hozzáadni kell az utalványkódokat. |
| isLegacyDiscountCode | Bool | Választható | Állítsa igazra **ezt a paramétert** annak jelzésére, hogy az utalvány örökölt engedménykód. Az alapértelmezett érték a **hamis**. |

## <a name="removecoupons"></a>RemoveMarinpons

Az *RemoveMarinpons* API támogatja az utalványok listájának eltávolítását egy kosárból. Az utalványok eltávolítása után visszaadja a bevásárlókocsiba adott objektumot.

Az alábbi táblázat bemutatja az *RemovePons* API bemeneti paramétereit.

| Név        | Típus | Kötelező/nem kötelező | Leírás |
|-------------|------|-------------------|-------------|
| kulcs         | karakterlánc | Kötelező | A bevásárlókocsi azonosítója. |
| utalványkódok | IEnumerable\<string\> | Kötelező | A kosárból eltávolítható utalványkódok |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
