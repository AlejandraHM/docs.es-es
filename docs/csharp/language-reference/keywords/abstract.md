---
title: 'abstract: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 325be8851b63a252c381d943943937332ec91e6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638046"
---
# <a name="abstract-c-reference"></a>abstract (Referencia de C#)
El modificador `abstract` indica que lo que se modifica carece de implementación o tiene una implementación incompleta. El modificador abstract puede usarse con clases, métodos, propiedades, indexadores y eventos. Use el modificador `abstract` en una declaración de clase para indicar que una clase solo está diseñada como clase base de otras clases. Los miembros marcados como abstractos o incluidos en una clase abstracta, deben implementarse con clases que deriven de la clase abstracta.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `Square` debe proporcionar una implementación de `Area` porque se deriva de `ShapesClass`:  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 Las clases abstractas tienen las siguientes características:  
  
-   No se pueden crear instancias de una clase abstracta.  
  
-   Una clase abstracta puede contener descriptores de acceso y métodos abstractos.  
  
-   No es posible modificar una clase abstracta con el modificador [sealed](../../../csharp/language-reference/keywords/sealed.md) porque los dos modificadores tienen significados opuestos. El modificador `sealed` impide que una clase se herede y el modificador `abstract` requiere que una clase se herede.  
  
-   Una clase no abstracta que derive de una clase abstracta debe incluir implementaciones reales de todos los descriptores de acceso y métodos abstractos heredados.  
  
 Use el modificador `abstract` en una declaración de método o de propiedad para indicar que el método o la propiedad no contienen implementación.  
  
 Los métodos abstractos tienen las siguientes características:  
  
-   Un método abstracto es, implícitamente, un método virtual.  
  
-   Solo se permiten declaraciones de métodos abstractos en clases abstractas.  
  
-   Dado que una declaración de método abstracto no proporciona una implementación real, no hay ningún cuerpo de método; la declaración de método finaliza simplemente con un punto y coma y no hay llaves ({ }) después de la firma. Por ejemplo:  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     La implementación la proporciona un método, [override](../../../csharp/language-reference/keywords/override.md), que es miembro de una clase no abstracta.  
  
-   Es un error usar los modificadores [static](../../../csharp/language-reference/keywords/static.md) o [virtual](../../../csharp/language-reference/keywords/virtual.md) en una declaración de método abstracto.  
  
 Las propiedades abstractas se comportan como métodos abstractos, salvo por las diferencias en la sintaxis de declaración e invocación.  
  
-   Es un error usar el modificador `abstract` en una propiedad estática.  
  
-   Una propiedad abstracta heredada se puede invalidar en una clase derivada incluyendo una declaración de propiedad que use el modificador [override](../../../csharp/language-reference/keywords/override.md).  
  
 Para obtener más información sobre las clases abstractas, vea [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) (Clases y miembros de clase abstractos y sellados [Guía de programación de C#]).  
  
 Una clase abstracta debe proporcionar implementación para todos los miembros de interfaz.  
  
 Una clase abstracta que implemente una interfaz podría asignar los métodos de interfaz a métodos abstractos. Por ejemplo:  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `DerivedClass` se deriva de una clase abstracta `BaseClass`. La clase abstracta contiene un método abstracto, `AbstractMethod`, y dos propiedades abstractas, `X` y `Y`.  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 En el ejemplo anterior, si intenta crear una instancia de la clase abstracta mediante una instrucción como esta:  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
Se mostrará un mensaje de error en el que se indica que el compilador no puede crear una instancia de la clase abstracta "BaseClass".  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)
- [virtual](../../../csharp/language-reference/keywords/virtual.md)
- [override](../../../csharp/language-reference/keywords/override.md)
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
