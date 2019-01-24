---
title: Свойство SmiOrderProperty.Item (Microsoft.SqlServer.Server)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5453167e16e2658b3546b7114201b04d481a0c79
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223018"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="607d3-102">Свойство SmiOrderProperty.Item</span><span class="sxs-lookup"><span data-stu-id="607d3-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="607d3-103">Получает порядок столбцов для сущности.</span><span class="sxs-lookup"><span data-stu-id="607d3-103">Gets the column order for the entity.</span></span> <span data-ttu-id="607d3-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="607d3-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="607d3-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="607d3-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="607d3-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="607d3-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="607d3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="607d3-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="607d3-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="607d3-108">Property value</span></span>

<span data-ttu-id="607d3-109">Порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="607d3-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="607d3-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="607d3-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="607d3-111">`SmiOrderProperty.Item` Свойство является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="607d3-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="607d3-112">Майкрософт не поддерживает использование этого свойства в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="607d3-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="607d3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="607d3-113">Requirements</span></span>

<span data-ttu-id="607d3-114">**Пространство имен:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="607d3-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="607d3-115">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="607d3-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="607d3-116">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="607d3-116">**.NET Framework versions:** Available since 2.0.</span></span>