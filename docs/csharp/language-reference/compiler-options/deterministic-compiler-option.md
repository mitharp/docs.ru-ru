---
title: -deterministic (параметры компилятора C#)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2cb45ea6ed5c5795c910b2f6c3575b12f8189cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-deterministic"></a><span data-ttu-id="8476c-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="8476c-102">-deterministic</span></span>

<span data-ttu-id="8476c-103">Указывает компилятору на необходимость создания сборки, чьи побайтовые выходные данные идентичны в разных компиляциях, если входные данные идентичны.</span><span class="sxs-lookup"><span data-stu-id="8476c-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="8476c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8476c-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="8476c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8476c-105">Remarks</span></span>

<span data-ttu-id="8476c-106">По умолчанию выходные данные компилятора из заданного набора входных данных являются уникальными, поскольку компилятор добавляет метку времени и идентификатор GUID, который создается из случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="8476c-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="8476c-107">Вы можете использовать параметр `-deterministic` для создания *детерминированной сборки*, двоичное содержимое которой идентично в разных компиляциях при условии, что входные данные не изменяются.</span><span class="sxs-lookup"><span data-stu-id="8476c-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="8476c-108">Компилятор учитывает идентичность следующих входных данных:</span><span class="sxs-lookup"><span data-stu-id="8476c-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="8476c-109">Последовательность параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="8476c-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="8476c-110">Содержимое RSP-файла ответов в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="8476c-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="8476c-111">Точная версия компилятора и его связанные сборки.</span><span class="sxs-lookup"><span data-stu-id="8476c-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="8476c-112">Текущий путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="8476c-112">The current directory path.</span></span>
- <span data-ttu-id="8476c-113">Двоичное содержимое всех файлов, явным образом переданных компилятору прямо или косвенно, в том числе:</span><span class="sxs-lookup"><span data-stu-id="8476c-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
    - <span data-ttu-id="8476c-114">Исходные файлы</span><span class="sxs-lookup"><span data-stu-id="8476c-114">Source files</span></span>
    - <span data-ttu-id="8476c-115">Связанные сборки</span><span class="sxs-lookup"><span data-stu-id="8476c-115">Referenced assemblies</span></span>
    - <span data-ttu-id="8476c-116">Связанные модули</span><span class="sxs-lookup"><span data-stu-id="8476c-116">Referenced modules</span></span>
    - <span data-ttu-id="8476c-117">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="8476c-117">Resources</span></span>
    - <span data-ttu-id="8476c-118">Файл ключа строгого имени</span><span class="sxs-lookup"><span data-stu-id="8476c-118">The strong name key file</span></span>
    - <span data-ttu-id="8476c-119">Файлы ответов @</span><span class="sxs-lookup"><span data-stu-id="8476c-119">@ response files</span></span>
    - <span data-ttu-id="8476c-120">Анализаторы</span><span class="sxs-lookup"><span data-stu-id="8476c-120">Analyzers</span></span>
    - <span data-ttu-id="8476c-121">Наборы правил</span><span class="sxs-lookup"><span data-stu-id="8476c-121">Rulesets</span></span>
    - <span data-ttu-id="8476c-122">Дополнительные файлы, которые могут использоваться анализаторами</span><span class="sxs-lookup"><span data-stu-id="8476c-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="8476c-123">Текущий язык и региональные параметры (для языка сообщений о диагностике и исключениях).</span><span class="sxs-lookup"><span data-stu-id="8476c-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="8476c-124">Кодировка по умолчанию (или текущая кодовая страница), если кодировка не указана.</span><span class="sxs-lookup"><span data-stu-id="8476c-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="8476c-125">Наличие, отсутствие и содержимое файлов на пути поиска компилятора (задается, например, с помощью `/lib` или `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="8476c-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="8476c-126">Платформа среды CLR, в которой выполняется компилятор.</span><span class="sxs-lookup"><span data-stu-id="8476c-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="8476c-127">Значение `%LIBPATH%`, которое может повлиять на загрузку зависимостей анализатора.</span><span class="sxs-lookup"><span data-stu-id="8476c-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="8476c-128">Если источники общедоступны, детерминированную компиляцию можно использовать, чтобы установить, компилируются ли двоичные данные из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="8476c-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="8476c-129">Ее также можно использовать в системе непрерывной сборки, чтобы определить необходимость выполнения шагов сборки, зависящих от изменений в двоичном файле.</span><span class="sxs-lookup"><span data-stu-id="8476c-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="8476c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8476c-130">See Also</span></span>  
 [<span data-ttu-id="8476c-131">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="8476c-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="8476c-132">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="8476c-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)