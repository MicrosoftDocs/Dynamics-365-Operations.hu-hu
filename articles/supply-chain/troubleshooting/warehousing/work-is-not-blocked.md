---
title: A munka nincs zárolva
description: A munka nincs zárolva
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6b4361682246397732e8326b98b1b86ff878664e54c8c352296b0d7eaff6bbbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719551"
---
# <a name="work-isnt-blocked"></a>A munka nincs zárolva

Hibakód: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 azonosítóval rendelkező munka nincs zárolva.

## <a name="cause"></a>Ok

A hullám **Blokkolt hullám** beállításának értéke *Nem*. A munka zárolása nem oldható fel, mert jelenleg nincs zárolva.

## <a name="resolution"></a>Felbontás

 Csak azok a munka zárolása oldható fel, amelyekben a **Blokkolt hullám** beállítása *Igen*.
