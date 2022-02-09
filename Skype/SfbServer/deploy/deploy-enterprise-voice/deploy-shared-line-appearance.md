---
title: 2015년 비즈니스용 Skype 서버 줄 모양 배포
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 이 항목을 통해 2015년 11월 2015년 11월 누적 업데이트에서 SLA(공유 선 모양)를 비즈니스용 Skype 서버 방법을 읽어 읽습니다. SLA는 공유 번호라는 특정 번호에서 여러 호출을 처리하는 기능입니다.
ms.openlocfilehash: 5adf5934e93bd93fe9f50c0a8e4dd790c695da57
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397488"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 줄 모양 배포

이 항목을 통해 2015년 11월 2015년 11월 누적 업데이트에서 SLA(공유 선 모양)를 비즈니스용 Skype 서버 방법을 읽어 읽습니다. SLA는 공유 번호라는 특정 번호에서 여러 호출을 처리하는 기능입니다.

이 기능에 대한 자세한 내용은 [Plan for Shared Line Appearance in 비즈니스용 Skype 서버 참조하십시오](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

SLA(공유 선 모양)는 2015년 11월 비즈니스용 Skype 서버 업데이트의 새로운 기능입니다. 이 기능을 사용하려면 먼저 이 누적 업데이트를 배포해야 합니다.

### <a name="install-shared-line-appearance"></a>공유 줄 모양 설치

1. 업데이트 비즈니스용 Skype 서버 2015 `SkypeServerUpdateInstaller.exe` 년 11월 누적 업데이트가 배포된 후 풀의 각 프런트 엔드 서버에서 패치를 실행합니다.

2. 설치 관리자에서 최신 버전의 SLA 응용 프로그램을 배포합니다. 그러나 응용 프로그램은 기본적으로 사용하도록 설정되지 않습니다. 아래에 설명된 단계에 따라 이 기능을 사용할 수 있습니다.

    a. 각 풀에 대해 다음 명령을 실행하여 SLA를 서버 응용 프로그램으로 등록합니다.

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   여기서 %FQDN%은 풀의 정식 도메인 이름입니다.

    b. 다음 명령을 실행하여 SLA cmdlet에 대한 RBAC 역할을 업데이트합니다.

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA가 설치 및 사용하도록 설정된 모든 풀에서 모든 프런트 엔드 서버(RTCSRV 서비스)를 다시 시작합니다.

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>SLA 그룹 만들기 및 사용자 추가

1. [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹을 만들 수 있습니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    이 Set-CsSlaConfiguration cmdlet은 Enterprise Voice 계정 SLAGroup1을 SLA 엔터티로 표시하고 SLAGroup1 수는 SLA 그룹의 번호가 됩니다. SLAGroup1에 대한 모든 호출은 전체 SLA 그룹을 울리게 합니다.

    다음 예제에서는 기존 Enterprise Voice SLAGroup1에 대한 SLA 그룹을 만들고 SLAGroup1에 할당된 번호를 SLA 기본 번호로 사용 합니다.

    이 명령은 새 SLA 그룹에 대한 최대 동시 호출 수를 3으로 설정하고 이 수를 초과하는 통화에 대해 통화 중 신호가 들리면 다음을 실행합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    새 SLA Set-CsSlaConfiguration 만들거나 기존 SLA 그룹을 수정할 수 있습니다.

    > [!NOTE]
    > 지정하는 `-Identity` 대상은 유효한 기존 사용자 Enterprise Voice 계정으로 지정해야 합니다.

2. [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet을 사용하여 그룹에 대리인을 추가합니다.

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    다음 예제에서는 SLA 그룹에 사용자를 추가합니다. 그룹에 추가된 각 사용자는 다음을 사용할 Enterprise Voice 있어야 합니다.

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    그룹에 추가할 각 사용자에 대해 cmdlet을 반복합니다. 사용자는 단일 SLA 그룹에만 속할 수 있습니다.

### <a name="configure-the-sla-group-busy-option"></a>SLA 그룹 사용 중 옵션 구성

- [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹 사용 중 옵션을 구성합니다.

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    다음 예에서는 전화 번호 202-555-1234로 전달할 최대 동시 통화 수를 초과하는 통화를 설정합니다. 대상은 전화 번호 대신 조직의 사용자일 수 있습니다. 이 경우 전달된 통화를 받을 사람의 구문은 대리인을 지정할 때와 같습니다  `sip:<NameofDelegate@domain>`. 다른 가능한 매개 변수는  `BusyOption` 입니다 `Voicemail`.

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>SLA 그룹 부재 중 통화 옵션 구성

1. [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹 부재 중 통화 옵션을 구성합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 다음 예에서는 이라는 사용자에게 부재 중 전화를 전달하도록 지정합니다  `sla_forward_number`. 매개 변수에 사용할 수 있는 옵션은  `-MissedCallOption` `Forward`, 또는  `BusySignal`입니다  `Disconnect`. 를 선택하는  `Forward`경우 사용자  `-MissedCallForwardTarget` 또는 전화 번호를 대상으로 매개 변수도 포함해야 합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>그룹에서 대리인 제거

- [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet을 사용하여 그룹에서 대리인을 제거합니다.

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    예제:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>SLA 그룹 삭제

- [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹을 삭제합니다.

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    예를 들면 다음과 같습니다.

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```