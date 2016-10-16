---
title: "Compiler Error CS0313"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0313"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0313"
ms.assetid: a0b0f2fb-e742-4df8-98bd-3bc068f0c71c
caps.latest.revision: 8
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Compiler Error CS0313
The type 'type1' cannot be used as type parameter 'parameter name' in the generic type or method 'type2'. The nullable type 'type1' does not satisfy the constraint of 'type2'. Nullable types cannot satisfy any interface constraints.  
  
 A nullable type is not equivalent to its non-nullable counterpart. In the example that follows, `ImplStruct` satisfies the `BaseInterface` constraint but `ImplStruct?` does not because `Nullable<ImplStruct>` does not implement `BaseInterface`.  
  
### To correct this error  
  
1.  Using the code that follows as an example, one solution is to specify an ordinary `ImplStruct` as the first type argument in the call to `TestMethod`. Then modify `TestMethod` to create a nullable version of `Implstruct` in its return statement:  
  
    ```  
    return new Nullable<T>(t);  
    ```  
  
## Example  
 The following code generates CS0313:  
  
```  
// cs0313.cs  
public interface BaseInterface { }  
public struct ImplStruct : BaseInterface { }  
  
public class TestClass  
{  
    public T? TestMethod<T, U>(T t) where T : struct, U  
    {  
        return t;  
    }  
}  
  
public class NullableTest  
{  
    public static void Run()  
    {  
  
        TestClass tc = new TestClass();  
        tc.TestMethod<ImplStruct?, BaseInterface>(new ImplStruct?()); // CS0313  
    }  
    public static void Main()  
    { }  
}  
```  
  
## See Also  
 [Nullable Types](../Topic/Nullable%20Types%20\(C%23%20Programming%20Guide\).md)