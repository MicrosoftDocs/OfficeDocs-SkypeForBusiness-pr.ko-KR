---
title: 비즈니스용 Skype 서버에 대 한 사용 중 옵션 설치 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 비즈니스용 Skype 서버에서 사용 중 옵션을 설치 하 고 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604215"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 사용 중 옵션 설치 및 구성

비즈니스용 Skype 서버에서 사용 중 옵션을 설치 하 고 구성 하는 방법에 대해 알아봅니다.

약속 있음 옵션은 사용자가 이미 통화 또는 회의에 있거나 통화를 대기 중인 경우 들어오는 호출을 처리 하는 방법을 구성할 수 있도록 하는 7 월 2016 누적 업데이트에 도입 된 새로운 음성 정책입니다. 새 통화 또는 수신 전화를 통화 중 신호가 거부 되거나 음성 메일로 전달 될 수 있습니다.

조직에 대 한 약속 있음 옵션을 사용 하는 경우 enterprise Voice 및 Enterprise 이외 음성 사용자 모두에 대해 엔터프라이즈의 모든 사용자가 다음 구성 옵션을 사용할 수 있습니다.

- 사용자가 통화 중 이라면 새 수신 전화가 통화 중으로 거부 됩니다.

- 사용자가 통화 중인 경우 새 수신 전화가 음성 메일로 착신 전환 되는 사용량이 많은 음성 사서함

약속 있음/없음 옵션을 구성 하는 방식에 관계 없이 통화 또는 전화 회의의 사용자가 또는 통화를 대기 하 고 있으면 새 통화 또는 회의가 시작 되지 않습니다.

사용 중인 옵션 기능에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 약속 있음/없음 옵션 계획](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)을 참조 하십시오.

## <a name="install"></a>설치

최신 버전의 비즈니스용 Skype 서버가 설치 되어 있고 최신 패치를 설치 했는지 확인 합니다. 이렇게 하려면 먼저 모든 서비스를 중지 한 다음 다음과 같이 비즈니스용 Skype 서버 업데이트 설치 관리자를 실행 합니다.

1. CsWindowsService 명령을 실행 합니다.

2. 풀의 각 프런트 엔드 서버에서 SkypeServerUpdateInstaller 설치 관리자를 실행 합니다.

3. SBS에서 장애 조치 (failover) 지원을 확인 하려면 각 SBS (Sba (survivable Branch Server)에서 SkypeServerUpdateInstaller 설치 관리자를 실행 합니다.

설치 관리자가 최신 버전의 사용 중 옵션 응용 프로그램을 배포 합니다. 그러나 응용 프로그램은 기본적으로 사용 하도록 설정 되지 않습니다. 응용 프로그램을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.

1. [Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet을 실행 하 여 사용 중 옵션을 다음 예와 같이 전역적으로 사용 하도록 설정 합니다.

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 다음으로, 사이트에 음성 정책이 있는 경우 다음과 같이 음성 정책에 대 한 약속 있음/없음 옵션을 사용 하도록 설정 해야 합니다.

    먼저 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) 를 실행 하 여 사이트 이름을 검색 합니다.

   ```powershell
   Get-CsSite
   ```

    다음과 같이 Get-CsSite에서 검색 된 Id 값 (예: Redmond1)을 사용 하 여 사이트의 음성 정책을 검색 합니다.

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    사이트에 대 한 음성 정책이 존재 하는 경우 다음 명령을 실행 합니다.

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 다음으로, 다음 예에 나와 있는 것 처럼, [새-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet을 실행 하 여 사용 중 옵션을 서버 응용 프로그램 목록에 추가 합니다.

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > % FQDN%를 특정 풀의 정규화 된 도메인 이름으로 바꿔야 합니다.

4. 다음에는 [CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet을 실행 하 여 사용 중인 옵션 cmdlet에 대 한 RBAC (역할 기반 액세스 제어) 역할을 다음 예제와 같이 업데이트 합니다.

   ```powershell
   Update-CsAdminRole
   ```

5. 마지막으로, 다른 용무 중 옵션이 설치 되어 있고 사용 하도록 설정 된 모든 풀의 모든 프런트 엔드 서버에서 비즈니스용 Skype 서버 Windows 서비스를 시작 합니다 ( [CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) 명령 실행).

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>구성

사용 중 옵션을 구성 하려면 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet을 사용 합니다.

예를 들어 다음 명령은 "Ken Myer" 사용자에 대 한 사용 중 옵션을 구성 합니다. 이 구성에서 "Ken Myer"에 대 한 호출은 이미 통화 중 이어야 하는 경우 통화 중 신호를 반환 합니다.

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

다음 예에서 명령은 "Chrystal Velasquez" 사용자에 대 한 사용 중 옵션을 구성 합니다. 이 구성에서는 이미 통화 중인 경우 "Chrystal Velasquez"에 대해 수신 되는 새 전화가 음성 메일로 착신 전환 됩니다.

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

[CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet을 사용 하 여 사용 중 옵션에 대 한 구성 정보를 검색할 수 있습니다. 다음은 "KenMyer@Contoso.com"에 대 한 사용 중 옵션 설정을 반환 하는 예제입니다.

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

[CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet을 사용 하 여 사용 중 옵션을 제거할 수 있습니다. 다음 명령은 "Ken Myer"에 대 한 사용 중 옵션을 제거 합니다.

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

다른 용무 중 옵션을 구성 하는 데 사용 하는 cmdlet에 대 한 자세한 내용은 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)및 [CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)에 대 한 기술 참조 콘텐츠를 참조 하십시오.

## <a name="enable-logging"></a>로깅 사용

중앙 로깅 서비스를 사용 하 여 사용 중 옵션에 대 한 로깅을 사용 하도록 설정 하려면 다음을 지정 합니다.

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>확인 및 문제 해결

사용 중 옵션을 설치한 후에는 [CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet을 사용 하 여 서버 응용 프로그램 목록을 검색 하 여 설치가 성공적으로 수행 되었는지 확인할 수 있습니다. 사용 중인 옵션이 올바르게 설치 되 면 cmdlet의 출력에는 사용 중인 옵션 구성이 다음과 같이 표시 됩니다.

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

Windows 이벤트 뷰어를 사용 하 여 작업 중 옵션이 성공적으로 설치 되었으며 비즈니스용 Skype 서버가 사용 중 옵션을 성공적으로 로드 했는지 확인할 수도 있습니다. 약속 있음 옵션을 확인 하려면 **이벤트 뷰어-\> 응용 프로그램 및 서비스 로그\> -Skype (또는 Lync) 서버** 를 열고 이벤트 ID = 30253을 검색 합니다.
