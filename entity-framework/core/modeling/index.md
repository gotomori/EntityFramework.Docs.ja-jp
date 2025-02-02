---
title: モデルの作成 - EF Core
author: rowanmiller
ms.date: 10/27/2016
ms.assetid: 88253ff3-174e-485c-b3f8-768243d01ee1
uid: core/modeling/index
ms.openlocfilehash: 78a8ffd2393a914edf737104f14e41f8a9074ad5
ms.sourcegitcommit: 87fcaba46535aa351db4bdb1231bd14b40e459b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59929899"
---
# <a name="creating-and-configuring-a-model"></a>モデルの作成と構成

Entity Framework では、一連の規則を利用し、エンティティ クラスの形状に基づいてモデルがビルドされます。 規則にあるものを捕捉する/オーバーライドする目的で、追加構成を指定できます。

この記事では、あらゆるデータ ストアをターゲットにするモデルに適用できる構成、あらゆるリレーショナル データベースをターゲットにするときに適用できる構成について取り上げます。 プロバイダーも、特定のデータ ストアに固有の構成を有効にできます。 プロバイダー固有の構成については、「 [データベース プロバイダー](../providers/index.md) 」セクションを参照してください。

> [!TIP]  
> この記事の [サンプル](https://github.com/aspnet/EntityFramework.Docs/tree/master/samples) は GitHub で確認できます。

## <a name="use-fluent-api-to-configure-a-model"></a>fluent API を使用してモデルを構成する

派生コンテキストで  `OnModelCreating`  メソッドをオーバーライドし、 `ModelBuilder API` を使用してモデルを構成できます。 これは最も強力な構成方法であり、エンティティ クラスを変更しなくても構成を指定できます。 Fluent API 構成には一番上の優先度が与えられ、規則やデータ注釈をオーバーライドします。

[!code-csharp[Main](../../../samples/core/Modeling/FluentAPI/Samples/Required.cs?highlight=11-13)]

## <a name="use-data-annotations-to-configure-a-model"></a>データ注釈を使用してモデルを構成する

クラスやプロパティに属性 (データ注釈と呼ばれています) を適用することもできます。 データ注釈は規則をオーバーライドしますが、Fluent API 構成で上書きされます。

[!code-csharp[Main](../../../samples/core/Modeling/DataAnnotations/Samples/Required.cs?highlight=14)]
