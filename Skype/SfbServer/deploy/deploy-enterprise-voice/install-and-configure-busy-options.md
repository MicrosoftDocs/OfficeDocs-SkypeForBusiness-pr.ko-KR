---
title: 비즈니스용 Skype 서버에 대한 사용 중 옵션 설치 및 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버에서 다른용 옵션을 설치 및 구성하는 방법을 읽어 보십시오.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830808"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 사용 중 옵션 설치 및 구성

비즈니스용 Skype 서버에서 다른용 옵션을 설치 및 구성하는 방법을 읽어 보십시오.

통화 중 옵션은 사용자가 이미 통화 또는 회의에 참석 중이거나 통화를 보류한 경우 수신 전화가 처리되는 방법을 구성할 수 있도록 2016년 7월 누적 업데이트에 도입된 새로운 음성 정책입니다. 새 전화나 수신 전화는 통화 중 신호로 거부되거나 음성 메일로 전달될 수 있습니다.

조직에 대해 다른 사용자 옵션을 사용하도록 설정한 경우 엔터프라이즈의 모든 사용자가 Enterprise Voice 및 비영구 Enterprise Voice 다음 구성 옵션을 사용할 수 있습니다.

- 다른 사용자의 통화 중 - 사용자가 통화 중일 경우 통화 중 신호로 새 수신 전화가 거부됩니다.

- 통화 중 음성 메일 - 사용자가 통화 중일 때 새 수신 전화가 음성 메일로 전달되는 경우

통화 중 옵션의 구성 방식에 관계없이 통화 또는 회의의 사용자 또는 통화가 보류된 사용자는 새 통화나 회의를 시작할 수 없습니다.

사용 중 옵션 기능에 대한 자세한 내용은 비즈니스용 Skype 서버의 다른 업무용 [옵션 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>설치

최신 버전의 비즈니스용 Skype 서버가 설치되어 있으며 최신 패치를 설치한지 확인합니다. 이렇게하려면 먼저 모든 서비스를 중지한 다음 다음과 같이 비즈니스용 Skype 서버 업데이트 설치 관리자를 실행합니다.

1. 명령 Stop-CsWindowsService 실행합니다.

2. 풀의 SkypeServerUpdateInstaller.exe 프런트 엔드 서버에서 설치 관리자를 실행합니다.

3. SBSSkypeServerUpdateInstaller.exe 장애 조치(failover)를 지원하려면 각 SBS(Survivable Branch Server)에서 설치 관리자를 실행합니다.

설치 프로그램은 최신 버전의 Busy Options 응용 프로그램을 배포합니다. 그러나 응용 프로그램은 기본적으로 사용하도록 설정되어 있지 않습니다. 응용 프로그램을 사용하도록 설정하려면 다음 단계를 수행합니다.

1. [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet을 실행하여 다음 예와 같이 Busy Options를 전역으로 사용하도록 설정할 수 있습니다.

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 다음으로 사이트에 음성 정책이 있는 경우 다음과 같이 음성 정책에 대해 다른용 옵션을 사용하도록 설정해야 합니다.

    먼저 [Get-CsSite를](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) 실행하여 사이트 이름을 검색합니다.

   ```powershell
   Get-CsSite
   ```

    사이트 음성 정책을 검색하는 데 사이트 Get-CsSite 검색된 Identity 값(예: Site:Redmond1)을 다음과 같이 사용하세요.

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    사이트에 대한 음성 정책이 있는 경우 다음 명령을 실행합니다.

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 다음으로, [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet을 실행하여 다음 예와 같이 서버 응용 프로그램 목록에 다른 사용 중 옵션을 추가합니다.

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > %FQDN%을 특정 풀의 정식 도메인 이름으로 바꾸야 합니다.

4. 다음으로 [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet을 실행하여 다음 예와 같이 다른 사용 중 옵션 cmdlet에 대한 RBAC(역할 기반 액세스 제어) 역할을 업데이트합니다.

   ```powershell
   Update-CsAdminRole
   ```

5. 마지막으로 [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) 명령을 실행하여 다른용 옵션을 설치하고 사용하도록 설정한 모든 풀의 모든 프런트 엔드 서버에서 비즈니스용 Skype 서버 Windows 서비스를 시작합니다.

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>구성

다른용 옵션을 구성하기 위해 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet을 사용하세요.

예를 들어 다음 명령은 "Ken Myer" 사용자에 대해 사용 중 옵션을 구성합니다. 이 구성에서 "Ken Myer"를 호출하면 이미 통화 중일 때 통화 중 신호가 반환됩니다.

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

다음 예제에서는 "Chrystal Velasquez" 사용자에 대한 사용 중 옵션을 구성합니다. 이 구성에서는 "Chrystal Velasquez"에 대한 새 수신 전화가 이미 통화 중일 때 음성 메일로 전달됩니다.

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet을 사용하여 다른 작업 중 옵션에 대한 구성 정보를 검색할 수 있습니다. 다음은 "KenMyer@Contoso.com"에 대한 사용 중 옵션 설정을 반환하는 예제입니다.

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet을 사용하여 다른용 옵션을 제거할 수 있습니다. 다음 명령은 "Ken Myer"에 대한 다른용 옵션을 제거합니다.

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

다른용 옵션을 구성하는 데 사용하는 cmdlet에 대한 자세한 내용은 [Set-CsBusyOptions, Get-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)및 [Remove-CsBusyOptions에](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)대한 기술 참조 콘텐츠를 참조하십시오. [](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)

## <a name="enable-logging"></a>로깅 사용

중앙 로깅 서비스를 사용하여 다른 작업 중 옵션에 대해 로깅을 사용하도록 설정하려면 다음을 지정합니다.

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>확인 및 문제 해결

사용 중 옵션을 설치한 후 [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet을 사용하여 서버 응용 프로그램 목록을 검색하여 설치가 성공적으로 완료된지 확인할 수 있습니다. 다른 작업 중 옵션이 제대로 설치된 경우 cmdlet의 출력에 사용 중 옵션 구성이 다음과 같이 표시됩니다.

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

Windows 이벤트 뷰어를 사용하여 사용 중 옵션 설치가 성공적이고 비즈니스용 Skype 서버에서 사용 중 옵션을 성공적으로 로드하는지 확인할 수 있습니다. 사용 중 옵션을 확인하려면 이벤트 뷰어 - 응용 프로그램 및 서비스 로그 **\> - \> Skype(또는 Lync) 서버를** 열고 이벤트 ID = 30253을 검색합니다.
