---
title: 비즈니스용 Skype 서버 2015에서 공유 선 모양 배포
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
description: 이 항목에서는 비즈니스용 Skype Server 2015, 2015 누적 업데이트에 대 한 SLA (공유 선 모양)를 배포 하는 방법에 대해 알아봅니다. SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하기 위한 기능입니다.
ms.openlocfilehash: c9c4eef43de2f03be32e92c23e8384020e24b099
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767511"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 공유 선 모양 배포

이 항목에서는 비즈니스용 Skype Server 2015, 2015 누적 업데이트에 대 한 SLA (공유 선 모양)를 배포 하는 방법에 대해 알아봅니다. SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하기 위한 기능입니다.

이 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 공유 라인 모양에 대 한 계획](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)을 참조 하세요.

SLA (공유 선 모양)는 비즈니스용 Skype Server의 새로운 기능으로, 11 월 2015 누적 업데이트입니다. 이 기능을 사용 하도록 설정 하려면 먼저이 누적 업데이트를 배포 해야 합니다.

### <a name="install-shared-line-appearance"></a>공유 선 모양 설치

1. 비즈니스용 Skype 서버, 11 월 2015 누적 업데이트가 배포 된 후에 풀의 `SkypeServerUpdateInstaller.exe` 각 프런트 엔드 서버에서 패치를 실행 합니다.

2. 설치 관리자가 최신 버전의 SLA 응용 프로그램을 배포 하지만, 응용 프로그램은 기본적으로 활성화 되어 있지 않습니다. 이 기능은 아래에 설명 된 단계에 따라 사용할 수 있습니다.

    에서. 각 풀에 대해 다음 명령을 실행 하 여 SLA를 서버 응용 프로그램으로 등록 합니다.

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   여기서% FQDN%는 풀의 정규화 된 도메인 이름입니다.

    b. 다음 명령을 실행 하 여 SLA cmdlet에 대 한 RBAC 역할을 업데이트 합니다.

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA를 설치 하 고 활성화 한 모든 풀에서 프런트 엔드 서버 (RTCSRV 서비스)를 모두 다시 시작 합니다.

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>SLA 그룹을 만들고 사용자를 추가 합니다.

1. [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 만듭니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    CsSlaConfiguration cmdlet은 Enterprise Voice account SLAGroup1을 SLA 엔터티로 표시 하 고 SLAGroup1의 수는 SLA 그룹의 숫자가 됩니다. SLAGroup1에 대 한 모든 통화가 전체 SLA 그룹에 연결 됩니다.

    다음 예에서는 기존 Enterprise Voice user에 대 한 SLA 그룹을 만들고, SLAGroup1에 대해 SLAGroup1에 지정 된 번호를 SLA의 중요 한 번호로 사용 합니다.

    이 명령은 새 SLA 그룹에 대 한 최대 동시 통화 수를 3으로 설정 하 고,이를 초과 하 여 통화 중 신호를 들을 수 있습니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Set-CsSlaConfiguration를 사용 하 여 새 SLA 그룹을 만들거나 기존 항목을 수정할 수 있습니다.

    > [!NOTE]
    > 에 대해 `-Identity` 지정 하는 항목은 유효한 기존 엔터프라이즈 음성 사용 사용자 계정 이어야 합니다.

2. [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에 대리인을 추가 합니다.

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    다음 예에서는 사용자를 SLA 그룹에 추가 합니다. 그룹에 추가 된 각 사용자는 유효한 Enterprise Voice 사용 사용자 여야 합니다.

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    그룹에 추가 하려는 각 사용자에 대해 cmdlet을 반복 합니다. 사용자는 단일 SLA 그룹에만 속할 수 있습니다.

### <a name="configure-the-sla-group-busy-option"></a>SLA 그룹 약속 있음 옵션 구성

- [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 사용 중 옵션을 구성 합니다.

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    다음 예에서는 전화 번호 202-555-1234로 착신 전환 될 최대 동시 통화 수를 초과 하는 호출을 설정 합니다. 대상은 전화 번호 대신 조직의 사용자 일 수 있습니다. 이 경우 착신 전환 된 전화를 받는 사람에 대 한 구문은 대리인을 지정 하는 경우와 동일 합니다 `sip:<NameofDelegate@domain>`. 다른 매개 변수 `BusyOption` 를 사용할 수 `Voicemail`있습니다.

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>SLA 그룹 부재 중 전화 옵션 구성

1. [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 부재 중 전화 옵션을 구성 합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 다음 예에서는 부재 중 통화가 명명 `sla_forward_number`된 사용자에 게 전달 되도록 지정 합니다. `-MissedCallOption` 매개 `Forward`변수에 `BusySignal`대 한 유효한 옵션은, 또는 `Disconnect`입니다. 선택 `Forward`하는 경우에는 사용자 또는 전화 `-MissedCallForwardTarget` 번호를 대상으로 하는 매개 변수도 포함 해야 합니다.

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>그룹에서 대리인 제거

- [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에서 대리자를 제거 합니다.

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


