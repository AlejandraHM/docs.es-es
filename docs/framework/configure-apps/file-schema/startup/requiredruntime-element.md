---
title: <requiredRuntime> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 5e528a8b81fa3d9abc4f345d18f01e33f483a4a9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254735"
---
# <a name="requiredruntime-element"></a>\<requiredRuntime > elemento

Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Este elemento está en desuso y ya no se debe usar. El [ `supportedRuntime` ](supportedruntime-element.md) elemento debe usarse en su lugar.

\<Configuración > \<Inicio > \<requiredRuntime >

## <a name="syntax"></a>Sintaxis

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`version`|Atributo opcional.<br /><br /> Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación. El valor de cadena debe coincidir con el nombre del directorio se encuentra en la raíz de instalación de .NET Framework. No se puede analizar el contenido del valor de cadena.|
|`safemode`|Atributo opcional.<br /><br /> Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión en tiempo de ejecución.|

## <a name="safemode-attribute"></a>atributo safemode

|Valor|Descripción|
|-----------|-----------------|
|`false`|El código de inicio en tiempo de ejecución busca en el registro. Este es el valor predeterminado.|
|`true`|El código de inicio en tiempo de ejecución no busca en el registro.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`startup`|Contiene el `<requiredRuntime>` elemento.|

## <a name="remarks"></a>Comentarios
 Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la `<requiredRuntime>` elemento. Las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución deben usar la `<supportedRuntime>` elemento.

> [!NOTE]
> Si usas el [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) función para especificar el archivo de configuración, debe usar el `<requiredRuntime>` (elemento) para todas las versiones del tiempo de ejecución. El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 El `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada de .NET Framework. No se interpreta esta cadena. Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no está cargado; el código de inicio muestra un mensaje de error y se cierra.

> [!NOTE]
> El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de inicio](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)