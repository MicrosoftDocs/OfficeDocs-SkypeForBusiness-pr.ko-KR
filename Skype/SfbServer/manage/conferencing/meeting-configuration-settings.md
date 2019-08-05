---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189651"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 관리
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 관리 하는 방법에 대해 알아봅니다.
  
이 항목에서는 모임 구성 설정을 관리 하는 방법에 대해 설명 합니다. 회의를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md) 및 비즈니스용 [skype 서버에서 회의 배포](../../deploy/deploy-conferencing/deploy-conferencing.md)를 참조 하세요.
  
모임 구성 설정에서는 사용자가 만들 수 있는 모임의 유형 외에도 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가할 수 있는 방법 (또는 경우)을 제어할 수도 있습니다. 이러한 설정은 예정 된 모임에만 영향을 줍니다. 비즈니스용 Skype에서 모임 시작 옵션을 클릭 하 여 만든 임시 모임에는 영향을 주지 않습니다.
  
모임 구성 설정에서 다음을 정의 합니다.
  
- 사용자가 공공 전화망 (PSTN)에서 전화 접속을 할 수 있는지 여부 대기실로 이동 합니다.
    
- 발표자가 될 수 있는 사람
    
- 회의 종류가 기본적으로 할당 되는지 여부
    
- 익명 (인증 되지 않은) 사용자가 기본적으로 허가 되었는지 여부
    
비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임의 특성을 정의할 수 있습니다. 
  
전역 수준 (기본적으로 만들어짐), 사이트 수준 또는 풀 수준에서 모임 설정을 지정할 수 있습니다. 기본적으로 전역 설정은 모임 환경을 정의 합니다. 풀 수준 설정을 만드는 경우 해당 설정이 해당 풀에서 호스트 하는 모든 모임에 적용 됩니다. 풀 수준 설정을 만들지 않으면 사이트 수준 설정이 있는 경우 적용 됩니다. 사이트 수준 설정을 정의 하지 않으면 모든 모임에 전역 설정이 적용 됩니다.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 모임 설정 관리

비즈니스용 Skype Server 제어판을 사용 하 여 모임 설정을 관리 하려면 다음을 실행 합니다.
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 모임 설정 관리

비즈니스용 Skype Server Management Shell을 사용 하 여 모임을 관리 하려면 다음 cmdlet을 사용 합니다.
  
**모임 구성 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정에 대 한 정보를 반환 합니다.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |사이트 또는 서비스 범위에서 모임 구성 설정의 새 컬렉션을 만듭니다.  <br/> |
|[제거-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |기존 모임 구성 설정 모음을 삭제 합니다.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정을 수정 합니다.  <br/> |
   

