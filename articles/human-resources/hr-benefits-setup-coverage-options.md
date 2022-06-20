---
title: Fedezeti lehetőségek létrehozása
description: Ez a témakör leírja, hogy milyen fedezeti lehetőségek állnak rendelkezésre a Microsoftban Dynamics 365 Human Resources a résztvevők juttatási tervben vagy programban való részvételére.
author: twheeloc
ms.date: 08/24/2021
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
ms.openlocfilehash: 8569cabf72871396b9935a14a5637e5e645705fb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848224"
---
# <a name="create-coverage-options"></a>Fedezeti lehetőségek létrehozása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A fedezeti lehetőségek határozzák meg, hogy kinek jár fedezet, illetve hogy mekkora fedezet érhető el a biztosítási konstrukcióban. Például egy egészségügyi biztosítási terv esetében lehet egy **csak munkavállaló**, egy **munkavállaló + 1** opció és egy **családi** opció. Az életbiztosításnál lehet **1 x fizetés**, illetve **2 x fizetés** fedezetet kínálni.

A definiálásukat követően, a juttatások fedezeti beállításai újra felhasználhatók. Egy beállítást egy vagy több tervhez is társítani lehet.

> [!IMPORTANT]
> A fedezeti beállítások megadása után csatolja ezeket egy juttatásiterv-típushoz. A program ezt követően egy juttatási tervhez vagy programhoz rendeli hozzá a tervtípust. A tervtípushoz társított fedezeti beállítások minden olyan terv számára elérhetők, amelyeket az adott típussal hoztak létre.

## <a name="create-coverage-options"></a>Fedezeti lehetőségek létrehozása
1. A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpont alatt található, válassza a **Fedezeti beállítások** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Fedezeti beállítás** | A fedezeti beállítások egyedi neve. |
   | **Leírás** | A fedezeti beállítás leírása. |
   | **Fedezeti kód** | A fedezeti kódok minimális és maximális összegeket rendelnek hozzá minden jogosult fedezett személytípushoz. A fedezeti kód a jogosultságot vagy azt jelzi, hogy az adott tervtípushoz mekkora fedezetösszeg engedélyezett. A fedezet összegét dollárban vagy százalékban lehet kifejezni. Példa:<ul><li>**Alk+1** – a minősítéshez az alkalmazottnak ki kell választania egy függő felet (ha egynél több van kiválasztva, már nem lehet jogosult).</li><li>**Alk+család** – a minősítéshez az alkalmazottnak legalább két függő felet kell kiválasztania.</li></ul> |
   | **Maximális szám** | A függő felek maximális száma. |
   | **Állapot** | A fedezeti beállítás állapota. Ha a Fedezet opció állapota **Inaktív**, a Fedezet opció nem választható ki a tervtípusoknál. |
   | **Százalék** | A százalékos összeg. Ez a mező csak akkor aktív, ha a Fedezet kódja mezőben % x Fizetés van kiválasztva. |
   | **Osztó** | A(z) % x fedezeti kód kiválasztásakor a számításban használt osztó. |
   | **Százalék minimuma** | Minimális százalék a százalékos fedezeti kód kiválasztása esetén. |
   | **Százalék maximuma** | Maximális százalék a százalékos fedezeti kód kiválasztása esetén. |

4. A **Személyes kapcsolattartásra vonatkozó jogosultsági beállítások** pontban csatolja a megfelelő személyes kapcsolattartók jogosultsági beállítását mindegyik fedezeti beállításhoz.

5. Az **Önkiszolgálás** pontban adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Alkalmazotti hozzájárulás összegének engedélyezése** | Meghatározza, hogy az alkalmazottaknak lehetővé tegye-e a hozzájárulás összegének módosítását a juttatások önkiszolgálásában, amikor a juttatásokat választják. Ha bejelöli ezt a jelölőnégyzetet, a rendszer a juttatási terv paramétereit a munkavállaló által a juttatások önkiszolgáló szolgáltatásban megadott járulékösszeg alapján számítja ki. |
   | **Alkalmazotti fedezet összegének engedélyezése** | Meghatározza, hogy az alkalmazottaknak lehetővé tegye-e a fedezeti összeg módosítását a juttatások önkiszolgáló szolgáltatásban, amikor a juttatásokat kiválasztják. Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon fedezeti összeg alapján, amelyet az alkalmazott önkiszolgáló alkalmazottként megad. |

6. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
