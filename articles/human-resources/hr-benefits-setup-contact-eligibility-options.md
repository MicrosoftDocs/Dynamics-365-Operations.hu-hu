---
title: A személyes kapcsolattartó jogosultsági beállításainak konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben konfigurálhatja a személyes kapcsolattartók jogosultsági beállításait. A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek.
author: andreabichsel
ms.date: 06/25/2021
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
ms.openlocfilehash: 071523e2a1e9de6f0ed2b77e4ad6802efb0073f7
ms.sourcegitcommit: 08797bc43e93ea05711c5a70dd7cdb82cada667a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2021
ms.locfileid: "6558249"
---
# <a name="configure-personal-contact-eligibility-options"></a>A személyes kapcsolattartó jogosultsági beállításainak konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör bemutatja, hogyan lehet konfigurálni a Microsoft Dynamics 365 Human Resources rendszer juttatásaiban használható személyes kapcsolattartók típusait. A személyes kapcsolattartók azok a személyek, akikre a terv fedezete vonatkozik (eltartottak), vagy akik a tervek kedvezményezettjei lesznek (kedvezményezettek). Az eltartottak általában házastársak vagy gyermekek. A kedvezményezettek házastársak, gyermekek, alapok vagy szülők lehet.

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
