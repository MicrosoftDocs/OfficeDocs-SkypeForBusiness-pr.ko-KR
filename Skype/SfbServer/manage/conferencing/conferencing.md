---
title: 비즈니스용 Skype 서버에서 회의 관리
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
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '요약: 비즈니스용 Skype 서버에서 회의를 관리 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: 321241be405789e5a8b0f9440fddd09f738911ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818629"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 관리
 
**요약:** 비즈니스용 Skype 서버에서 회의를 관리 하는 방법에 대해 알아봅니다.
  
이 항목에서는 회의를 관리 하는 방법에 대해 설명 합니다. 회의를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md) 및 비즈니스용 [skype 서버에서 회의 배포](../../deploy/deploy-conferencing/deploy-conferencing.md)를 참조 하세요.
  
비즈니스용 Skype 서버에서 다음과 같이 구성 및 정책 설정을 지정 하 여 회의의 세부 정보를 관리 합니다. 회의와 모임 이라는 용어는 서로 혼용 하 여 사용 되기도 합니다. 일반적으로 모임을 특정 회의 인스턴스로 생각할 수 있습니다.
  
- **회의 정책 설정** 에는 모임에서 IP 오디오 및 비디오를 참석할 수 있는 최대 사용자 수까지 포함할 수 있는지 여부에 이르기까지 다양 한 일정 및 참가 옵션이 포함 됩니다. 회의 정책을 사용 하 여 모임의 보안, 대역폭 및 법적 측면을 관리할 수 있습니다.
    
    회의 정책은 사용자 또는 사이트에 적용 되며 특정 모임에 적용할 수 없습니다. 따라서 회의에 대 한 모임 초대는 몇 주 후에 미리 만들 수 있지만, 회의가 시작 되기 바로 전에 모임 주최자의 비즈니스용 Skype 계정에 제한적인 회의 정책을 적용 해야 합니다. 
    
    모임 이끌이 역할에 전용 계정이 사용 되는 경우 회의 정책은 해당 계정에 할당 된 상태로 유지 될 수 있습니다. 모임 이끌이가 일반적인 비즈니스용 Skype 계정을 사용 하는 경우에는 회의가 완료 된 후 정책을 제거 해야 합니다.
    
- **모임 구성 설정** 에서는 사용자가 만들 수 있는 모임의 유형 외에도 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가할 수 있는 방법 (또는 경우)을 제어할 수도 있습니다. 이러한 설정은 예정 된 모임에만 영향을 줍니다. 모임 구성은 풀, 사이트별 또는 전역으로 적용 됩니다.
    
- **회의 구성 설정** 에서는 모임 콘텐츠 및 유인물에 허용 되는 최대 크기와 같은 항목을 결정 합니다. 응용 프로그램 공유 회의 서비스에 대 한 최대 대역폭 양 저장소 용량 한도 및 만료 기간 지원 되는 클라이언트의 내부 및 외부 다운로드에 대 한 Url입니다. 사용자가 회의 도움말 및 리소스를 얻을 수 있는 내부 및 외부 Url에 대 한 포인터 응용 프로그램 공유, 클라이언트 오디오, 파일 전송 및 미디어 트래픽에 사용 되는 포트.
    
    이러한 설정을 통해 실제 서버 자체를 관리할 수 있습니다. 이러한 설정은 비즈니스용 Skype Server Management Shell을 사용 하는 경우에만 설정할 수 있습니다. 
    
- 전화 **접속 액세스 설정을** 사용 하 여 사용자가 휴대폰에서 전화를 거는 지 여부와 방법에 대 한 정보를 정의할 수 있습니다. 제어판 회의 탭에서 액세스 번호와 같은 전화 접속 액세스 정보 중 일부를 지정 하 고, 전화 접속 계획, 음성 정책, 경로, PSTN 사용 등의 일부 전화 접속 정보를 제어판의 음성 라우팅 탭에서 지정할 수 있습니다.
    
- **Pin 정책 설정을** 사용 하면 참가자가 전화 접속 액세스에 사용 하는 pin의 이름을 지정 하 고 정의할 수 있습니다.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 회의 관리

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 대부분의 회의 정책 및 구성 설정을 관리할 수 있습니다. 일부 구성 설정은 비즈니스용 Skype Server Management Shell을 사용 하는 경우에만 사용할 수 있습니다.
  
