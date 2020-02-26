---
title: Fedezeti beállítások létrehozása
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009224"
---
# <a name="create-coverage-options"></a>Fedezeti beállítások létrehozása

[!include [banner](includes/preview-feature.md)]

A Microsoft Dynamics 365 Human Resources fedezeti beállításai olyan fedezeti szintek, amelyek a résztvevők megválasztását jellemzik a juttatási tervben vagy programban, például az egészségügyi terv esetében a „csak alkalmazottak„ terv, vagy az életbiztosítási terv esetében a „kétszeri fizetés”. Ha már egyszer megadták, a juttatások fedezeti beállításai újra felhasználhatók, valamint a beállítások újra társíthatók egy vagy több tervhez.

A fedezeti beállítások megadása után csatolja a fedezeti beállításokat egy juttatásiterv-típushoz. A program ezt követően egy juttatási tervhez vagy programhoz rendeli hozzá a tervtípust. A tervtípushoz társított fedezeti beállítások minden olyan terv számára elérhetők lesznek, amelyeket az adott tervtípussal hoztak létre. 

1. A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpont alatt található, válassza a **Fedezeti beállítások** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Fedezeti beállítás** | A fedezeti beállítások egyedi neve. |
   | **Leírás** | A fedezeti beállítás leírása. |
   | **Fedezeti kód** | A fedezeti kódok minimális és maximális összegeket rendelnek hozzá minden jogosult fedezett személytípushoz. A fedezeti kód a jogosultságot vagy azt jelzi, hogy az adott tervtípushoz mekkora fedezetösszeg engedélyezett. A fedezet összegét dollárban vagy százalékban lehet kifejezni. Példa:</br></br>- **Alk+1** – a minősítéshez az alkalmazottnak ki kell választania egy függő felet (ha egynél több van kiválasztva, már nem lehet jogosult).</br></br>- **Alk+család** – a minősítéshez az alkalmazottnak legalább két függő felet kell kiválasztania. |
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
