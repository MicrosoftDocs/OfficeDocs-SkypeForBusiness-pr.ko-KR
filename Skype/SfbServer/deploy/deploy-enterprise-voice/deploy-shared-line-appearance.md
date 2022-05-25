---
title: 비즈니스용 Skype 서버 2015에서 공유 줄 모양 배포
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
description: 2015년 비즈니스용 Skype 서버 2015년 11월 누적 업데이트에서 SLA(공유 회선 모양)를 배포하는 방법을 알아보려면 이 항목을 참조하세요. SLA는 공유 번호라는 특정 번호에서 여러 호출을 처리하는 기능입니다.
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671594"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 공유 줄 모양 배포

2015년 비즈니스용 Skype 서버 2015년 11월 누적 업데이트에서 SLA(공유 회선 모양)를 배포하는 방법을 알아보려면 이 항목을 참조하세요. SLA는 공유 번호라는 특정 번호에서 여러 호출을 처리하는 기능입니다.

이 기능에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015의 공유 줄 모양 계획을](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md) 참조하세요.

SLA(공유 줄 모양)는 비즈니스용 Skype 서버 2015년 11월 누적 업데이트의 새로운 기능입니다. 이 기능을 사용하려면 먼저 이 누적 업데이트를 배포해야 합니다.

## <a name="install-shared-line-appearance"></a>공유 줄 모양 설치

1. 비즈니스용 Skype 서버 후 2015년 11월 누적 업데이트가 배포되고 풀의 `SkypeServerUpdateInstaller.exe` 각 프런트 엔드 서버에서 패치를 실행합니다.

2. 설치 관리자는 최신 버전의 SLA 애플리케이션을 배포합니다. 그러나 애플리케이션은 기본적으로 사용하도록 설정되지 않습니다. 아래에 설명된 단계에 따라 사용하도록 설정됩니다.

    a. 각 풀에 대해 다음 명령을 실행하여 SLA를 서버 애플리케이션으로 등록합니다.

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   여기서 %FQDN%는 풀의 정규화된 도메인 이름입니다.

    b. 다음 명령을 실행하여 SLA cmdlet에 대한 RBAC 역할을 업데이트합니다.

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA가 설치되고 사용하도록 설정된 모든 풀에서 모든 프런트 엔드 서버(RTCSRV 서비스)를 다시 시작합니다.

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>SLA 그룹 만들기 및 사용자 추가

1. [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) cmdlet을 사용하여 SLA 그룹을 만듭니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Set-CsSlaConfiguration cmdlet은 Enterprise Voice 계정 SLAGroup1을 SLA 엔터티로 표시하고 SLAGroup1의 수는 SLA 그룹의 숫자가 됩니다. SLAGroup1에 대한 모든 호출은 전체 SLA 그룹을 울림합니다.

    다음 예제에서는 기존 Enterprise Voice 사용자인 SLAGroup1에 대한 SLA 그룹을 만들고 SLAGroup1에 할당된 번호를 SLA 주선 번호로 사용합니다.

    이 명령은 새 SLA 그룹에 대한 최대 동시 호출 수를 3으로 설정하고 이를 초과하는 호출이 사용 중인 신호를 수신하도록 설정합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Set-CsSlaConfiguration 사용하여 새 SLA 그룹을 만들거나 기존 그룹을 수정할 수 있습니다.

    > [!NOTE]
    > 지정 `-Identity` 한 항목은 유효한 기존 Enterprise Voice 사용 가능한 사용자 계정이어야 합니다.

2. [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) cmdlet을 사용하여 그룹에 대리자를 추가합니다.

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    다음 예제에서는 SLA 그룹에 사용자를 추가합니다. 그룹에 추가된 각 사용자는 유효한 Enterprise Voice 사용 가능한 사용자여야 합니다.

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    그룹에 추가하려는 각 사용자에 대해 cmdlet을 반복합니다. 사용자는 단일 SLA 그룹에만 속할 수 있습니다.

## <a name="configure-the-sla-group-busy-option"></a>SLA 그룹 사용 중 옵션 구성

- [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) cmdlet을 사용하여 SLA 그룹 사용 중 옵션을 구성합니다.

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    다음 예제에서는 전화 번호 202-555-1234로 전달될 최대 동시 호출 수를 초과하는 호출을 설정합니다. 대상은 전화 번호 대신 조직의 사용자일 수 있습니다. 이 경우 전달된 호출을 받는 사람의 구문은 대리  `sip:<NameofDelegate@domain>`자를 지정할 때와 동일합니다. 다른 가능한 매개 변수는 다음과 같습니다`Voicemail`.`BusyOption`

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>SLA 그룹 부재 중 통화 옵션 구성

1. [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) cmdlet을 사용하여 SLA 그룹 부재 중 호출 옵션을 구성합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 다음 예제에서는 부재 중 호출이 명명  `sla_forward_number`된 사용자에게 전달되도록 지정합니다. 매개 변수`Forward`에 `-MissedCallOption` 대한 유효한 옵션은 , `BusySignal`또는 `Disconnect`. 선택하는  `Forward`경우 사용자 또는 전화 번호를 대상으로 포함하는 매개 변수도 포함  `-MissedCallForwardTarget` 해야 합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>그룹에서 대리자 제거

- [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) cmdlet을 사용하여 그룹에서 대리자를 제거합니다.

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    예:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>SLA 그룹 삭제

- [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) cmdlet을 사용하여 SLA 그룹을 삭제합니다.

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    예를 들면 다음과 같습니다.

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
