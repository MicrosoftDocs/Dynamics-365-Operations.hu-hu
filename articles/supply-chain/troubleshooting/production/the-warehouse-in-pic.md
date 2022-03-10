---
title: A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron.
description: A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron (BOM).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 970930bbdd30b57a8374de7810bb3ece8cb19a7010b5ef19d90bfc39d09f172b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740551"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron

Tudásbáziscikk száma: 4614848

## <a name="symptoms"></a>Tünetek

A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron (BOM).

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. Ha olyan kitárolásilista-naplósor jön létre, amely hivatkozik (a tételazonosítón keresztül) egy termelési anyagjegyzéksorra, a termelési anyagjegyzéksor raktára nem frissül, ha a termelési kitárolásilista-napló sorában később megváltozik a raktár dimenzió.
