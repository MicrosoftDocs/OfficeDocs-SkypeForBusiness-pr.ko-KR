---
title: 비즈니스용 Skype 서버 2015에 공유 선 모양 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 비즈니스용 Skype 서버 2015, 2015의 11 월 누적 업데이트에 SLA (공유 선 모양)를 배포 하는 방법을 알아보려면이 항목을 읽어 보십시오. SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 기능입니다.
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604225"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 공유 선 모양 배포

비즈니스용 Skype 서버 2015, 2015의 11 월 누적 업데이트에 SLA (공유 선 모양)를 배포 하는 방법을 알아보려면이 항목을 읽어 보십시오. SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 기능입니다.

이 기능에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에서 공유 라인 모양 계획](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)을 참조 하십시오.

SLA (공유 선 모양)는 비즈니스용 Skype 서버의 새로운 기능이 며 11 월 2015 누적 업데이트입니다. 이 기능을 사용 하도록 설정 하려면 먼저이 누적 업데이트를 배포 해야 합니다.

### <a name="install-shared-line-appearance"></a>공유 선 모양 설치

1. 비즈니스용 Skype 서버, 2015 11 월 누적 업데이트가 배포 되 면 풀의 각 `SkypeServerUpdateInstaller.exe` 프런트 엔드 서버에서 패치를 실행 합니다.

2. 설치 관리자가 SLA 응용 프로그램의 최신 버전을 배포 하지만 응용 프로그램은 기본적으로 사용 하도록 설정 되지 않습니다. 아래에 설명 된 단계에 따라 사용 하도록 설정 됩니다.

    a. 각 풀에 대해 다음 명령을 실행 하 여 SLA를 서버 응용 프로그램으로 등록 합니다.

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   여기서% FQDN%는 풀의 정규화 된 도메인 이름입니다.

    b. 다음 명령을 실행 하 여 SLA cmdlet에 대 한 RBAC 역할을 업데이트 합니다.

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA가 설치 되어 있고 사용 하도록 설정 된 모든 풀에서 모든 프런트 엔드 서버 (RTCSRV 서비스)를 다시 시작 합니다.

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>SLA 그룹을 만들고 사용자를 추가 합니다.

1. [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 만듭니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    CsSlaConfiguration cmdlet은 Enterprise Voice 계정 SLAGroup1를 SLA 엔터티로 표시 하 고 SLAGroup1의 수는 SLA 그룹의 숫자가 됩니다. SLAGroup1에 대 한 모든 호출이 전체 SLA 그룹에 연결 됩니다.

    다음은 기존 Enterprise Voice 사용자에 대 한 SLA 그룹을 만들고 SLAGroup1에 SLAGroup1에 대해 지정 된 번호를 SLA의 중요 번호로 사용 하는 예입니다.

    이 명령은 새 SLA 그룹에 대 한 최대 동시 통화 수를 3으로 설정 하 고,이를 초과 하 여 통화 중 신호를 들을 수 있습니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    CsSlaConfiguration을 사용 하 여 새 SLA 그룹을 만들거나 기존 항목을 수정할 수 있습니다.

    > [!NOTE]
    > 지정 하는 항목은 유효한 `-Identity` 기존 Enterprise Voice 사용 가능 사용자 계정 이어야 합니다.

2. [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에 대리인을 추가 합니다.

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    다음은 SLA 그룹에 사용자를 추가 하는 예제입니다. 그룹에 추가 되는 각 사용자는 유효한 Enterprise Voice 사용이 가능한 사용자 여야 합니다.

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    그룹에 추가 하려는 각 사용자에 대해 cmdlet을 반복 합니다. 사용자는 단일 SLA 그룹에만 속할 수 있습니다.

### <a name="configure-the-sla-group-busy-option"></a>SLA 그룹 약속 있음 옵션 구성

- [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 사용 옵션을 구성 합니다.

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    다음 예에서는 전화 번호 202-555-1234으로 전달 되는 최대 동시 통화 수를 초과 하는 통화를 설정 합니다. 대상은 전화 번호 대신 조직의 사용자 일 수 있습니다. 이 경우 착신 전환 된 전화를 받는 사람에 대 한 구문은 대리인을 지정할 때와 같습니다 `sip:<NameofDelegate@domain>`. 그 밖의 `BusyOption` 가능한 매개 변수 `Voicemail`는 다음과 같습니다.

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>SLA 그룹 부재 중 전화 옵션 구성

1. [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 부재 중 전화 옵션을 구성 합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 다음 예에서는 부재 중 전화가 라는 `sla_forward_number`사용자에 게 착신 전환 되도록 지정 합니다. `-MissedCallOption` 매개 변수에 사용할 수 `Forward`있는 옵션은, `BusySignal`또는 `Disconnect`입니다. 을 선택 `Forward`하는 경우에는 다음과 같이 `-MissedCallForwardTarget` 사용자 또는 전화 번호를 대상으로 매개 변수도 포함 해야 합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>그룹에서 대리인 제거

- [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에서 대리인을 제거 합니다.

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    예를 들면 다음과 같습니다.

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>SLA 그룹 삭제

- [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 삭제 합니다.

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    예를 들면 다음과 같습니다.

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


