---
title: "Data class inheritance (O-R Designer)"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
caps.latest.revision: 3
ms.author: "mblome"
manager: "ghogen"
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
# Data class inheritance (O/R Designer)
Like other objects, [!INCLUDE[vbtecdlinq](../datatools/includes/vbtecdlinq_md.md)] classes can use inheritance and be derived from other classes. In code, you can specify inheritance relationships between objects by declaring that one class inherits from another. In a database, inheritance relationships are created in several ways. The [!INCLUDE[vs_ordesigner_long](../datatools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../datatools/includes/vs_ordesigner_short_md.md)]) supports the concept of single-table inheritance as it is often implemented in relational systems.  
  
 In single-table inheritance, there is a single database table that contains columns for both base and derived classes. With relational data, a discriminator column contains the value that determines which class any given record belongs to. For example, consider a Persons table that contains everyone employed by a company. Some people are employees and some people are managers. The Persons table contains a column named Type that has a value of 1 for managers and a value of 2 for employees. The Type column is the discriminator column. In this scenario, you can create a subclass of employees and populate the class with only records that have a Type value of 2.  
  
 When you configure inheritance in entity classes by using the [!INCLUDE[vs_ordesigner_short](../datatools/includes/vs_ordesigner_short_md.md)], drag the single table that contains the inheritance data onto the designer two times: one time for each class in the inheritance hierarchy. After you add the tables to the designer, connect them with an Inheritance item from the **Object Relational Designer** toolbox and then set the four inheritance properties in the **Properties** window.  
  
## Inheritance Properties  
 The following table lists the inheritance properties and their descriptions:  
  
|Property|Description|  
|--------------|-----------------|  
|Discriminator Property|The property (mapped to the column) that determines which class the current record belongs to.|  
|Base Class Discriminator Value|The value (in the column designated as the Discriminator Property) that determines that a record is of the base class.|  
|Derived Class Discriminator Value|The value (in the property designated as the Discriminator Property) that determines that a record is of the derived class.|  
|Inheritance Default|The class that should be populated when the value in the property designated as the **Discriminator Property** does not match either the **Base Class Discriminator Value** or the **Derived Class Discriminator Value**.|  
  
 Creating an object model that uses inheritance and corresponds to relational data can be somewhat confusing. This topic provides information about the basic concepts and individual properties that are required for configuring inheritance. The following topics provide a clearer explanation of how to configure inheritance with the [!INCLUDE[vs_ordesigner_short](../datatools/includes/vs_ordesigner_short_md.md)].  
  
|Topic|Description|  
|-----------|-----------------|  
|[How to: Configure inheritance by using the O/R Designer](../datatools/how-to--configure-inheritance-by-using-the-o-r-designer.md)|Describes how to configure entity classes that use single-table inheritance by using the [!INCLUDE[vs_ordesigner_short](../datatools/includes/vs_ordesigner_short_md.md)].|  
|[Walkthrough: Creating LINQ to SQL Classes by Using Single-Table Inheritance (O/R Designer)](../datatools/walkthrough--creating-linq-to-sql-classes-by-using-single-table-inheritance--o-r-designer-.md)|Provides step-by-step instructions about how to configure entity classes that use single-table inheritance by using the [!INCLUDE[vs_ordesigner_short](../datatools/includes/vs_ordesigner_short_md.md)].|  
  
## See Also  
 [LINQ to SQL Tools in Visual Studio](../datatools/linq-to-sql-tools-in-visual-studio2.md)   
 [Walkthrough: Creating LINQ to SQL Classes (O-R Designer)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [Walkthrough: Creating LINQ to SQL Classes by Using Single-Table Inheritance (O/R Designer)](../datatools/walkthrough--creating-linq-to-sql-classes-by-using-single-table-inheritance--o-r-designer-.md)   
 [Getting Started](../Topic/Getting%20Started.md)