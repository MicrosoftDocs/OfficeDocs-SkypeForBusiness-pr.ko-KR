---
title: 2013에서 회의 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '요약: 회의에서 회의를 관리하는 비즈니스용 Skype 서버.'
---

# <a name="manage-conferencing-in-skype-for-business-server"></a>2013에서 회의 비즈니스용 Skype 서버
 
**요약:** 회의에서 회의를 관리하는 방법을 비즈니스용 Skype 서버.
  
이 항목에서는 회의를 관리하는 방법에 대해 설명합니다. 회의를 계획하고 배포하는 방법에 대한 자세한 내용은 [Plan for conferencing in 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in 비즈니스용 Skype 서버](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
이 비즈니스용 Skype 서버 다음과 같이 구성 및 정책 설정을 지정하여 회의 세부 정보를 관리합니다. 회의 및 모임 용어가 서로 다른 데 사용되는 경우도 있습니다. 그러나 일반적으로 모임을 특정 회의 인스턴스로 생각할 수 있습니다.
  
- **회의 정책** 설정에는 모임에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 최대 참석할 수 있는 사용자 수에 이르기까지 다양한 이벤트 및 참가 옵션이 포함됩니다. 회의 정책을 사용하여 모임의 보안, 대역폭 및 법적 측면을 관리할 수 있습니다.
    
    회의 정책은 사용자 또는 사이트에 적용되고 특정 모임에 적용할 수 없습니다. 따라서 회의에 대한 모임 초대는 몇 주 전에 만들 수 있지만 제한적인 회의 정책은 회의가 시작되기 직전에 모임 이끌이의 비즈니스용 Skype 계정에 적용해야 합니다. 
    
    모임 이끌이 역할에 전용 계정을 사용하는 경우 회의 정책이 해당 계정에 할당된 상태로 유지될 수 있습니다. 모임 이끌이가 일반 비즈니스용 Skype 사용하는 경우 회의가 완료된 후 정책을 제거해야 합니다.
    
- **모임 구성 설정** 은 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가하는 방법을 제어하는 것 외에도 사용자가 만들 수 있는 모임 유형을 제어합니다. 이러한 설정은 예약된 모임에만 영향을 미치게 됩니다. 모임 구성은 풀, 사이트 또는 전역에 따라 적용됩니다.
    
- **회의 구성** 설정은 모임 콘텐츠 및 유인물에 허용되는 최대 크기와 같은 내용을 확인합니다. 응용 프로그램 공유 회의 서비스의 최대 대역폭 양 저장소 제한 및 만료 기간 지원되는 클라이언트의 내부 및 외부 다운로드 URL 사용자가 회의 도움말 및 리소스를 얻을 수 있는 내부 및 외부 URL에 대한 포인터 및 응용 프로그램 공유, 클라이언트 오디오, 파일 전송 및 미디어 트래픽에 사용되는 포트
    
    이러한 설정을 통해 실제 서버를 직접 관리할 수 있습니다. 이러한 설정은 관리 셸에서만 설정할 비즈니스용 Skype 서버 있습니다. 
    
- **전화 접속 액세스 설정을** 사용하면 사용자가 휴대폰에서 전화를 걸지 여부와 방법에 대한 정보를 정의할 수 있습니다. 제어판 음성 라우팅 탭에서 액세스 번호와 같은 전화 접속 액세스 정보 중 일부를 지정하고 다이얼 플랜, 음성 정책, 경로 및 PSTN 사용과 같은 일부 전화 접속 정보를 지정합니다.
    
- **PIN 정책 설정을** 사용하면 참가자가 전화 접속 액세스에 사용하는 PIN의 이름을 지정하고 정의할 수 있습니다.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>회의 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 비즈니스용 Skype 서버 관리

대부분의 회의 정책 및 구성 설정은 비즈니스용 Skype 서버 관리 셸을 사용하여 관리할 비즈니스용 Skype 서버 있습니다. 일부 구성 설정은 관리 셸에서만 비즈니스용 Skype 서버 있습니다.
  
- 회의 정책 설정을 관리하려면
    
  - 제어판에서 회의 **회의 | 회의 정책**.
    
  - PowerShell에서 **-CsConferencingPolicy** cmdlet을 검색합니다.
    
- 모임 구성 설정을 관리하려면
    
  - 제어판에서 회의 **회의 | 모임 구성**.
    
  - 관리 비즈니스용 Skype 서버 셸에서 **-CsMeetingConfiguration** cmdlet을 검색합니다.
    
- 전화 접속 액세스 번호 설정을 관리하려면
    
  - 제어판에서 회의 **회의 | 전화 접속 액세스 번호입니다**.
    
  - 비즈니스용 Skype 서버 관리 셸에서 **-CsDialInConferencing** cmdlet을 검색합니다.
    
- 다이얼 플랜, 음성 정책, 경로 및 PSTN 사용과 같은 전화 접속 액세스 정보를 관리합니다. 
    
  - 제어판에서 회의 **회의 | 음성 라우팅**.
    
  - 비즈니스용 Skype 서버 관리 셸에서 **-CsDialPlan** 및 **-CsVoice** cmdlet을 검색합니다.
    
- PIN 정책 설정을 관리하려면
    
  - 제어판에서 회의 **회의 | PIN 정책**.
    
  - 관리 비즈니스용 Skype 서버 셸에서 **-CsPinPolicy** cmdlet을 검색합니다.
    
- 회의 구성 설정을 관리하려면 관리 셸의 비즈니스용 Skype 서버 합니다. **-CsConferencingConfiguration** cmdlet을 검색합니다.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>비즈니스용 Skype 서버 관리 셸 cmdlet

다음 관리 셸 cmdlet을 비즈니스용 Skype 서버 회의를 관리할 수 있습니다. 
  
**회의 정책 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |조직에서 사용하도록 구성된 회의 정책에 대한 정보를 반환합니다. 회의 정책에 따라 회의에 사용할 수 있는 기능이 결정됩니다. 여기에는 전화 회의에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 모임에 참가할 수 있는 최대 사용자 수까지 모든 것이 포함됩니다.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |사용자별 범위에서 전화 회의 정책을 할당합니다.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |조직에서 사용할 새 회의 정책을 만듭니다.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |지정한 회의 정책을 제거합니다.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |기존 회의 정책을 수정합니다.  <br/> |
   
**모임 구성 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정에 대한 정보를 반환합니다. 모임 구성 설정은 사용자가 만들 수 있는 모임 유형을 제어하고 익명 사용자 및 전화 접속 회의 사용자가 이러한 모임에 참가할 수 있는 방법을 제어하는 데 도움이 됩니다.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |사이트 또는 서비스 범위에서 새 전화 회의 구성 컬렉션을 만듭니다. 이러한 설정은 예약된 모임에만 영향을 미치게 됩니다. 모임 시작 옵션을 클릭하여 만든 ad-hoc 모임에는 영향을 주지 비즈니스용 Skype.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |모임 구성 설정의 기존 컬렉션을 삭제합니다.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |조직에서 현재 사용 중인 모임 구성 설정을 수정합니다.  <br/> |
   
**회의 구성 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |조직의 회의 구성 설정에 대한 정보를 반환합니다. 전화 회의 설정은 전화 회의 콘텐츠 및 유인물에 허용되는 최대 크기, 콘텐츠 유예 기간(즉, 콘텐츠를 삭제하기 전까지 보관할 시간) 및 지원되는 클라이언트의 내부 및 외부 다운로드 URL 등과 같은 사항을 결정합니다.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |전화 회의 구성 설정의 새 컬렉션을 만듭니다.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |전화 회의 구성 설정의 지정된 컬렉션을 제거합니다.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |전화 회의 구성 설정의 기존 컬렉션을 수정합니다.  <br/> |
   
**전화 접속 구성 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용하도록 구성된 전화 회의 디렉터리에 대한 정보를 반환합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가하거나 비즈니스용 Skype 서버 응답하는 방법에 대한 정보를 검색합니다.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |조직에서 사용하도록 구성된 모든 전화 접속 회의 액세스 번호에 대한 정보를 반환합니다.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multifrequency) 신호 설정을 반환합니다. DTMF는 전화 회의에 전화로 접속한 사용자가 전화기의 키패드를 사용하여 전화 회의 설정(예: 자신에 대한 음소거 및 음소거 해제, 전화 회의 잠금 및 잠금 해제)을 제어할 수 있도록 합니다.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |전화 접속 회의에서 사용할 수 있는 지역/소수 언어를 비롯한 언어 비즈니스용 Skype 서버 반환합니다. 이러한 언어는 전화를 통해 전화 회의에 참가하고 있는 사용자에게 오디오 메시지와 지침을 릴레이하는 데 사용됩니다.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |조직에서 사용되는 다이얼 플랜에 대한 정보를 반환합니다.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |다이얼 플랜을 하나 이상의 사용자나 그룹에 할당합니다.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Microsoft Office Communications Server 2007 R2에서 회의 비즈니스용 Skype 서버. 이렇게 하면 Communications Server 2007 R2와 비즈니스용 Skype 서버 Office 상호운용할 수 있습니다.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |한 풀에서 다른 풀로 기존 회의 디렉터리를 이동합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용할 새 전화 회의 디렉터리를 만듭니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |새 전화 접속 회의 액세스 번호를 만듭니다.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |전화 접속 회의 구성 설정의 새 컬렉션을 만듭니다. 이러한 설정은 사용자가 비즈니스용 Skype 서버 전화 접속 회의에 참가하거나 퇴장할 때 응답하는 방식이 결정됩니다. 이 정보는 참가자가 회의에 입장할 때 자신의 이름을 기록해야 하는지 여부와 시스템에서 입장 또는 퇴장을 알리는 방법(또는 알리는지 여부)에 관계없이 반환됩니다.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multifrequency) 신호 설정의 새 컬렉션을 만듭니다.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |새 다이얼 플랜을 만듭니다.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |기존 전화 회의 디렉터리를 제거합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호를 제거합니다.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |전화 접속 회의 구성 설정 컬렉션을 하나 이상 제거합니다. 이러한 설정은 사용자가 비즈니스용 Skype 서버 전화 접속 회의에 참가하거나 퇴장할 때 응답하는 방식이 결정됩니다.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(복합 주파수 부호) 신호 설정의 기존 컬렉션을 제거합니다.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호의 속성 값을 수정합니다. 전화 접속 회의를 사용하면 사용자가 "일반" 전화기, 휴대폰 또는 PSTN(공중 전화망)의 다른 장치를 사용하여 전화 회의의 오디오 부분에 참가할 수 있습니다.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가하거나 퇴장할 비즈니스용 Skype 서버 응답하는 방법을 결정하는 설정을 수정합니다.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multifrequency) 신호 설정을 수정합니다.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |기존 다이얼 플랜을 수정합니다.  <br/> |
   
