---
title: Költségvetési terv típusai
description: A konstrukciótípus a Microsoft Dynamics 365 Human Resources alkalmazásban a meghatározott típusú juttatások magas szintű csoportosítása. Minden konstrukciótípusnak van egy terv konstrukciótípus-kódja, amely meghatározza a konstrukció típusának szabályait.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb4746425c2faa3c0b1bd3940bf2e03cf7f9595c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057862"
---
# <a name="create-plan-types"></a>Költségvetési terv típusai

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A konstrukciótípus a Microsoft Dynamics 365 Human Resources alkalmazásban a meghatározott típusú juttatások magas szintű csoportosítása. Minden konstrukciótípusnak van egy terv konstrukciótípus-kódja, amely meghatározza a konstrukció típusának szabályait. Például az Alapélettartam konstrukciótípushoz az Élettartam konstrukciótípus-kód szükséges, mivel ez egyfajta életbiztosítási konstrukció, amelyeknek meg kell felelniük az Élettartam konstrukciótípus-kódhoz meghatározott szabályoknak. Egy másik konstrukciótípus lehet a Kiegészítő élettartam, szintén az Élettartam konstrukciótípus-kóddal.

Mindegyik konstrukciótípus jelzi, hogy egy alkalmazott regisztrálhat-e egy vagy több ilyen típusú konstrukcióra. Például egy alkalmazott valószínűleg képes regisztrálni az Alapélettartam és a Kiegészítő élettartam biztosításokra az Élettartam konstrukciótípusból. Egy alkalmazott valószínűleg csak egy Orvosi típusú biztosításra regisztrálhat.

Ha egy konstukciótípus kapcsolattartókat tartalmaz, akkor a konstrukciótípus jelzi, hogy a kapcsolattartók kedvezményezettek vagy függő felek-e. Például egy Alapélettartam konstrukciótípushoz tartozhatnak kedvezményezettek, míg egy Alap orvosi konstukciótípushoz csak függő felek tartozhatnak. Bizonyos esetekben előfordulhat, hogy egy konstrukció nem rendelkezik személyes kapcsolattartókkal. Például egy Rugalmas kiadási számla vagy Parkolási támogatás.

A konstrukciótípus meghatározhatja a fedezeti beállításokat. A fedezeti beállítások a Fedezeti beállítás képernyőn vannak meghatározva. A fedezeti beállítások határozzák meg a juttatás összegét, illetve azokat a kapcsolattartókat, akik jogosultak a konstrukciótípusra. Ha például a kapcsolattartó típusa Kedvezményezett, a fedezeti beállításnak meg kell határoznia, hogy a kedvezményezett milyen feltételekkel kaphat juttatást annak igénybevétele esetén. Ha a kapcsolattartó típusa Függő fél, a fedezeti beállításnak meg kell határoznia a függő fél és az alkalmazott közötti kapcsolatot. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Konstrukciótípusok** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció típusa** | A konstrukciótípust azonosító egyedi név. |
   | **Leírás** | A konstrukciótípus leírása. |
   | **Konstrukció típuskódja** | Válasszon egy konstrukciótípus-kódot az értékek legördülő listájából. A konstrukciótípus-kód listája megjeleníti az aktuális verzióban támogatott összes konstrukciótípust. |
   | **Párhuzamos regisztráció** | Megadja, hogy az alkalmazott több ugyanolyan konstrukciótípusú juttatási konstrukciót is regisztrálhat-e, vagy csak egy juttatási konstrukciót konstrukciótípusonként. |
   | **Névjegy típusa** | Megadja a személyes kapcsolattartó szerepét. Az érték üres, Függő fél és Kedvezményezett lehet. A **Kapcsolattartó típusa** elemet üresen hagyhatja, ha a konstrukciótípus nem igényel függő felet vagy kedvezményezettet a fedezeti beállítás alapján. |

4. Az élettartam-esemény beállításainak konfigurálásához válassza ki a **Műveletek** elemet, majd az **Élettartam-esemény beállításai** lehetőséget. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció típusa** | A konstrukciótípus, amely számára az élettartam-esemény beállításait konfigurálni kell. |
   | **Életesemény-típus azonosítója** | A élettartam-esemény típusának azonosítója. |
   | **Megszakítás engedélyezése** | Megadja, hogy az alkalmazott érvénytelenítheti-e a juttatási konstrukciót az élettartam-esemény során. |
   | **Fedezeti beállítás módosítása** | Megadja, hogy az alkalmazott módosíthatja-e a fedezeti beállításokat az élettartam-esemény során. |
   | **Váltás új konstrukcióra** | Megadja, hogy az alkalmazott módosíthatja-e a konstrukciókat az élettartam-esemény során. |
   | **Konstrukció automatikus megszakítása** | Megadja, hogy a konstrukció automatikusan érvénytelenítendő-e a élettartam-eseménye során. |
   | **Jogosultsági ellenőrzés automatikus újranyitása** | Megadja, hogy a rendszer automatikusan nyissa-e újra a juttatási regisztrációra való jogosultsági ellenőrzése az életesemény során. |
   | **Jelentéskészítési időtartam** | Megadja az életeseménnyel kapcsolatos jelentéskészítés időtartamát napokban. **Megjegyzés**: Ha nem ad meg összeget, akkor a rendszer nulla értékre állítja a jelentési ablakot, és nem dolgozza fel az élettartam-eseményt. |

5. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]