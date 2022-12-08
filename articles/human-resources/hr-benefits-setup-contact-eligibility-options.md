---
title: A személyes kapcsolattartó jogosultsági beállításainak konfigurálása
description: Ez a cikk bemutatja, hogy hogyan konfigurálhatja a Microsoft személyes kapcsolattartói jogosultsági beállításait Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e3e393002901f31c035a54bd8036ed20ecdf9e00
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803884"
---
# <a name="configure-personal-contact-eligibility-options"></a>A személyes kapcsolattartó jogosultsági beállításainak konfigurálása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk bemutatja, hogy hogyan konfigurálja a Microsoft juttatásokban használható személyes kapcsolattartó-típusait Dynamics 365 Human Resources. A személyes kapcsolattartók azok a személyek, akikre a terv fedezete vonatkozik (eltartottak), vagy akik a tervek kedvezményezettjei lesznek (kedvezményezettek). Az eltartottak általában házastársak vagy gyermekek. A kedvezményezettek házastársak, gyermekek, alapok vagy szülők lehet.

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
   | **Kor** |Megadja a juttatási terv jogosult személyes kapcsolattartó maximális korát. Ez a mező csak akkor aktív, ha választ egy kapcsolatot. A rendszer összehasonlítja ezt az életkort a személyes kapcsolattartó számított életkorával. Számított életkor: (fedezeti dátum – személyes kapcsolattartó születési dátuma / 365). Ez a szám mindig egész szám.
A **túlórafüggő személyes** kapcsolattartási jogosultságok esetén a mezőben a korhatár a minimális kor. Ha például a túlórafüggő beállítás 18-ra van állítva a korhoz, akkor a 18 vagy 18 **éves** túlórafüggőként megjelölt eltartottak lesznek az alkalmazhatósági beállításban.  |

4. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
