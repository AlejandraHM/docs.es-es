---
title: ICorDebugHeapValue (Interfaz1)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a87790647ed8896f072aa8e943e31fa1980e3f62
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622863"
---
# <a name="icordebugheapvalue-interface1"></a>ICorDebugHeapValue (Interfaz1)
Una subclase de "ICorDebugValue" que representa un objeto que se han recopilado por el recolector de elementos no utilizados de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateRelocBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|Sin implementar.|  
|[IsValid (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|Obtiene un valor que indica si el objeto representado por este `ICorDebugHeapValue` es válido o ha sido reclamado por el recolector de elementos no utilizados. Este método está desusado en .NET Framework versión 2.0.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también



- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