**PIN 정책 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |조직에서 사용하도록 구성된 클라이언트 개인식별번호(PIN) 인증 정책에 대한 정보를 반환합니다. PIN 인증을 사용하면 사용자가 사용자 비즈니스용 Skype 서버 암호 대신 PIN을 제공하여 PIN에 액세스할 수 있습니다.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |사용자 또는 사용자 그룹에 클라이언트 PIN(개인 식별 번호) 정책을 할당합니다.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |새 클라이언트 개인식별번호(PIN) 정책을 만듭니다.  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |지정된 개인식별번호(PIN) 정책을 제거합니다.  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |하나 이상의 기존 클라이언트 PIN(개인 식별 번호) 정책을 수정합니다.  <br/> |
   
**기타 회의 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |회의실을 비즈니스용 Skype 서버 사용하지 않도록 설정합니다. 회의실은 소규모 회의 공간의 비디오 회의 및 공동 작업 시나리오를 진행할 수 있도록 설계된 회의 장치입니다. 회의실 개체를 사용하지 않도록 설정하면 회의실을 나타내는 비즈니스용 Skype 서버 할당된 모든 Active Directory 특성이 제거됩니다. 그러나 Active Directory 사용자 계정 자체는 삭제되지 않습니다.  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |회의실을 비즈니스용 Skype 서버 수 있습니다. 회의실을 사용하도록 설정하려면 먼저 해당 시스템을 나타내는 Active Directory 사용자 계정을 만들어야 합니다. 회의실 개체는 사용자 계정을 기반으로 하지만 Get-CsUser cmdlet을 실행할 때는 표시되지 않습니다.  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |조직에서 사용되는 회의 고지 조항에 대한 정보를 반환합니다. 회의 고지 조항은 하이퍼링크를 사용하여 회의에 참가하는 사용자에게 표시되는 메시지입니다(예: 회의에 대한 링크를 Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |조직에서 사용하도록 구성된 비즈니스용 Skype 서버 회의실에 대한 정보를 반환합니다.  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |등록자 비즈니스용 Skype 서버 회의실 개체를 다른 등록자 풀로 이동합니다.  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |조직에서 사용되는 전화 회의 고지의 머리글 및 본문에서 텍스트를 지우습니다. 회의 고지 조항은 하이퍼링크를 사용하여 회의에 참가하는 사용자에게 표시되는 메시지입니다(예: 회의에 대한 링크를 Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |기존 회의실의 속성 비즈니스용 Skype 서버 수정합니다.  <br/> |
   
**설정 테스트**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |사용자 쌍이 응용 프로그램 공유 회의에 참가할 수 있는지 여부를 테스트합니다.  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |사용자가 오디오 회의 공급자에 연결할 수 있는지 테스트합니다. 오디오 회의 공급자는 조직에 회의 서비스를 제공하는 타사입니다. 특히 외부에 있거나 회사 네트워크 또는 인터넷에 연결되지 않은 사용자는 오디오 회의 공급자를 통해 회의 또는 모임의 오디오 부분에 참여할 수 있습니다.  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |사용자 쌍이 A/V(오디오/비디오) 회의에 참가할 수 있는지 여부를 테스트합니다.  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |한 쌍의 사용자가 슬라이드, 화이트보드 또는 설문 조사를 공유하거나 비즈니스용 Skype 서버 등의 활동을 포함하는 PowerPoint 회의에 참가할 수 있는지 여부를 검증합니다. 또한 이 cmdlet은 비즈니스용 Skype 서버 웹 회의 서비스가 Office Web Apps 서버를 검색할 수 있으며 클라이언트가 PowerPoint Web Apps Server를 통해 브로드캐스트할 PowerPoint 업로드할 수 Office 확인합니다.  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |사용자가 전화 접속 회의 세션에 참여할 수 있는지 검사합니다.  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |다이얼 플랜(이전의 위치 프로필)에 대해 전화 번호를 테스트하고 정규화 규칙이 적용된 후 변환된 번호뿐만 아니라 번호에 적용되는 정규화 규칙을 반환합니다.  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |세 사용자가 모바일 서비스 회의에 참가할 비즈니스용 Skype 서버 기능을 테스트합니다. 모바일 서비스를 사용하면 iPhone 및 Windows Phone과 같은 휴대폰 사용자가 인스턴트 메시지 및 현재 상태 정보를 교환하고, 무선 공급자가 아닌 내부적으로 음성 메일을 저장 및 검색하고, 업무를 통한 전화 및 전화 접속 회의와 같은 비즈니스용 Skype 서버 기능을 활용할 수 있습니다.  <br/> **참고:** MCX를 사용하는 클라이언트는 2019년 8월에 비즈니스용 Skype 서버 않습니다.|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |한 쌍의 사용자가 UCWA(Unified Communications Web API)를 사용하여 온라인 회의를 예약, 참가 및 진행할 수 있는 기능을 테스트합니다.  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |에 포함된 데이터 회의 기능에 대한 진단 정보를 비즈니스용 Skype 서버.  <br/> |
