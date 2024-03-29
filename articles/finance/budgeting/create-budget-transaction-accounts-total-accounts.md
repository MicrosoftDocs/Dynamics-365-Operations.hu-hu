---
title: Költségvetés létrehozása tranzakciószámlákból vagy összegző számlákból
description: Ez a cikk betekintést nyújt az összegző számlákon alapuló költségvetés-létrehozás folyamatába. Azt is bemutatja, hogyan kapcsolja be a költségvetés-ellenőrzést az összegző számlák esetében, már amennyiben szükséges a költségvetés-ellenőrzés.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: kfend
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33f7e49c56a5780644023b6b4fdcbc0937f7f90b
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714397"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Költségvetés létrehozása tranzakciószámlákból vagy összegző számlákból

[!include [banner](../includes/banner.md)]

Ez a cikk betekintést nyújt az összegző számlákon alapuló költségvetés-létrehozás folyamatába. Azt is bemutatja, hogyan kapcsolja be a költségvetés-ellenőrzést az összegző számlák esetében, már amennyiben szükséges a költségvetés-ellenőrzés.

A költségvetési terv és a költségvetési tételjegyzék-bejegyzés dokumentumaival olyan fő számlákra készíthet költségvetést, melyek típusa **Összesen**. A tényadatok csak tranzakciós fő számlákra adhatóak fel. 

A **Költségvetési terv létrehozása a Főkönyv alapján** időszakos folyamatnál a **Forrás** lapon lehet feltételként beállítani az **Összesen** típusú fő számlákat. Ebben az esetben minden összesen típusú főszámla szerepelni fog a cél költségvetési tervben, és az összeg megegyezik a tartományban kiválasztott fő számlák teljes összegével. 

Költségvetés-ellenőrzést is aktiválhat az **Összesen** típusú fő számlákra. Ezt a funkciót a költségvetési csoportok használata támogatja. Minden összesen típusú fő számlánál egy költségvetési csoportnak kell vezérelnie a költségvetést, amelyet a **Költségvetés-ellenőrzési konfiguráció** oldalon lehet létrehozni. A kritériumok között meg kell adni az összesen típusú főszámlát és a számlatartományt. A költségvetési csoportok létrehozásának folyamata felgyorsítható a költségvetés-ellenőrzési csoportok adatentitásaival. 

Ha költségvetést használ jelentéseknél, például pénzügyi kimutatásokban, akkor az összegző számla költségvetési összege az alábbi összegekből áll:

-   Az összegző számla intervallumán belül az egyes főkönyvi tranzakciószámlákon elkönyvelt költségvetések.
-   A közvetlenül az összegző számlán elkönyvelt költségvetési összeg.

Így lehet külön költségvetéseket létrehozni az összegző számla intervallumának legfontosabb tranzakciószámláihoz és hozzáadni a fennmaradó költségvetési összeget az összegző számlához.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
