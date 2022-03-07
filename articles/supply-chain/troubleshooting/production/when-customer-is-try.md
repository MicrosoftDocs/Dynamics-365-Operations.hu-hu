---
title: A tételszám törlődik, ha új tételazonosítót választott
description: Ha egy kitárolási lista naplósorát tekinti át, a Tételszám mezőben lévő érték törlődik, ha új értéket jelöl ki a Tételazonosító mezőben.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026560"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>A tételszám törlődik, ha új tételazonosítót választott

Tudásbáziscikk száma: 4613107

## <a name="symptoms"></a>Tünetek

Ha egy kitárolási lista naplósorát tekinti át, a **Tételszám** mezőben lévő érték törlődik, ha új értéket jelöl ki a **Tételazonosító** mezőben.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. Ha módosítja a tételazonosítót, módosítja az elemkörnyezetet. Ebből következően a kötegszámot vissza lesz állítva.

A tételszámhoz tételazonosító társításához először be kell állítania a tételazonosítót.
