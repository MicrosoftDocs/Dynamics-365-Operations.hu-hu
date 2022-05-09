---
title: Nem található egyező eredmény.
description: Ez a témakör leírja, hogyan lehet elhárítani az adószámítási művelet "Nincs egyező eredmény" hibáit.
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
ms.openlocfilehash: c1a343b0b74645d40b0a2582749968cc0a56afd7
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648146"
---
# <a name="no-matching-result-could-be-found"></a>Nem található egyező eredmény.

[!include [banner](../includes/banner.md)]

Ez a témakör az Adószámítás szolgáltatás "Nincs egyező eredmény" hibaüzenete esetén szükséges hibaelhárítási lépéseket mutatja be.

## <a name="symptom"></a>Tünet

A következő hibaüzenet jelenik meg: "Fejléc/sorok - 1, adócsoport, nem található megfelelő eredmény."

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
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
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

A probléma akkor fordul elő, ha helytelen a beállítás a szabályozó konfigurációs szolgáltatásban (RCS).

## <a name="troubleshoot"></a>Hibaelhárítás

1. Töltse le a hibaelhárítási fájlt. A további tudnivalókat lásd [a Hibakeresési mód engedélyezése hibaelhárításhoz](tcs-troubleshooting-enable-debug-mode.md).
2. A beállítási probléma megoldásához hasonlítsa össze az adó-szolgáltatás számításának bemenetét a funkcióbeállítással.

    A következő példa az adószolgáltatás számításának bemenetét mutatja be.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    A következő táblázat felsorolja az RCS adócsoport-alkalmazhatóságát.

    | Header.Üzleti folyamat | Sorok.Üzleti egység | Header.Ship from Irányítószám | Adócsoport |
    |-------------------------|---------------------|---------------------------|-----------|
    | Napló                 |                     |                           | A csoport   |
    | Értékesítés                   |                     | 30160                     | B csoport   |

    Az adószolgáltatás **számításában** **megadott** adatok szerint a fejlécben az Üzleti folyamat értéke Értékesítés, **·** **a fejléc irányítószáma értéke pedig 30159.** Ez a bevitel az RCS alkalmazhatósági szabályain alapul. Mivel nincs egyező sor, a hiba történik.

    > [!NOTE]
    > Ha az alkalmazhatósági szabályban üres az érték, akkor a szabály bármely értékre alkalmazható.

## <a name="mitigation"></a>Kockázatcsökkentés

A hibák enyhítése érdekében hajtsa végre a következő lépéseket.

1. Az RCS esetében használja a **Globalizációs funkciók** \> **Adószámítás** részt.
2. A funkció új verziójának létrehozása.
3. Sor hozzáadása a megfelelő információkhoz.

    | Header.Üzleti folyamat | Sorok.Üzleti egység | Header.Ship from Irányítószám| Adócsoport |
    |-------------------------|---------------------|--------------------------|-----------|
    | Napló                 |                     |                          | A csoport   |
    | Értékesítés                   |                     | 30160                    | B csoport   |
    | Értékesítés                   |                     | 30159                    | B csoport   |

4. A funkcióbeállítás verziójának közzététele
5. A Microsoft Dynamics 365 Pénzügy mezőben **válassza** \> **·** \> **ki az új verziót az Adóbeállítási adó konfigurációs** \> **paraméterei** között.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
