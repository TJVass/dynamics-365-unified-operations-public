---
# required metadata

title: Attributes that make methods extensible
description: This topic provides information about attributes that make methods extensible.
author: mfp
manager: AnnBe
ms.date: 09/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 


# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Developer
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: Operations
# ms.tgt_pltfrm: 
ms.custom: 268724
ms.assetid: 
ms.search.region: Global
# ms.search.industry: 
ms.author: mfp
ms.search.validFrom: 2018-09-09
ms.dyn365.ops.version: Platform update 20
---

# Attributes that make methods extensible

This topic describes the various attributes that can be used to control extensibility capabilities for methods.

The following table provides an overview of the default support for extensibility on methods.

|   | Hookable | Wrappable | Replaceable |
|---|----------|-----------|-------------|
| **Protected** | Yes | Yes | No |
| **Public** | Yes | Yes | No |

> [!NOTE]
> Private methods are not extensible.

## Hookable
If a method is hookable, extenders can subscribe to pre-events and post-events.

For protected and public methods, you can opt out by adding **\[Hookable(false)\]** to the method.

You can't opt in for private methods.

### Best practices when you write code
When a method is hookable, the compiler generates extra intermediate language (IL) code to enable the method as an extension point. Although the extra code has performance overhead, this overhead is negligible in most cases. However, for performance-critical methods, consider marking the method as non-hookable.

## Wrappable
If a method is wrappable, extenders can wrap it by using Chain of Command (CoC). Extenders must call next, because they aren't allowed to break the CoC.

To be wrappable, a method must also be hookable. Therefore, methods that are wrappable are hookable.

For protected and public methods, you can opt out by adding **\[Wrappable(false)\]** to the method.

You can't opt in for private methods.

### Best practices when you write code
CoC resembles inheritance in many ways. Typically, if you want other people to be able to call your method but not change it, you mark the method as final. Consider marking these methods as non-wrappable or non-hookable.

## Replaceable 
If a method is replaceable, extenders can wrap it by using CoC, but they don't have to unconditionally call next. Although extenders can break the CoC, the expectation is that they will only conditionally break it. The compiler doesn't enforce calls to next.

To be replaceable, a method must also be wrappable.

For wrappable methods, you can opt in by adding **\[Replaceable\]** to the method.

### Best practices when you write code
When a method is replaceable, it can be extended by using CoC, and the execution of next can be skipped. Before you enable a method to be replaceable, you should thoroughly assess the functional impact if an extender skips the execution of the method.
			
+ **Do** make sure that methods that have **\[Replaceable\]** have XML documentation that describes the responsibility of the method.
+ **Don't** use **\[Replaceable\]** to let consumers skip the replaced logic and do nothing.
+ **Don't** use **\[Replaceable\]** for factory methods when **SysExtension** can be used instead.
+ **Avoid** using **\[Replaceable\]** when the method changes databases or class state.
+ **Avoid** using **\[Replaceable\]** if the method performs multiple operations and has multiple responsibilities. Instead, refactor the method into separate methods, each of which has a single responsibility, and consider which methods should actually be replaceable.
+ **Consider** using **\[Replaceable\]** to solve transformations. 

    **Example:** Enum conversion that uses a switch statement over enum values, where the default block has a throw.

+ **Consider** using **\[Replaceable\]** to override lookups and jumprefs.
 
### Best practices for extenders
+ **Don't** write logic that has a different responsibility than the logic that is being replaced.
+ **Do** call the base functionality (call next) when the replacement logic doesn't apply.
+ **Avoid** replacing logic completely by not calling the base functionality (call next).

## Using the attributes in conjunction with each other

The general rule is that \[Hookable\] is required by \[Wrappable\], which is required by \[Replaceable\]. The following table outlines the dependencies.

|   | Hookable | Wrappable | Replaceable |
|---|----------|-----------|-------------|
| **\[Hookable(true)\]** | Yes | No | No |
| **\[Hookable(false)\]** |	No | No | No |
| **\[Wrappable(true)\]** |	Yes | Yes |	No |
| **\[Wrappable(false)\]** | Maybe, depending on whether the method is hookable (see the table earlier in this topic) | No | No |
| **\[Replaceable(true)\]** | Yes | Yes | Yes |
| **\[Replaceable(false)\]** | Maybe, depending on whether the method is hookable (see the table earlier in this topic) | Maybe, depending on whether the method is wrappable (see the table earlier in this topic) | No |
