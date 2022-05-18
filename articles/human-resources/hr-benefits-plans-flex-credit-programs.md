---
title: Rugalmas jóváírási programok beállítása
description: A Microsoft Dynamics 365 Human Resources rugalmas jóváírási programjaival az alkalmazottakat előre meghatározott számú rugalmas jóváírásnak megfelelően lehet beléptetni a juttatásokba.
author: twheeloc
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8cca45ad87dad6025c49668434cbd37f32cf4a65
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693255"
---
# <a name="set-up-flex-credit-programs"></a>Rugalmas jóváírási programok beállítása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources rugalmas jóváírási programjaival az alkalmazottakat előre meghatározott számú rugalmas jóváírásnak megfelelően lehet beléptetni a juttatásokba. Az alkalmazottak határozhatják meg, hogyan osztják fel a rugalmas jóváírásaikat. Ha például egy alkalmazottra a házastárs egészségbiztosítási konstrukciója érvényes, akkor felhasználhatja más juttatásokhoz az egyébként egészségbiztosításhoz használt jóváírásokat. 

1. A **Juttatások kezelése** munkaterület **Konstrukciók** beállításánál válassza a **Rugalmas jóváírási programok** lehetőséget.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás-jóváírás azonosítója** | A rugalmas jóváírási program egyedi azonosítója. |
   | **Leírás** | A rugalmas jóváírási program leírása. | 
   | **Kezdő dátum** | A rugalmas jóváírási program aktívvá válásának dátuma. |
   | **Záró dátum** | A rugalmas jóváírási program záró dátuma. Az alapértelmezett érték (2154. 12. 31.) megtartásával jelezheti, hogy a rugalmas jóváírási programnak nincs ütemezett lejárata. |
   | **Jóváírás értéke összesen** | Azoknak a jóváírásoknak a száma, amelyeket az alkalmazottak használni fognak a juttatásaikhoz. |
   | **Arányosítási szabály** | A rugalmas jóváírások arányosításához használt szabály, amely akkor használható, amikor az alkalmazottat a rugalmas jóváírási program időszakának közepén veszik fel. </br></br><ul><li>**Nincs** – Az alkalmazott nem kap rugalmas jóváírásokat, ha a rugalmas jóváírási program időszak kezdete után veszik fel.</li><li>**Teljes jóváírás** – Az alkalmazott megkapja a rugalmas jóváírások teljes összegét, függetlenül attól, hogy mikor vették fel.</li><li>**Arányosítás** – Az alkalmazott a rugalmas jóváírások arányosított összegét kapja meg a kezdési dátumától függően.</li></ul> |
   | **Rugalmas jóváírás arányosítási képlete** | A rugalmas jóváírások arányosításához használt szabály azon alkalmazottak esetében, akiket a rugalmas jóváírási program juttatási időszakának közepén vesznek fel. Az arányosítás az alkalmazott foglalkoztatásának kezdő dátuma alapján történik. Ez a mező csak akkor használható, ha az **Arányosítás** lehetőséget választja az **Arányosítási szabály** mezőben. </br></br><ul><li>**Napi** – Az alkalmazott által kapott rugalmas jóváírások számát a nap szintjéig arányosítja. A rugalmas jóváírások számát az időszak napjainak számával kell elosztani. Ha például a juttatási időszak 400 nap, akkor a rendszer a rugalmas jóváírások számát 400-zal elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak naponta.</li><li>**Aktuális hónap** – Az alkalmazott által kapott rugalmas jóváírások számát a hónap szintjéig arányosítja, az aktuális hónapra kerekítve. A rugalmas jóváírások számát az időszak hónapjainak számával kell elosztani. Ha például a juttatási időszak 15 hónap, akkor a rendszer a rugalmas jóváírások számát 15-tel elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak havonta.</li><li>**Következő hónap** – Az alkalmazott által kapott rugalmas jóváírások számát a hónap szintjéig arányosítja, a következő hónapra kerekítve. A rugalmas jóváírások számát az időszak hónapjainak számával kell elosztani. Ha például a juttatási időszak 15 hónap, akkor a rendszer a rugalmas jóváírások számát 15-tel elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak havonta.</li></ul> |
   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
