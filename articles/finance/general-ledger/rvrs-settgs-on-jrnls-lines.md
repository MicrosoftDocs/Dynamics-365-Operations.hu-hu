---
title: Naplók és sorok sztornírozási beállításai
description: Ez a cikk azt ismerteti, hogy egy általános naplón bevitt sztornírozási bejegyzés miért nem jelenik meg a feladott tranzakción.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e36a3ea1736e4d7f60a5a6ce588ad3e66c950c14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899842"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Naplók és sorok sztornírozási beállításai

[!include [banner](../includes/banner.md)]

Ez a cikk azt ismerteti, hogy egy általános naplón bevitt sztornírozási bejegyzés miért nem jelenik meg a feladott tranzakción.  

## <a name="symptom"></a>Tünet

Az általános napló tartalmaz egy sztornírozási bejegyzést és egy sztornírozási dátumot a naplóban. A napló feladásakor egyik bizonylat sztornírozása sem történt meg. Miért történik ez?

## <a name="resolution"></a>Megoldás

A napló feladásakor a sztornírozási folyamat csak a **Sztornírozási bejegyzés** és **Sztornírozási dátum** beállítást figyeli a bizonylat **Sorok** szakaszában. Ez a megközelítés lehetővé teszi a napló számára, hogy néhány olyan bizonylatot is tartalmazzon, amelyek sztornírozásra meg vannak jelölve, és másikat is, amelyek nincsenek megjelölve.

A napló értékeit csak alapértelmezettként használja a rendszer, amikor *új* sorokat ad hozzá. A napló értékeinek módosítása nem érinti a meglévő sorokat. Ebben a példában először a bizonylatsorok lettek megadva. Amikor azelőtt adja meg a sor részletes adatait, mielőtt naplót sztornírozási naplóként jelölné meg, a sztornírozási bejegyzésként és dátumként való megjelölést a rendszer nem alkalmazza egyik meglévő sorra sem.

A sztornírozási bejegyzés vagy sztornírozási dátum módosítása egy meglévő soron továbbviszi a módosítást a többi sorra ugyanazon a bizonylaton. A teljesítmény optimalizálása érdekében a rács nem frissül a módosítások más sorokra történő továbbvitele után. A módosított értékeket a rács frissítésével jelenítheti meg.


