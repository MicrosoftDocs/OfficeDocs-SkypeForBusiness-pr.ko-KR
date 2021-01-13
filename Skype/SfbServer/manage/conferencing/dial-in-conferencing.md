---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 관리
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
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 2674db010939f7b544ee296aea28739ecc7b806d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828158"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 회의 관리
 
**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 관리하는 방법을 배워야 합니다.
  
이 항목에서는 전화 접속 회의를 관리하는 방법에 대해 설명합니다. 배포 시 전화 접속 회의를 계획 및 구성하는 방법에 대한 자세한 내용은 비즈니스용 [Skype](../../plan-your-deployment/conferencing/dial-in-conferencing.md) 서버에서 전화 접속 회의 계획 및 비즈니스용 [Skype](../../deploy/deploy-conferencing/dial-in-conferencing.md)서버에서 전화 접속 회의 구성을 참조하세요.
  
전화 접속 회의를 관리하기 위해 다음 작업을 수행할 수 있습니다. 전화 접속 회의를 사용하거나 사용하지 않도록 설정하고, 액세스 번호를 관리하고, 전화 접속 회의에 대한 PIN 정책을 관리하고, 전화 회의 참가 및 나가기 공지 사항을 관리하고, DTMF 명령에 대한 키 매핑을 수정하고, 사용자를 전화 접속 회의로 시작하도록 허용할 수 있습니다. 
  
다이얼 플랜 관리에 대한 자세한 내용은 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 [수정을 참조하세요.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
PSTN 사용에 대한 자세한 내용은 [비즈니스용 Skype에서 음성 정책, PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)사용 레코드 및 음성 경로 구성을 참조하세요.
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 회의 관리

전화 접속 회의에 대한 정보를 관리합니다.
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭합니다.
    
다이얼 플랜 및 PSTN 사용에 대한 정보를 관리합니다.
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅을 클릭합니다.**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 관리

비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의를 관리하기 위해 다음 cmdlet을 사용하세요.
  
**전화 접속 구성 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용하도록 구성된 전화 회의 디렉터리에 대한 정보를 반환합니다. 전화 회의 디렉터리는 전화 접속 회의 사용자가 전화 회의 정보를 찾는 데 사용됩니다.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가하거나 퇴장할 때 비즈니스용 Skype 서버가 응답하는 방식에 대한 정보를 검색합니다.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |조직에서 사용하도록 구성된 모든 전화 접속 회의 액세스 번호에 대한 정보를 반환합니다.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multi-Frequency) 신호 설정을 반환합니다. DTMF는 전화 회의에 전화로 접속한 사용자가 전화기의 키패드를 사용하여 전화 회의 설정(예: 자신에 대한 음소거 및 음소거 해제, 전화 회의 잠금 및 잠금 해제)을 제어할 수 있도록 합니다.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |비즈니스용 Skype 서버 전화 접속 회의에서 사용할 수 있는 지역/소수 언어를 비롯한 언어 목록을 반환합니다. 이러한 언어는 전화를 통해 전화 회의에 참가하고 있는 사용자에게 오디오 메시지와 지침을 릴레이하는 데 사용됩니다.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |조직에서 사용되는 다이얼 플랜에 대한 정보를 반환합니다.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |다이얼 플랜을 하나 이상의 사용자나 그룹에 할당합니다.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Microsoft Office Communications Server 2007 R2에서 비즈니스용 Skype 서버로 전화 회의를 가져올 수 있습니다. 이를 통해 비즈니스용 Skype 서버와 Office Communications Server 2007 R2 간의 상호 연동성을 제공할 수 있습니다.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |기존 회의 디렉터리를 한 풀에서 다른 풀로 이동  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |조직에서 사용할 새 전화 회의 디렉터리를 만듭니다.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |새 전화 접속 회의 액세스 번호를 만듭니다.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |전화 접속 회의 구성 설정의 새 컬렉션을 만듭니다. 이러한 설정에 따라 사용자가 전화 접속 회의에 참가하거나 회의에서 나간 경우 비즈니스용 Skype 서버가 응답하는 방식이 결정됩니다. 이 정보는 참가자가 회의에 입장할 때 자신의 이름을 기록해야 하는지 여부와 시스템에서 입장 또는 퇴장을 알리는 방법(또는 알리는지 여부)에 관계없이 반환됩니다.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multi-Frequency) 신호 설정의 새 컬렉션을 만듭니다.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |새 다이얼 플랜을 만듭니다.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |기존 전화 회의 디렉터리를 제거합니다.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호를 제거합니다.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |전화 접속 회의 구성 설정 컬렉션을 하나 이상 제거합니다. 이러한 설정에 따라 사용자가 전화 접속 회의에 참가하거나 회의에서 나간 경우 비즈니스용 Skype 서버가 응답하는 방식이 결정됩니다.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multi-Frequency) 신호 설정의 기존 컬렉션을 제거합니다.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |기존 전화 접속 회의 액세스 번호의 속성 값을 수정합니다.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |사용자가 전화 접속 회의에 참가하거나 퇴장할 때 비즈니스용 Skype 서버가 응답하는 방법을 결정하는 설정을 수정합니다.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |전화 접속 회의에 사용되는 DTMF(Dual-Tone Multifrequency) 신호 설정을 수정합니다.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |기존 다이얼 플랜을 수정합니다.  <br/> |
   
**PIN 정책 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |조직에서 사용하도록 구성된 클라이언트 개인식별번호(PIN) 인증 정책에 대한 정보를 반환합니다. PIN 인증을 사용하면 사용자 이름과 암호 대신 PIN을 제공하여 비즈니스용 Skype 서버에 액세스할 수 있습니다.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |사용자 또는 사용자 그룹에 클라이언트 개인식별번호(PIN) 정책을 할당합니다.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |새 클라이언트 개인식별번호(PIN) 정책을 만듭니다.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |지정된 개인식별번호(PIN) 정책을 제거합니다.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |하나 이상의 기존 클라이언트 PIN(개인 식별 번호) 정책을 수정합니다.  <br/> |
   

