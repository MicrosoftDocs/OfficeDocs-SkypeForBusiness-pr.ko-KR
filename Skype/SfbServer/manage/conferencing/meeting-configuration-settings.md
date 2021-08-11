---
title: 모임 구성 설정 관리 비즈니스용 Skype 서버
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '요약: 이 문서에서 모임 구성 설정을 관리하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 9bd0cefb32074f6e11d524e65096fa0999db4ae35b5244c202616d76ded81085
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321680"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>모임 구성 설정 관리 비즈니스용 Skype 서버
 
**요약:** 모임 구성 설정을 관리하는 방법을 비즈니스용 Skype 서버.
  
이 항목에서는 모임 구성 설정을 관리하는 방법에 대해 설명합니다. 회의를 계획하고 배포하는 방법에 대한 자세한 내용은 [Plan for conferencing in 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in 비즈니스용 Skype 서버.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
모임 구성 설정은 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가하는 방법을 제어하는 것 외에도 사용자가 만들 수 있는 모임 유형을 제어합니다. 이러한 설정은 예약된 모임에만 영향을 미치게 됩니다. 모임 시작 옵션을 클릭하여 만든 ad-hoc 모임에는 영향을 주지 비즈니스용 Skype.
  
모임 구성 설정은 다음을 정의합니다.
  
- 공중 전화망(PSTN)에서 전화 접속하는 사용자가 대기실로 이동하는지 여부
    
- 발표자로 지정될 수 있는 사용자
    
- 회의 유형이 기본적으로 지정되는지 여부
    
- 인증되지 않은 익명 사용자가 기본적으로 허용되는지 여부
    
회의 제어판을 사용하여 모임의 특성을 정의하거나 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다. 
  
모임 설정은 전역 수준(기본적으로 생성), 사이트 수준 또는 풀 수준에서 지정할 수 있습니다. 기본적으로 전역 설정은 모임 환경을 정의합니다. 풀 수준 설정을 만들면 설정이 해당 풀에서 호스팅된 모든 모임에 적용됩니다. 풀 수준 설정을 만들지 않으면 사이트 수준 설정이 적용됩니다(있는 경우). 사이트 수준 설정을 정의하지 않으면 전역 설정이 모든 모임에 적용됩니다.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 모임 비즈니스용 Skype 서버 관리

제어판을 사용하여 모임 설정을 비즈니스용 Skype 서버:
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 모임 비즈니스용 Skype 서버 관리

관리 셸을 사용하여 비즈니스용 Skype 서버 관리하기 위해 다음 cmdlet을 사용 합니다.
  
**모임 구성 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정에 대한 정보를 반환합니다.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |사이트 또는 서비스 범위에서 새 전화 회의 구성 컬렉션을 만듭니다.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |모임 구성 설정의 기존 컬렉션을 삭제합니다.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정을 수정합니다.  <br/> |
