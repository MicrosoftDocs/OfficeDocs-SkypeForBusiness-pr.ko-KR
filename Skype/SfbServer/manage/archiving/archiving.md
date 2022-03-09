---
title: 보관 관리 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '요약: 보관에 대한 보관을 관리하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 0849a9fbc3db95579a1711e2934b0bafdc7b6e23
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392660"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>보관 관리 비즈니스용 Skype 서버

**요약:** 보관에 대한 보관을 관리하는 방법을 비즈니스용 Skype 서버.
  
조직에 대한 보관을 배포할 때 배포 중에 초기 구성을 지정합니다. 그러나 매일 관리에 대한 보관 지원을 구현하거나 조직의 새로운 요구 사항을 충족하는 방법을 변경하려는 경우도 있습니다. 예를 들어 조직 내의 특정 사이트, 특정 풀 또는 특정 사용자에 대해 보관 지원을 다르게 설정해야 할 수 있습니다. 이 비즈니스용 Skype 서버 보관 구성 옵션 및 사용자 정책을 만들고 사용자 지정하면 됩니다. 
  
이 항목을 읽기 전에 Plan [for archiving in 비즈니스용 Skype 서버](../../plan-your-deployment/archiving/archiving.md) [및 Deploy archiving for 비즈니스용 Skype 서버](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> 배포에 대해 Microsoft Exchange 통합을 사용하도록 설정하면 Exchange 정책은 Exchange 사서함을 보류로 설정한 사용자에 대해 보관을 사용할지 여부를 In-Place 제어합니다. 자세한 내용은 [Plan for archiving in 비즈니스용 Skype 서버](../../plan-your-deployment/archiving/archiving.md) [and Configure integration with Exchange storage for 비즈니스용 Skype 서버](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>보관 구성 옵션

보관 구성 옵션은 다음을 할지 여부를 지정합니다.
  
- 보관을 활성화 또는 비활성화
    
- IM 세션 보관
    
- 웹 회의 세션 보관
    
- 보관을 사용할 수 없는 경우 활동 차단
    
- 통합 Exchange 사용
    
- 데이터 제거 및 내보내기 설정
    
이러한 옵션은 전역, 사이트 또는 풀 수준에서 설정할 수 있습니다. 자세한 내용은 [Manage archiving options in 비즈니스용 Skype 서버](options.md).
  
## <a name="archiving-policies"></a>보관 정책

보관 정책에 따라 다음을 보관할지 여부가 결정됩니다.
  
- 내부 통신
    
- 외부 통신
    
이러한 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다. 자세한 내용은 [Manage archiving policies in 비즈니스용 Skype 서버](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>제어판을 사용하여 또는 제어판을 사용하여 Windows PowerShell

제어판을 사용하여 또는 제어판을 사용하여 보관을 관리할 Windows PowerShell. 다음 표에서는 보관을 관리하는 데 사용할 수 있는 cmdlet을 요약하여 제공합니다. 사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 비즈니스용 Skype 서버 [관리 셸을 참조합니다](../management-shell.md). 


|**Cmdlet**|**설명**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |보관 데이터베이스에 저장된 레코드를 비즈니스용 Skype 서버 내보낼 수 있습니다.  <br/> |
|Get-CsArchivingConfiguration  <br/> |조직의 보관 구성 설정에 대한 정보를 반환합니다.  <br/> |
|Get-CsArchivingPolicy  <br/> |내부 및 외부 통신에 대한 조직의 보관 정책에 대한 정보를 반환합니다.  <br/> |
|Grant-CsArchivingPolicy  <br/> |사용자 또는 사용자 집합에 IM(인스턴트 메시징) 세션 보관 정책을 할당합니다. 이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |보관 데이터베이스에서 레코드를 수동으로 제거합니다.  <br/> |
|New-CsArchivingConfiguration  <br/> |메신저 세션 자동 저장을 사용하도록 설정하거나 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 차단하는 데 사용할 수 있는 새 IM(인스턴트 메시징) 설정 집합을 만듭니다.  <br/> |
|New-CsArchivingPolicy  <br/> |새 IM(인스턴트 메시징) 세션 보관 정책을 만듭니다. 이러한 정책은 내부 사용자 간에 발생하는 모든 메신저 대화 세션을 보관하고 내부 사용자와 외부 파트너 간에 발생하는 모든 메신저 대화 세션을 보관하는 기능을 제공합니다.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |IM(인스턴트 메시징) 세션의 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 선택적으로 차단하는 데 사용되는 보관 설정의 지정된 컬렉션을 제거합니다.  <br/> |
|Remove-CsArchivingPolicy  <br/> |내부 사용자 간에 수행되는 모든 메신저 비즈니스용 Skype 서버 및/또는 내부 사용자와 페더링 파트너 간의 모든 메신저 세션을 자동으로 저장할지 여부를 결정하는 지정된 IM(인스턴트 메시징) 보관 정책을 제거합니다.  <br/> |
|Set-CsArchivingConfiguration  <br/> |IM(인스턴트 메시징) 보관 구성 옵션의 기존 컬렉션을 수정합니다.  <br/> |
|Set-CsArchivingPolicy  <br/> |기존 메신저 대화 보관 정책을 수정합니다. 보관 정책을 사용하면 내부 사용자 간에 수행되는 모든 메신저 대화 세션과 전화 회의를 보관하는 기능을 사용할 수 있고, 내부 사용자와 페더레이션 파트너 간에 수행되는 세션을 보관할 수 있습니다.  <br/> |
|Set-CsArchivingServer  <br/> |하나 이상의 보관 서버에 대한 새 데이터베이스 위치를 지정할 수 있습니다.  <br/> |
   

