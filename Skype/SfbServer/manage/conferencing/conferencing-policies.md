---
title: 비즈니스용 Skype 서버에서 회의 정책 관리
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835278"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 관리
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 관리하는 방법에 대해 자세히 알아보습니다.
  
이 항목에서는 회의 정책을 관리하는 방법에 대해 설명합니다. 회의를 계획 및 배포하는 방법에 대한 자세한 내용은 비즈니스용 [Skype](../../plan-your-deployment/conferencing/conferencing.md) 서버에서 회의 계획 및 비즈니스용 Skype 서버에서 회의 배포를 [참조하세요.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
회의 정책을 사용하면 모임에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 참가할 수 있는 최대 사용자 수에 이르기까지 다양한 예정 및 참가 옵션을 정의할 수 있습니다. 회의 정책을 사용하여 모임의 보안, 대역폭 및 법적 측면을 관리할 수 있습니다.
  
회의 정책은 전역 범위, 사이트 범위 및 사용자 범위의 세 가지 수준에서 정의할 수 있습니다. 설정은 가장 좁은 범위에서 가장 넓은 범위순으로 특정 사용자에게 적용됩니다. 사용자에게 정책을 할당하는 경우 해당 설정이 우선합니다. 사용자 정책을 할당하지 않으면 사이트 설정이 적용됩니다. 사용자 정책이나 사이트 정책을 적용하지 않는 경우에는 글로벌 정책에서 기본 설정을 제공합니다.
  
글로벌 정책은 기본적으로 있으므로 새 글로벌 정책을 만들 수는 없습니다. 또한 기존 글로벌 정책을 삭제할 수도 없지만, 기존 글로벌 정책을 변경하여 기본 설정을 사용자 지정할 수는 있습니다.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 관리

비즈니스용 Skype 서버 제어판을 사용하여 회의 정책을 관리합니다.
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의를 클릭한 다음 회의 **정책을 클릭합니다.**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 관리

비즈니스용 Skype 서버 관리 셸을 사용하여 모임을 관리하기 위해 다음 cmdlet을 사용하세요.
  
**회의 정책 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |조직에서 사용하도록 구성된 회의 정책에 대한 정보를 반환합니다.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |사용자별 범위에서 전화 회의 정책을 할당합니다.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |조직에서 사용할 새 회의 정책을 만듭니다.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |지정한 회의 정책을 제거합니다.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |기존 회의 정책을 수정합니다.  <br/> |
   