- 회의 정책 설정을 관리 하려면 다음을 실행 합니다.
    
  - 제어판에서 "회의"를 선택 합니다. ** 회의 정책**.
    
  - PowerShell에서 **-CsConferencingPolicy** cmdlet을 검색 합니다.
    
- 모임 구성 설정을 관리 하려면 다음을 실행 합니다.
    
  - 제어판에서 "회의"를 선택 합니다. ** 모임 구성**.
    
  - 비즈니스용 Skype 서버 관리 셸에서 **-CsMeetingConfiguration** cmdlet을 검색 합니다.
    
- 전화 접속 액세스 번호 설정을 관리 하려면 다음을 실행 합니다.
    
  - 제어판에서 "회의"를 선택 합니다. ** 전화 접속 액세스 번호**
    
  - 비즈니스용 Skype 서버 관리 셸에서 **-CsDialInConferencing** cmdlet을 검색 합니다.
    
- 다이얼 플랜, 음성 정책, 경로, PSTN 사용 등 전화 접속 액세스 정보를 관리 하려면 다음을 수행 합니다. 
    
  - 제어판에서 "회의"를 선택 합니다. ** 음성 라우팅**.
    
  - 비즈니스용 Skype 서버 관리 셸에서 **-csdialplan 플랜** 및 **-csdialplan** cmdlet을 검색 합니다.
    
- PIN 정책 설정을 관리 하려면 다음을 실행 합니다.
    
  - 제어판에서 "회의"를 선택 합니다. ** 고정 정책**.
    
  - 비즈니스용 Skype 서버 관리 셸에서 **-CsPinPolicy** cmdlet을 검색 합니다.
    
- 회의 구성 설정을 관리 하려면 비즈니스용 Skype Server Management Shell을 사용 해야 합니다. **-CsConferencingConfiguration** cmdlet을 검색 합니다.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>비즈니스용 Skype 서버 관리 셸 cmdlet

다음 비즈니스용 Skype Server Management Shell cmdlet을 사용 하 여 회의를 관리할 수 있습니다. 
  
