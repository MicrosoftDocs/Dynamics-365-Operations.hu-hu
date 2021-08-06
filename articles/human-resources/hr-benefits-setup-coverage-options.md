---
title: Fedezeti lehetőségek létrehozása
description: A Microsoft Dynamics 365 Human Resources fedezeti lehetőségei fedezeti szintek a résztvevőknek egy juttatási csomagban vagy programban.
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
ms.openlocfilehash: 1e8f13075a9835963c231a8e4e8a737368a952ba
ms.sourcegitcommit: 08797bc43e93ea05711c5a70dd7cdb82cada667a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2021
ms.locfileid: "6558225"
---
# <a name="create-coverage-options"></a>Fedezeti lehetőségek létrehozása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A fedezeti lehetőségek határozzák meg, hogy kinek jár fedezet, illetve hogy mekkora fedezet érhető el a biztosítási konstrukcióban. Például egy egészségügyi terv esetén lehet egy **csak az alkalmazott** lehetőség, egy **alkalmazott + 1** lehetőség és egy **családra** lehetőség. Az életbiztosításnál lehet **1 x fizetés**, illetve **2 x fizetés** fedezetet kínálni.

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
   | **Állapot** | A fedezeti beállítás állapota. Ha a Fedezeti beállítás állapota inaktív értékre van állítva, akkor a program nem jelöli be a fedezeti beállítást a tervtípusokon. |
   | **Százalék** | A százalékos összeg. Ez a mező csak akkor aktív, ha a Fedezet kódja mezőben % x Fizetés van kiválasztva. |
   | **Osztó** | A(z) % x fedezeti kód kiválasztásakor a számításban használt osztó. |
   | **Százalék minimuma** | Minimális százalék a százalékos fedezeti kód kiválasztása esetén. |
   | **Százalék maximuma** | Maximális százalék a százalékos fedezeti kód kiválasztása esetén. |

4. A **Személyes kapcsolattartásra vonatkozó jogosultsági beállítások** pontban csatolja a megfelelő személyes kapcsolattartók jogosultsági beállítását mindegyik fedezeti beállításhoz.

5. Az **Önkiszolgálás** pontban adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Alkalmazotti hozzájárulás összegének engedélyezése** | Azt adja meg, hogy az alkalmazottak módosíthatják-e az önkiszolgálói juttatás összegét a juttatások kiválasztása alkalmával. Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon hozzájárulás összege alapján, amelyet az alkalmazott önkiszolgáló juttatásként megad. |
   | **Alkalmazotti fedezet összegének engedélyezése** | Azt adja meg, hogy az alkalmazottak módosíthatják-e a fedezeti juttatás önkiszolgálói összegét a juttatások kiválasztása alkalmával. Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon fedezeti összeg alapján, amelyet az alkalmazott önkiszolgáló alkalmazottként megad. |

6. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
