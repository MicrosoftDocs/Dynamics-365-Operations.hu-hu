---
title: A jövőbeli életesemények konfigurálása
description: Ez a témakör azt ismerteti, hogyan lehet ütemezni a jövőbeli életeseményeket a következőben:Dynamics 365 Human Resources
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2cb3ca03e0d9d7e5423a405f1eb0372e1c19588d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227985"
---
# <a name="configure-future-life-events"></a>A jövőbeli életesemények konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.

1. A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpontban található, válassza a **Jövőbeli életesemények** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | Életesemény dátuma | A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban. |
   | Életesemény naplózva | Az esemény naplózásának dátuma és ideje. |
   | Eseménynapló típusa | Azt jelzi, hogy a művelet a következők egyike-e:</br></br>- **Frissítés** – olyan meglévő rekord módosítása, amely életeseményeket követ</br></br>- **Beszúrás** – új életesemény rekordjának létrehozása |
   | Életesemény-típus azonosítója | Az életesemény típusának egyedi azonosítója. |
   | Életesemény-típus | Katalizátor az alkalmazotti juttatások regisztrálásának frissítéséhez. A további tudnivalókat lásd a Life event Triggers szakaszban. |
   | Állapot | Annak megjelenítése, hogy feldolgozták-e az életeseményt vagy sem. |
   | Sor | A jövőbeli életesemény sorának száma. |

4. Válassza a **Mentés** lehetőséget. 

A jövőbeli életesemények törölhetők. Ha egy feldolgozott jövőbeli esemény törölve van, akkor a jövőbeli rekord is törlődik. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
