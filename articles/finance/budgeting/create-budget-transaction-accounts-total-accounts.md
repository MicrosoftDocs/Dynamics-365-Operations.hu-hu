---
title: Költségvetés létrehozása tranzakciószámlákból vagy összegző számlákból
description: Ez a cikk betekintést nyújt az összegző számlákon alapuló költségvetés-létrehozás folyamatába. Azt is bemutatja, hogyan kapcsolja be a költségvetés-ellenőrzést az összegző számlák esetében, már amennyiben szükséges a költségvetés-ellenőrzés.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c2298a774e35bc92fafb8bc24871b288fb198d7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003081"
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



