---
title: Microsoft Teams 및 Bookings 앱을 통해 가상 방문
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Bookings 앱을 통해 Microsoft Teams 및 가상 방문
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125751"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams 및 Bookings 앱을 통해 가상 방문

Microsoft Teams의 Bookings 앱은 의료 방문, 금융 상담, 면접, 고객 지원, 교육 사무실 시간 등 대면 및 가상 약속을 예약하는 간단한 방법을 제공합니다.

스케줄러는 단일 경험에서 여러 부서 및 직원 일정뿐만 아니라 내부 및 외부 참석자와의 통신을 관리할 수 있습니다. 가상 약속 자체는 강력한 비디오 회의 기능을 제공하는 Microsoft Teams 모임을 통해 개최됩니다.

> [!NOTE]
> 스케줄러만 Teams에 Bookings 앱을 설치해야 합니다. 가상 약속을 진행하거나 참여하는 직원에게는 앱이 필요하지 않습니다. Outlook 또는 Teams 일정 또는 예약 확인 전자 메일의 링크에서 간단히 약속에 참가할 수 있습니다.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Teams에서 Bookings 앱을 사용하기 위한 전제

- Exchange 사서함은 Exchange Online에 있어야 합니다. 사서함의 Exchange Server 프레미스가 지원되지 않습니다.

- 조직에 대해 Microsoft Bookings를 설정해야 합니다.

- 사용자에게 적절한 라이선스가 있어야 합니다. Office 365 A3, A5, E3 및 E5와 Microsoft 365 Business Standard, A3, A5, E3 및 E5가 지원됩니다.

- Bookings 앱의 모든 사용자와 모임에 참여하는 모든 직원에게 Teams 모임 예약을 지원하는 라이선스가 있어야 합니다.

- 시스템은 모든 소프트웨어 및 브라우저의 요구 사항을 [충족해야 합니다.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Teams의 Bookings 가용성

Teams용 Microsoft Bookings 앱은 데스크톱 및 웹에서 사용할 수 있습니다. Microsoft Teams 내의 [앱](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 및 Teams 관리 센터 내의 **앱** 관리 아래에서 찾을 수 있습니다.

### <a name="control-access-to-bookings-within-your-organization"></a>조직 내에서 Bookings에 대한 액세스 제어

Bookings 앱에 대한 액세스 권한이 있는 사용자 및 앱의 특정 기능을 제어하는 여러 가지 방법이 있습니다. Microsoft 365 관리 센터에서 Microsoft Bookings를 켜거나 끄는 방법과 선택한 사용자가 Bookings 일정을 만들 수 있도록 Bookings 앱 정책을 만드는 방법을 알아보고 [Microsoft Bookings에](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)대한 액세스 권한을 참조하세요. Teams 앱 정책을 만들어 일부 사용자를 위해 Bookings 앱을 [고정하는 방법도 배울 수 있습니다.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>권장되는 모임 정책 설정

Bookings에 대한 최상의 환경을 사용하려면 조직의 모든 사람을 자동으로 인정하는 직원 모임 정책을 **만들어야 합니다.** 이렇게 하면 직원이 자동으로 약속에 참가하고 외부 참석자에 대한 로비 환경을 사용할 수 있습니다. 모임에 자동으로 사용자 수를 추가하는 방법을 자세히 [배울 수 있습니다.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>선택적 직원 승인 설정

추가 개인 정보 설정으로 예약을 통해 예약 가능 정보를 공유하기 전에 예약을 예약할 수 있도록 직원에게 옵트인(opt in)을 요구할 수 있습니다.  

이 설정을 사용하려면 **Microsoft 365** 관리 센터 설정 설정으로 이동한 다음 \>  \>  **예약을 선택합니다.**

이 설정을 설정하면 직원에게 예약 일정에 대한 구성원 자격을 승인할지 묻는 전자 메일을 받게 됩니다.  

이 기능은 Microsoft 365 및 Office 365 고객에게 점진적으로 배포되고 있습니다. 사용자 환경에서 모든 옵션을 아직 사용할 수 없는 경우 곧 다시 확인하세요.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Bookings 사서함을 설정할 때 기본 도메인 변경

Bookings 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인이 사용됩니다. 그러나 외부 받는 사람에게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 초대에 스팸으로 플래그가 지정된 후 받는 사람의 정크 폴더로 이동될 수 있으므로 받는 사람이 초대를 볼 수 없습니다.

Bookings 사서함을 만들기 전에 기본 도메인을 변경하는 것이 좋습니다. 이 작업을 하는 방법에 대한 자세한 내용은 [도메인 FAQ를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Bookings 사서함을 이미 만든 후 기본 도메인을 변경해야 하는 경우 PowerShell을 사용하여 변경할 수 있습니다.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

자세한 내용은 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet에 대한 PowerShell 설명서를 참조하세요.

> [!NOTE]
> Exchange 하이브리드 구성을 사용하는 경우 기본 도메인을 변경하는 경우,온-프레미스 Exchange와 Exchange Online 간의 메일 흐름을 철저히 테스트하는 것이 좋습니다.

## <a name="sending-feedback"></a>피드백 보내기

다음에 대한 여러분의 의견을 환영합니다.

  - 사용자 환경 또는 사용 편의성
  - 기능 간격 또는 누락된 기능
  - 버그 또는 문제
  
피드백을 보내려면  Teams 왼쪽 탐색 모음 아래쪽에 있는 도움말 단추를 클릭한 다음 모든 문제에 대한 문제 **보고를** 클릭합니다.  "Bookings"에 대한 피드백을 보내고 있는 피드백 보고서의 시작부분에서 Bookings 문제를 쉽게 식별할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[최종 사용자를 위한 Bookings 설명서](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
