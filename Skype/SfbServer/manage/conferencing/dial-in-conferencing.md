---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: ba8b62456a1fa2024f2cf37642658e76d528ebf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818579"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 회의 관리
 
**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 관리 하는 방법에 대해 알아봅니다.
  
이 항목에서는 전화 접속 회의를 관리 하는 방법에 대해 설명 합니다. 배포 시 전화 접속 회의를 계획 하 고 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 전화 접속 회의 계획](../../plan-your-deployment/conferencing/dial-in-conferencing.md) 및 비즈니스용 [skype 서버에서 전화 접속 회의 구성](../../deploy/deploy-conferencing/dial-in-conferencing.md)을 참조 하세요.
  
전화 접속 회의를 관리 하는 다음 작업을 수행할 수 있습니다. 전화 접속 회의 사용 또는 사용 안 함, 액세스 번호 관리, 회의 전화 접속을 위한 PIN 정책 관리, 컨퍼런스 참가 관리, 알림 남기기, DTMF에 대 한 키 매핑 수정 명령 및 사용자가 전화 접속 회의를 시작 합니다. 
  
다이얼 플랜 관리에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.
  
PSTN 사용에 대 한 자세한 내용은 [비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성을](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)참조 하세요.
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 전화 접속 회의 관리

전화 접속 회의에 대 한 정보를 관리 하려면:
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 합니다.
    
다이얼 플랜 및 PSTN 사용에 대 한 정보를 관리 하려면:
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의 관리

비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의를 관리 하려면 다음 cmdlet을 사용 합니다.
  
**전화 접속 구성 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 회의 디렉터리에 대 한 정보를 반환 합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가 하거나 탈퇴할 때 비즈니스용 Skype 서버가 응답 하는 방법에 대 한 정보를 검색 합니다.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 모든 전화 접속 회의 액세스 번호에 대 한 정보를 반환 합니다.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용 되는 DTMF (듀얼 톤 다중 주파수) 신호 설정을 반환 합니다. DTMF를 사용 하 여 전화 회의에 전화를 거는 사용자는 전화기에 있는 키패드를 통해 컨퍼런스 설정 (예: 음소거 및 음소거 해제, 또는 전화를 잠그거나 잠금 취소)을 제어할 수 있습니다.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |비즈니스용 Skype 서버 전화 접속 회의에 사용 하도록 지원 되는 지역/소주주 언어를 포함 하 여 언어 목록을 반환 합니다. 이러한 언어는 전화를 사용 하 여 회의에 참여 하는 사용자에 게 오디오 메시지와 지침을 릴레이할 때 사용 됩니다.  <br/> |
|[가져오기-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |조직에서 사용 하는 다이얼 플랜에 대 한 정보를 반환 합니다.  <br/> |
|[부여-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |하나 이상의 사용자 또는 그룹에 다이얼 플랜을 할당 합니다.  <br/> |
|[가져오기-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Microsoft Office Communications Server 2007 R2에서 비즈니스용 Skype 서버로 전화 회의 디렉터리를 가져옵니다. 이렇게 하면 비즈니스용 Skype 서버와 Office Communications Server 2007 R2 간의 상호 운영성이 제공 됩니다.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |기존 전화 회의 디렉터리를 다른 풀로 이동합니다.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용할 새 전화 회의 디렉터리를 만듭니다.  <br/> |
|[새로운 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |새 전화 접속 회의 액세스 번호를 만듭니다.  <br/> |
|[새로운 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |전화 접속 회의 구성 설정의 새 모음을 만듭니다. 이 설정은 사용자가 전화 접속 회의에 참가 하거나 나갈 때 비즈니스용 Skype 서버가 응답 하는 방식을 결정 합니다. 특히 참가자가 회의에 참가할 때 자신의 이름을 기록해 서 필요한 지 여부와 관련 하 여 사용자가 통화에 참가 또는 남겨진 시스템을 알리는 방법 (또는 if)에 대 한 정보가 반환 됩니다.  <br/> |
|[새로운 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |전화 접속 회의에 사용 되는 새 DTMF (이중 톤 다중 주파수) 신호 설정 모음을 만듭니다.  <br/> |
|[새 CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |새 다이얼 플랜을 만듭니다.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |기존 전화 회의 디렉터리를 제거합니다.  <br/> |
|[제거-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호를 제거 합니다.  <br/> |
|[제거-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |하나 이상의 전화 접속 회의 구성 설정 모음을 제거 합니다. 이 설정은 사용자가 전화 접속 회의에 참가 하거나 나갈 때 비즈니스용 Skype 서버가 응답 하는 방식을 결정 합니다.  <br/> |
|[제거-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용 되는 기본 DTMF (연속톤 multi frequency) 신호 설정 모음을 제거 합니다.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호의 속성 값을 수정 합니다.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가 하거나 탈퇴할 때 비즈니스용 Skype 서버가 응답 하는 방식을 결정 하는 설정을 수정 합니다.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용 된 DTMF (multifrequency) 신호 설정을 수정 합니다.  <br/> |
|[Set CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |기존 다이얼 플랜을 수정 합니다.  <br/> |
   
**PIN 정책 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 클라이언트 개인 식별 번호 (PIN) 정책에 대 한 정보를 반환 합니다. PIN 인증은 사용자 이름 및 암호 대신 PIN을 제공 하 여 비즈니스용 Skype 서버에 액세스할 수 있도록 합니다.  <br/> |
|[부여-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |사용자 또는 사용자 그룹에 클라이언트 개인 id 번호 (PIN) 정책을 할당 합니다.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |새 클라이언트 PIN (개인 식별 번호) 정책을 만듭니다.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |지정 된 PIN (개인 식별 번호) 정책을 제거 합니다.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |하나 이상의 기존 클라이언트 PIN (개인 식별 번호) 정책을 수정 합니다.  <br/> |
   

