---
title: A személyes kapcsolattartó jogosultsági beállításainak konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben konfigurálhatja a személyes kapcsolattartók jogosultsági beállításait. A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 137416477928fd4d6b4438f25df5afea93972027
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112828"
---
# <a name="configure-personal-contact-eligibility-options"></a>A személyes kapcsolattartó jogosultsági beállításainak konfigurálása

Ez a cikk bemutatja, hogyan lehet konfigurálni a Microsoft Dynamics 365 Human Resources rendszer juttatásaiban használt személyes kapcsolattartók típusait. A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Személyes kapcsolattartó jogosultsági beállításai** lehetőséget.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Jogosultsági beállítás** | Az egyedi jogosultsági beállítást azonosító egyedi név vagy kód. |
   | **Leírás** | A jogosultsági beállítás rövid leírása. |
   | **Kapcsolattartói jogosultság kódja** | A személyes jogosultsági beállítást legjobban leíró rendszerkód. A következő lehetőségek közül választhat: <ul><li>Kapcsolat</li><li>Diák</li><li>Felnőtt korú függő fél</li><li>Nagykorú fogyatékossággal élő függő fél</li></ul> |
   | **Állapot** | A jogosultsági beállítás állapota. Ha a jogosultsági beállítás állapota inaktív értékre van állítva, akkor nem lehet kiválasztani a személyes kapcsolattartókra vonatkozó jogosultsági beállításként. |
   | **Kapcsolat** | A személyes kapcsolattartó és az alkalmazott közötti kapcsolatot határozza meg. Ez a mező csak akkor aktív, ha a kapcsolattartó jogosultsági kódja a Kapcsolat értékre van beállítva. |
   | **Kor** | A juttatási konstrukció jogosult személyes kapcsolattartójának maximális életkora. Ez a mező csak akkor aktív, ha választ egy kapcsolatot. A rendszer összehasonlítja ezt az életkort a személyes kapcsolattartó számított életkorával. Számított életkor: (fedezeti dátum – személyes kapcsolattartó születési dátuma / 365). Ez a szám mindig egész szám. |

4. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]