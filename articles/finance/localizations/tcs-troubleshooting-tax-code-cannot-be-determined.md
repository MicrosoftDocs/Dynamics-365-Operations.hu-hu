---
title: Az adókód nem állapítható meg
description: Ez a témakör ismerteti az Adószámítás szolgáltatás "Nem határozható meg az adókódok" hiba elhárítását.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 6a74724de38cf362900277ab9addc8e6894f7689
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877859"
---
# <a name="tax-code-cannot-be-determined"></a>Az adókód nem állapítható meg

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja az adószámítási szolgáltatásban található "Adókód nem határozható meg" hibaüzenet esetén szükséges hibaelhárítási lépéseket.

## <a name="symptom"></a>Tünet

A következő hibaüzenet jelenik meg: "Fejléc/sorok - 1, az adókód nem határozható meg." Másik lehetőségként a hibakeresési fájlban találja meg a hibát, amint az a következő példában látható. A további tudnivalókat lásd [a Hibakeresési mód engedélyezése hibaelhárításhoz](tcs-troubleshooting-enable-debug-mode.md).

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Ok

A probléma valószínűleg előfordul, mert az áfacsoport és a cikkadócsoport nincs egymás között.

## <a name="troubleshoot"></a>Hibaelhárítás

A következő lépések szerint elháríthatja a problémát.

1. A hibakeresési fájlban ellenőrizze, hogy meg van-e határozva az áfacsoport és a cikkadócsoport. Ha az adócsoport **és** **a** cikkadócsoport értékei üresek, akkor az áfacsoport és a cikkadócsoport nem lett meghatározva. Ha meg vannak határozva, az eredmény hibás lehet.

    Az alábbi példa egy hibaelhárítási fájlra mutat be.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
                            "Adjustment": null
                        }
                    ],
                    "Measures": {
                        ...
                    },
                    ...
                }
            ]
        },
        ...
    }
    ```

2. Győződjön meg **róla**, hogy engedélyezve van az Áfa felülírása beállítás **az** értékesítésirendelés-sor részleteinek Beállítás lapján.

    - Ha engedélyezve van, **·** **az** áfakódokat a tranzakciósorhoz megadott adócsoport és cikkadócsoport-értékek határozzák meg. Ellenőrizze, hogy ezek az értékek helyesen vannak-e megadva.
    - Ha ez nincs engedélyezve, ellenőrizze, **·** **hogy helyes értékek vannak-e beállítva az Adócsoport alkalmazhatósága és a Cikkadócsoport alkalmazhatósági mezőiben.** További információ: nincs [egyező](tcs-troubleshooting-no-matching-result.md) eredmény.

3. Ha az áfacsoportot és a cikkadócsoportot helyesen határozzák meg, döntse el, hogy van-e valamilyen nyereséges számukra.

    1. Az RCS szolgáltatásban kattintson az Adó **funkciók adókódok** \> **és adócsoportok** \> **csoportjára.**

        | Sor.adócsoport | Adókódok |
        |----------------|-----------|
        | A csoport        | A         |

    2. Ugrás az Adó **funkciókhoz** \> **: Adókódok és cikkadócsoportok.** \> **·**

        | Sor.Cikk adócsoportja | Adókódok |
        |---------------------|-----------|
        | B csoport             | milliárd         |

    Ha az adócsoportra és a cikkadócsoportra nem igaz a nyereség, akkor a program nem határozza meg az áfakódot.

## <a name="mitigation"></a>Kockázatcsökkentés

1. Menjen végig a [cikk Hibaelhárítás szakaszának](#troubleshoot) mindegyik lépésében, és javítsa ki a szükséges beállításokat. Ha az adócsoport és a cikkadócsoport nem megfelelően lett meghatározva, nem [található egyező eredmény](tcs-troubleshooting-no-matching-result.md).
2. Ha az adócsoportra és a cikkadócsoportra nem jellemző a probléma, hozzon létre egy új funkcióverziót az RCS-ben, és javítsa ki a beállításokat.

    - Ugrás az Adó **funkciókhoz** \> **: Adókódok és cikkadócsoportok.** > **·**

        | Sor.Cikk adócsoportja | Adókódok |
        |---------------------|-----------|
        | B csoport             | A; B       |

    Az adókód meghatározása A **lesz**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