**회의 정책 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 회의 정책에 대 한 정보를 반환 합니다. 회의 정책은 회의에 사용할 수 있는 기능과 기능을 결정 합니다. 여기에는 전화 회의에 참가할 수 있는 최대 사용자 수에 대 한 IP 오디오 및 비디오를 포함 하는 것이 포함 됩니다.  <br/> |
|[부여-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |사용자 단위 범위에서 회의 정책을 할당 합니다.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |조직에서 사용할 새 회의 정책을 만듭니다.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |지정 된 회의 정책을 제거 합니다.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |기존 회의 정책을 수정 합니다.  <br/> |
   
**모임 구성 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정에 대 한 정보를 반환 합니다. 모임 구성 설정 사용자가 만들 수 있는 모임의 유형을 입력 하 고 익명 사용자와 전화 접속 회의 사용자가 이러한 모임에 참가할 수 있는 방법 (또는 사용자)을 제어 합니다.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |사이트 또는 서비스 범위에서 모임 구성 설정의 새 컬렉션을 만듭니다. 이러한 설정은 예정 된 모임에만 영향을 줍니다. 비즈니스용 Skype에서 모임 시작 옵션을 클릭 하 여 만든 임시 모임에는 영향을 주지 않습니다.  <br/> |
|[제거-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |기존 모임 구성 설정 모음을 삭제 합니다.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정을 수정 합니다.  <br/> |
   
**회의 구성 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |조직의 전화 회의 구성 설정에 대 한 정보를 반환 합니다. 컨퍼런스 설정에 따라 회의 콘텐츠 및 유인물에 허용 되는 최대 크기, 콘텐츠 유예 기간 (즉, 삭제 되기 전에 저장 되는 시간 콘텐츠),이에 대 한 내부 및 외부 다운로드의 Url이 결정 됩니다. 지원 되는 클라이언트.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |회의 구성 설정의 새 컬렉션을 만듭니다.  <br/> |
|[제거-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |지정 된 회의 구성 설정 모음을 제거 합니다.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |기존 회의 구성 설정 컬렉션을 수정 합니다.  <br/> |
   
**전화 접속 구성 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 회의 디렉터리에 대 한 정보를 반환 합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가 하거나 탈퇴할 때 비즈니스용 Skype 서버가 응답 하는 방법에 대 한 정보를 검색 합니다.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 모든 전화 접속 회의 액세스 번호에 대 한 정보를 반환 합니다.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용 된 DTMF (듀얼 톤 multifrequency) 신호 설정을 반환 합니다. DTMF를 사용 하 여 전화 회의에 전화를 거는 사용자는 전화기에 있는 키패드를 통해 컨퍼런스 설정 (예: 음소거 및 음소거 해제, 또는 전화를 잠그거나 잠금 취소)을 제어할 수 있습니다.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |비즈니스용 Skype 서버 전화 접속 회의에 사용 하도록 지원 되는 지역/소주주 언어를 포함 하 여 언어 목록을 반환 합니다. 이러한 언어는 전화를 사용 하 여 회의에 참여 하는 사용자에 게 오디오 메시지와 지침을 릴레이할 때 사용 됩니다.  <br/> |
|[가져오기-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |조직에서 사용 하는 다이얼 플랜에 대 한 정보를 반환 합니다.  <br/> |
|[부여-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |하나 이상의 사용자 또는 그룹에 다이얼 플랜을 할당 합니다.  <br/> |
|[가져오기-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Microsoft Office Communications Server 2007 R2에서 비즈니스용 Skype 서버로 전화 회의 디렉터리를 가져옵니다. 이렇게 하면 비즈니스용 Skype 서버와 Office Communications Server 2007 R2 간의 상호 운영성이 제공 됩니다.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |기존 전화 회의 디렉터리를 다른 풀로 이동합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용할 새 전화 회의 디렉터리를 만듭니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[새로운 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |새 전화 접속 회의 액세스 번호를 만듭니다.  <br/> |
|[새로운 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |전화 접속 회의 구성 설정의 새 모음을 만듭니다. 이 설정은 사용자가 전화 접속 회의에 참가 하거나 나갈 때 비즈니스용 Skype 서버가 응답 하는 방식을 결정 합니다. 특히 참가자가 회의에 참가할 때 자신의 이름을 기록해 서 필요한 지 여부와 관련 하 여 사용자가 통화에 참가 또는 남겨진 시스템을 알리는 방법 (또는 if)에 대 한 정보가 반환 됩니다.  <br/> |
|[새로운 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용 되는 DTMF (multifrequency) 신호 설정의 새 모음을 만듭니다.  <br/> |
|[새 CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |새 다이얼 플랜을 만듭니다.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |기존 전화 회의 디렉터리를 제거합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[제거-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호를 제거 합니다.  <br/> |
|[제거-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |하나 이상의 전화 접속 회의 구성 설정 모음을 제거 합니다. 이 설정은 사용자가 전화 접속 회의에 참가 하거나 나갈 때 비즈니스용 Skype 서버가 응답 하는 방식을 결정 합니다.  <br/> |
|[제거-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용 되는 기본 DTMF (연속톤 multi frequency) 신호 설정 모음을 제거 합니다.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호의 속성 값을 수정 합니다. 전화 접속 회의는 사용자가 PSTN (공개 교환 전화 네트워크)의 "일반" 전화, 휴대 전화 또는 기타 장치를 사용 하 여 컨퍼런스의 오디오 부분에 참가할 수 있는 방법을 제공 합니다.  <br/> |
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
   
**다른 회의 설정**

|**은**|**설명**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |비즈니스용 Skype 서버 회의실을 사용 하지 않도록 설정 합니다. 회의실은 소규모 회의 공간의 비디오 회의 및 공동 작업 시나리오를 진행할 수 있도록 설계된 회의 장치입니다. 회의실 개체를 사용 하지 않도록 설정 하면 회의실을 나타내는 사용자 계정에 할당 된 비즈니스용 Skype Server 관련 Active Directory 특성을 모두 제거 합니다. 그러나 Active Directory 사용자 계정 자체는 삭제 되지 않습니다.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |비즈니스용 Skype 서버 회의실을 사용 하도록 설정 합니다. 회의실을 사용 하도록 설정 하려면 먼저 해당 시스템을 표시 하는 Active Directory 사용자 계정을 만들어야 합니다. 회의실 개체는 사용자 계정에 기반을 두고 있지만, Get-CsUser cmdlet을 실행할 때 이러한 개체는 표시 되지 않습니다.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |조직에서 사용 하는 회의 부인 정보를 반환 합니다. 회의 부인는 하이퍼링크 (예: Windows Internet Explorer 등의 브라우저에 회의 링크를 붙여 넣는 사용자)를 사용 하 여 전화 회의에 참가 하는 사용자에 게 표시 되는 메시지입니다.  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |조직에서 사용 하도록 구성 된 모든 비즈니스용 Skype 서버 모임 채팅방에 대 한 정보를 반환 합니다.  <br/> |
|[이동-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |비즈니스용 Skype 서버 회의실 개체를 한 등록자 풀에서 다른 등록자로 이동 합니다.  <br/> |
|[제거-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |조직에서 사용 하는 회의 책임의 머리글 및 본문에서 텍스트를 지웁니다. 회의 부인는 하이퍼링크 (예: Windows Internet Explorer 등의 브라우저에 회의 링크를 붙여 넣는 사용자)를 사용 하 여 전화 회의에 참가 하는 사용자에 게 표시 되는 메시지입니다.  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |기존 비즈니스용 Skype 서버 회의실의 속성 값을 수정 합니다.  <br/> |
   
**테스트 설정**

|**은**|**설명**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |한 쌍의 사용자가 응용 프로그램 공유 회의에 참여할 수 있는 능력을 테스트 합니다.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |사용자가 자신의 오디오 회의 공급자에 연결할 수 있는지 테스트 합니다. 오디오 회의 공급자는 조직에서 회의 서비스를 제공 하는 타사 회사입니다. 다른 요인 중에서 오디오 회의 공급자는 사용자를 사이트 외부에 배치 하 고 회사 네트워크나 인터넷에 연결 되지 않은 상태에서 컨퍼런스 또는 모임의 오디오 부분에 참가할 수 있도록 합니다.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |한 쌍의 사용자가 오디오/비디오 (A/V) 회의에 참여할 수 있는 능력을 테스트 합니다.  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |PowerPoint 슬라이드, 화이트 보드 또는 설문 보기 등의 작업을 포함 하 여 사용자 쌍이 비즈니스용 Skype 서버 웹 회의에 참가할 수 있는지 여부를 확인 합니다. 또한 cmdlet은 비즈니스용 Skype 서버 웹 회의 서비스가 Office Web Apps Server를 검색할 수 있고 클라이언트가 Office Web Apps 서버에서 브로드캐스트할 PowerPoint 파일을 업로드할 수 있는지 확인 합니다.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |사용자가 전화 접속 회의 세션에서 참여할 수 있는지 확인 합니다.  <br/> |
|[테스트-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |다이얼 플랜 (이전에 위치 프로필)에 대해 전화 번호를 테스트 하 고 정규화 규칙을 적용 한 후 해당 번호와 번역 된 숫자에 적용 되는 정규화 규칙을 반환 합니다.  <br/> |
|[테스트-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |3 명의 사용자가 비즈니스용 Skype 서버 이동성 서비스 회의에 참여할 수 있는지 테스트 합니다. 모바일 서비스는 Iphone 및 Windows phone과 같은 휴대폰 사용자가 exchange 인스턴트 메시지 및 현재 상태 정보 등의 작업을 수행할 수 있도록 합니다. 무선 공급자 대신 음성 메일을 내부적으로 저장 하 고 검색 합니다. 업무 및 전화 접속 회의를 통한 통화와 같은 비즈니스용 Skype 서버 기능을 활용해 보세요.  <br/> **참고:** MCX를 사용 하는 클라이언트는 비즈니스용 Skype 서버 2019에서 지원 되지 않습니다.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |통합 커뮤니케이션 웹 API (c)를 사용 하 여 사용자 쌍이 온라인 회의를 스케줄링 하 고, 참가 하 고, 수행할 수 있는 능력을 테스트 합니다.  <br/> |
|[디버그-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |비즈니스용 Skype 서버에 포함 된 데이터 회의 기능에 대 한 진단 정보를 반환 합니다.  <br/> |
   

