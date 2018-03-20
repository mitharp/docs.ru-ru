---
title: "Практическое руководство. Изменение содержимого строки (C#)"
ms.date: 02/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 830ca207c4cd5bd24dbb667328465cafb2509409
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-modify-string-contents-in-c"></a><span data-ttu-id="a6ac3-102">Практическое руководство. Изменение содержимого строки в C#</span><span class="sxs-lookup"><span data-stu-id="a6ac3-102">How to: Modify string contents in C#</span></span> #

<span data-ttu-id="a6ac3-103">В этой статье демонстрируется несколько способов получения `string` путем изменения существующего объекта `string`.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-103">This article demonstrates several techniques to produce a `string` by modifying an existing `string`.</span></span> <span data-ttu-id="a6ac3-104">Все показанные методы возвращают результат изменений как новый объект `string`.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-104">All the techniques demonstrated return the result of the modifications as a new `string` object.</span></span> <span data-ttu-id="a6ac3-105">Чтобы это было очевидно, во всех примерах результат сохраняется в новой переменной.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-105">To clearly demonstrate this, the examples all store the result in a new variable.</span></span> <span data-ttu-id="a6ac3-106">Затем вы можете изучить исходный объект `string` и объект `string`, полученный в результате изменений при выполнении каждого примера.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-106">You can then examine both the original `string` and the `string` resulting from the modification when you run each example.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="a6ac3-107">В статье приводится несколько методов.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-107">There are several techniques demonstrated in this article.</span></span> <span data-ttu-id="a6ac3-108">Вы можете заменять существующий текст.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-108">You can replace existing text.</span></span> <span data-ttu-id="a6ac3-109">Вы можете искать шаблоны и заменять соответствующий текст другим.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-109">You can search for patterns and replace matching text with other text.</span></span> <span data-ttu-id="a6ac3-110">Вы можете рассматривать строку как последовательность символов.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-110">You can treat a string as a sequence of characters.</span></span> <span data-ttu-id="a6ac3-111">Вы также можете использовать удобные методы удаления пробелов.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-111">You can also use convenience methods that remove white space.</span></span> <span data-ttu-id="a6ac3-112">Выберите метод, наиболее подходящий для вашего сценария.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-112">You should choose the techniques that most closely match your scenario.</span></span>

## <a name="replace-text"></a><span data-ttu-id="a6ac3-113">Замена текста</span><span class="sxs-lookup"><span data-stu-id="a6ac3-113">Replace text</span></span>

<span data-ttu-id="a6ac3-114">Следующий код создает новую строку, заменяя существующий текст.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-114">The following code creates a new string by replacing existing text with a substitute.</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#1)]

<span data-ttu-id="a6ac3-115">В коде выше демонстрируется *неизменяемое* свойство строк.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-115">The preceding code demonstrates this *immutable* property of strings.</span></span> <span data-ttu-id="a6ac3-116">В примере видно, что исходная строка `source` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-116">You can see in the preceding example that the original string, `source`, is not modified.</span></span> <span data-ttu-id="a6ac3-117">Метод <xref:System.String.Replace%2A?displayProperty=nameWithType> создает новый объект `string`, содержащий изменения.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-117">The <xref:System.String.Replace%2A?displayProperty=nameWithType> method creates a new `string` containing the modifications.</span></span>

<span data-ttu-id="a6ac3-118">Метод <xref:System.String.Replace%2A> может заменять строки или отдельные символы.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-118">The <xref:System.String.Replace%2A> method can replace either strings or single characters.</span></span> <span data-ttu-id="a6ac3-119">В обоих случаях заменяется каждое вхождение искомого текста.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-119">In both cases, every occurrence of the sought text is replaced.</span></span>  <span data-ttu-id="a6ac3-120">В следующем примере все символы ' ' заменяются на '\_':</span><span class="sxs-lookup"><span data-stu-id="a6ac3-120">The following example replaces all ' ' characters with '\_':</span></span>

