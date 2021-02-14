---
title: 비즈니스용 Skype 서버에서 보관 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '요약: 비즈니스용 Skype 서버의 보관을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817738"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 관리

**요약:** 비즈니스용 Skype 서버의 보관을 관리하는 방법을 자세히 알아보고,
  
조직에 대한 보관을 배포할 때 배포 중에 초기 구성을 지정합니다. 그러나 매일 관리 또는 조직의 새로운 요구 사항을 충족하기 위해 보관 지원을 구현하는 방법을 변경하려는 경우도 있습니다. 예를 들어 조직 내의 특정 사이트, 특정 풀 또는 특정 사용자에 대해 보관 지원을 다르게 설정해야 할 수 있습니다. 비즈니스용 Skype 서버에 있는 사용자의 경우 보관 구성 옵션 및 사용자 정책을 만들고 사용자 지정하여 이 작업을 실행합니다. 
  
이 항목을 읽기 전에 비즈니스용 Skype 서버의 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 보관 배포의 정보에 익숙해야 [합니다.](../../deploy/deploy-archiving/deploy-archiving.md)
  
> [!NOTE]
> 배포에 대해 Microsoft Exchange 통합을 사용하도록 설정하는 경우 Exchange 정책은 Exchange에 있으며 사서함이 보류된 사용자에 대해 보관을 사용할지 여부를 In-Place 제어합니다. 자세한 내용은 비즈니스용 Skype 서버에서 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 Exchange 저장소와의 통합 [구성을 참조하세요.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="archiving-configuration-options"></a>보관 구성 옵션

보관 구성 옵션은 다음을 할지 여부를 지정합니다.
  
- 보관을 활성화 또는 비활성화
    
- IM 세션 보관
    
- 웹 회의 세션 보관
    
- 보관을 사용할 수 없는 경우 활동 차단
    
- Exchange 통합 사용
    
- 데이터 제거 및 내보내기 설정
    
이러한 옵션은 전역, 사이트 또는 풀 수준에서 설정할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버에서 보관 옵션 [관리를 참조하세요.](options.md)
  
## <a name="archiving-policies"></a>보관 정책

보관 정책에 따라 다음을 보관할지 여부가 결정됩니다.
  
- 내부 통신
    
- 외부 통신
    
이러한 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버에서 보관 정책 [관리를 참조하세요.](policies.md)
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>제어판을 사용하여 또는 제어판을 사용하여 보관을 Windows PowerShell

제어판을 사용하여 또는 보관을 사용하여 보관을 관리할 Windows PowerShell. 다음 표에서는 보관을 관리하는 데 사용할 수 있는 cmdlet을 요약하여 제공합니다. 사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../management-shell.md) 


|**Cmdlet**|**설명**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |비즈니스용 Skype 서버 보관 데이터베이스에 저장된 레코드를 내보낼 수 있습니다.  <br/> |
|Get-CsArchivingConfiguration  <br/> |조직의 보관 구성 설정에 대한 정보를 반환합니다.  <br/> |
|Get-CsArchivingPolicy  <br/> |내부 및 외부 통신에 대한 조직의 보관 정책에 대한 정보를 반환합니다.  <br/> |
|Grant-CsArchivingPolicy  <br/> |사용자 또는 사용자 집합에 IM(인스턴트 메시징) 세션 보관 정책을 할당합니다. 이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |보관 데이터베이스에서 레코드를 수동으로 제거합니다.  <br/> |
|New-CsArchivingConfiguration  <br/> |메신저 세션 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 차단하는 데 사용할 수 있는 새 IM(인스턴트 메시징) 설정 집합을 만듭니다.  <br/> |
|New-CsArchivingPolicy  <br/> |새 IM(인스턴트 메시징) 세션 보관 정책을 만듭니다. 이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |IM(인스턴트 메시징) 세션의 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 선택적으로 차단하는 데 사용되는 보관 설정의 지정된 컬렉션을 제거합니다.  <br/> |
|Remove-CsArchivingPolicy  <br/> |비즈니스용 Skype 서버에서 내부 사용자 간에 수행되는 모든 메신저 세션 및/또는 내부 사용자와 페더링 파트너 간의 모든 메신저 세션을 자동으로 저장할지 여부를 결정하는 지정된 IM(인스턴트 메시징) 보관 정책을 제거합니다.  <br/> |
|Set-CsArchivingConfiguration  <br/> |IM(인스턴트 메시징) 보관 구성 옵션의 기존 컬렉션을 수정합니다.  <br/> |
|Set-CsArchivingPolicy  <br/> |기존 메신저 대화 보관 정책을 수정합니다. 보관 정책을 사용하면 내부 사용자 간에 수행되는 모든 메신저 대화 세션과 전화 회의를 보관하는 기능을 사용할 수 있고, 내부 사용자와 페더레이션 파트너 간에 수행되는 세션을 보관할 수 있습니다.  <br/> |
|Set-CsArchivingServer  <br/> |하나 이상의 보관 서버에 대한 새 데이터베이스 위치를 지정할 수 있습니다.  <br/> |
   