[!code-csharp-interactive[replace characters](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#2)]

<span data-ttu-id="a6ac3-121">Исходная строка не изменяется. Возвращается новая строка с заменой.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-121">The source string is unchanged, and a new string is returned with the replacement.</span></span>

## <a name="trim-white-space"></a><span data-ttu-id="a6ac3-122">Усечение пробелов</span><span class="sxs-lookup"><span data-stu-id="a6ac3-122">Trim white space</span></span>

<span data-ttu-id="a6ac3-123">Используйте методы <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> и <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> для удаления всех начальных или конечных пробелов.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-123">You can use the <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType>, and <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> methods to remove any leading or trailing white space.</span></span>  <span data-ttu-id="a6ac3-124">В приведенном ниже коде показан пример каждого метода.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-124">The following code shows an example of each.</span></span> <span data-ttu-id="a6ac3-125">Исходная строка не изменяется. Эти методы возвращают новую строку с измененным содержимым.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-125">The source string does not change; these methods return a new string with the modified contents.</span></span>

[!code-csharp-interactive[trim white space](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#3)]

## <a name="remove-text"></a><span data-ttu-id="a6ac3-126">Удаление текста</span><span class="sxs-lookup"><span data-stu-id="a6ac3-126">Remove text</span></span>

<span data-ttu-id="a6ac3-127">Вы можете удалять из строки текст с помощью метода <xref:System.String.Remove%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-127">You can remove text from a string using the <xref:System.String.Remove%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a6ac3-128">Этот метод удаляет определенное число символов, начиная с указанного индекса.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-128">This method removes a number of characters starting at a specific index.</span></span> <span data-ttu-id="a6ac3-129">В следующем примере показано, как использовать <xref:System.String.IndexOf%2A?displayProperty=nameWithType> с <xref:System.String.Remove%2A> для удаления текста из строки:</span><span class="sxs-lookup"><span data-stu-id="a6ac3-129">The following example shows how to use <xref:System.String.IndexOf%2A?displayProperty=nameWithType> followed by <xref:System.String.Remove%2A> to remove text from a string:</span></span>

[!code-csharp-interactive[remove text](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#4)]

## <a name="replace-matching-patterns"></a><span data-ttu-id="a6ac3-130">Замена совпадающих шаблонов</span><span class="sxs-lookup"><span data-stu-id="a6ac3-130">Replace matching patterns</span></span>

<span data-ttu-id="a6ac3-131">Используйте [регулярные выражения](../../standard/base-types/regular-expressions.md) для замены текста, соответствующего шаблонам, на новый текст, который может быть определен шаблоном.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-131">You can use [regular expressions](../../standard/base-types/regular-expressions.md) to replace text matching patterns with new text, possibly defined by a pattern.</span></span> <span data-ttu-id="a6ac3-132">В следующем примере используется класс <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> для поиска шаблона в исходной строке и замены его с правильным регистром.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-132">The following example uses the <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class to find a pattern in a source string and replace it with proper capitalization.</span></span> <span data-ttu-id="a6ac3-133">Метод <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> принимает в качестве одного из аргументов функцию, которая предоставляет логику замены.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-133">The <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> method takes a function that provides the logic of the replacement as one of its arguments.</span></span> <span data-ttu-id="a6ac3-134">В примере эта функция (`LocalReplaceMatchCase`) является **локальной функцией** и объявляется внутри демонстрируемого метода.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-134">In this example, that function, `LocalReplaceMatchCase` is a **local function** declared inside the sample method.</span></span> <span data-ttu-id="a6ac3-135">`LocalReplaceMatchCase` использует класс <xref:System.Text.StringBuilder?displayProperty=nameWithType>, чтобы создать замещающую строку с правильным регистром.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-135">`LocalReplaceMatchCase` uses the <xref:System.Text.StringBuilder?displayProperty=nameWithType> class to build the replacement string with proper capitalization.</span></span>

<span data-ttu-id="a6ac3-136">Регулярные выражения наиболее эффективны при поиске и замене текста, который соответствует шаблону, а не известного текста.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-136">Regular expressions are most useful for searching and replacing text that follows a pattern, rather than known text.</span></span> <span data-ttu-id="a6ac3-137">Дополнительные сведения см. в статье [Практическое руководство. Поиск по строкам](search-strings.md).</span><span class="sxs-lookup"><span data-stu-id="a6ac3-137">See [How to: search strings](search-strings.md) for more details.</span></span> <span data-ttu-id="a6ac3-138">Шаблон поиска "the\s" ищет слово "the", за которым следует пробел.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-138">The search pattern, "the\s" searches for the word "the" followed by a white-space character.</span></span> <span data-ttu-id="a6ac3-139">Эта часть шаблона гарантирует пропуск слова "there" в исходной строке.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-139">That part of the pattern ensures that it doesn't match "there" in the source string.</span></span> <span data-ttu-id="a6ac3-140">Дополнительные сведения об элементах языка регулярных выражений см. в разделе [Элементы языка регулярных выражений — краткий справочник](../../standard/base-types/regular-expression-language-quick-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a6ac3-140">For more information on regular expression language elements, see [Regular Expression Language - Quick Reference](../../standard/base-types/regular-expression-language-quick-reference.md).</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#5)]

<span data-ttu-id="a6ac3-141">Метод <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> возвращает неизменяемую строку с содержимым в объекте <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-141">The <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method returns an immutable string with the contents in the <xref:System.Text.StringBuilder> object.</span></span>

## <a name="modifying-individual-characters"></a><span data-ttu-id="a6ac3-142">Изменение отдельных символов</span><span class="sxs-lookup"><span data-stu-id="a6ac3-142">Modifying individual characters</span></span>

<span data-ttu-id="a6ac3-143">Вы можете создать из строки массив символов, изменить содержимое массива, а затем создать из измененного содержимого новую строку.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-143">You can produce a character array from a string, modify the contents of the array, and then create a new string from the modified contents of the array.</span></span>

<span data-ttu-id="a6ac3-144">В примере ниже показано, как заменить набор символов в строке.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-144">The following example shows how to replace a set of characters in a string.</span></span> <span data-ttu-id="a6ac3-145">Сначала используется метод <xref:System.String.ToCharArray?displayProperty=nameWithName> для создания массива символов.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-145">First, it uses the <xref:System.String.ToCharArray?displayProperty=nameWithName> method to create an array of characters.</span></span> <span data-ttu-id="a6ac3-146">Для поиска начального индекса слова "fox" используется метод <xref:System.String.IndexOf%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-146">It uses the <xref:System.String.IndexOf%2A> method to find the starting index of the word "fox."</span></span> <span data-ttu-id="a6ac3-147">Следующие три символа заменяются другим словом.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-147">The next three characters are replaced with a different word.</span></span> <span data-ttu-id="a6ac3-148">Наконец, из обновленного массива символов создается новая строка.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-148">Finally, a new string is constructed from the updated character array.</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#6)]

## <a name="unsafe-modifications-to-string"></a><span data-ttu-id="a6ac3-149">Небезопасные изменения в строке</span><span class="sxs-lookup"><span data-stu-id="a6ac3-149">Unsafe modifications to string</span></span>

<span data-ttu-id="a6ac3-150">**Небезопасный** код позволяет изменить строку непосредственно ("на месте") после ее создания.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-150">Using **unsafe** code, you can modify a string "in place" after it has been created.</span></span> <span data-ttu-id="a6ac3-151">Такой код обходит многие функции .NET, призванные свести к минимуму определенные типы ошибок в коде.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-151">Unsafe code bypasses many of the features of .NET designed to minimize certain types of bugs in code.</span></span> <span data-ttu-id="a6ac3-152">Для изменения строки на месте приходится использовать небезопасный код, так как класс строк имеет **неизменяемый** тип.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-152">You need to use unsafe code to modify a string in place because the string class is designed as an **immutable** type.</span></span> <span data-ttu-id="a6ac3-153">После создания объекта такого класса его значение не меняется.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-153">Once it has been created, its value does not change.</span></span> <span data-ttu-id="a6ac3-154">Небезопасный код позволяет обойти это свойство. Он обращается к памяти, используемой объектом `string`, и изменяет ее без применения обычных методов `string`.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-154">Unsafe code circumvents this property by accessing and modifying the memory used by a `string` without using normal `string` methods.</span></span>
<span data-ttu-id="a6ac3-155">Следующий пример приводится для тех редких случаев, когда вы хотите непосредственно изменить строку с помощью небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-155">The following example is provided for those rare situations where you want to modify a string in-place using unsafe code.</span></span> <span data-ttu-id="a6ac3-156">Этот пример демонстрирует применение ключевого слова `fixed`.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-156">The example shows how to use the `fixed` keyword.</span></span> <span data-ttu-id="a6ac3-157">Ключевое слово `fixed` не позволяет сборщику мусора перемещать в памяти строковый объект, когда код обращается к памяти с помощью небезопасного указателя.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-157">The `fixed` keyword prevents the garbage collector (GC) from moving the string object in memory while code accesses the memory using the unsafe pointer.</span></span> <span data-ttu-id="a6ac3-158">Также здесь показан один из возможных побочных эффектов, связанных с выполнением небезопасных операций со строками, причиной которого является интернирование (внутреннее сохранение) строк компилятором C#.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-158">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="a6ac3-159">В общем случае этот способ следует использовать только при крайней необходимости.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-159">In general, you shouldn't use this technique unless it is absolutely necessary.</span></span> <span data-ttu-id="a6ac3-160">Дополнительные сведения см. в статьях о [небезопасных](../language-reference/keywords/unsafe.md) и [фиксированных](../language-reference/keywords/fixed-statement.md) элементах.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-160">You can learn more in the articles on [unsafe](../language-reference/keywords/unsafe.md) and [fixed](../language-reference/keywords/fixed-statement.md).</span></span> <span data-ttu-id="a6ac3-161">Справочник по API для <xref:System.String.Intern%2A> включает сведения об интернировании строк.</span><span class="sxs-lookup"><span data-stu-id="a6ac3-161">The API reference for <xref:System.String.Intern%2A> includes inforamtion on string interning.</span></span>

[!code-csharp-interactive[unsafe ways to create a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#7)]

<span data-ttu-id="a6ac3-162">Вы можете оценить эти примеры, просмотрев код в нашем [репозитории GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="a6ac3-162">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="a6ac3-163">Или можете загрузить образцы [в ZIP-файле](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="a6ac3-163">Or you can download the samples [as a zip file](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6ac3-164">См. также</span><span class="sxs-lookup"><span data-stu-id="a6ac3-164">See also</span></span>

[<span data-ttu-id="a6ac3-165">Регулярные выражения в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6ac3-165">.NET Framework Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)  
 [<span data-ttu-id="a6ac3-166">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="a6ac3-166">Regular Expression Language - Quick Reference</span></span>](../../standard/base-types/regular-expression-language-quick-reference.md)  