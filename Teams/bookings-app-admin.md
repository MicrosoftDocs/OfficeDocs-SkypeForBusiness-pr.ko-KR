---
title: Microsoft Teams에서 Bookings 앱 관리
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
- highpri
ms.reviewer: ''
description: 조직의 사용자를 위해 Teams에서 Bookings 앱을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 3b3db2fed9177c089a27b89264ec85425d4ffbbf
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784213"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Microsoft Teams에서 Bookings 앱 관리

Microsoft Teams의 Bookings 앱은 대면 및 가상 약속을 예약하는 간단한 방법을 제공합니다. 예를 들어, 의료 방문, 재무 상담, 인터뷰, 고객 지원 및 교육 사무실 시간. 자세한 내용은 [Teams 및 Bookings 앱을 사용하여 가상 약속을 참조하세요](/microsoft-365/frontline/bookings-virtual-visits).

스케줄러에서는 단일 환경에서 여러 부서 및 직원 일정 및 내부 및 외부 참석자와의 통신을 관리할 수 있습니다. 가상 약속은 강력한 화상 회의 기능을 제공하는 Microsoft Teams 모임을 통해 개최됩니다.

> [!NOTE]
> 스케줄러만 Teams에 Bookings 앱을 설치하면 됩니다. 가상 약속을 수행하거나 참여하는 직원은 앱이 필요하지 않습니다. Outlook 또는 Teams 일정 또는 예약 확인 전자 메일의 Teams 모임 링크에서 약속에 참가하기만 하면 됩니다.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Teams에서 Bookings 앱을 사용하기 위한 필수 구성 요소

* Exchange 사서함이 Exchange Online 있습니다. 온-프레미스 Exchange Server 사서함은 지원되지 않습니다.
* Microsoft Bookings 조직에 사용할 수 있습니다.
* 사용자에게 적절한 라이선스가 있습니다. Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 및 Business Standard가 지원됩니다.
* Bookings 앱의 모든 사용자와 모임에 참여하는 모든 직원은 Teams 모임 일정을 지원하는 라이선스를 가지고 있습니다.
* [소프트웨어 및 브라우저 필수 구성 요소.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Teams의 Bookings 가용성

Teams용 Microsoft Bookings 앱은 데스크톱 및 웹에서 사용할 수 있습니다. [Teams의 앱 및 Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 관리 센터의 **앱 관리** 에서 찾을 수 있습니다.

### <a name="control-access-to-bookings-within-your-organization"></a>조직 내에서 Bookings에 대한 액세스 제어

Bookings 앱에 액세스할 수 있는 사용자와 앱의 특정 기능에 액세스할 수 있도록 제어하는 방법에는 여러 가지가 있습니다. Microsoft Bookings 앱을 사용할 수 있도록 설정하거나 Microsoft 365 관리 센터 사용하지 않도록 설정할 수 있습니다. 또는 일부 사용자가 Bookings 일정을 만들 수 있도록 Bookings 앱 정책을 만들 수 있습니다. [Microsoft Bookings 액세스 권한을](/microsoft-365/bookings/get-access) 참조하세요.

[Teams 앱 설정 정책을 만들어 일부 사용자에 대해 Bookings 앱을 고정할 수도 있습니다](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>권장 모임 정책 설정

Bookings에 가장 적합한 환경을 사용하도록 설정하려면 Teams 모임 정책을 만들어 **조직의 모든 사용자를** 자동으로 허용하고 직원에게 정책을 할당합니다. 이 정책을 사용하면 직원이 약속에 자동으로 참가하고 외부 참석자에게 로비 환경을 사용할 수 있습니다. [모임에 사용자를 자동으로 인정하는 방법을 참조하세요](meeting-policies-participants-and-guests.md#automatically-admit-people).

모임 정책에 대한 자세한 내용은 [Teams에서 모임 정책 관리 및 Teams에서](meeting-policies-in-teams.md) [모임 정책 및 모임 만료를 참조하세요](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>선택적 직원 승인 설정

Bookings가 일정 가용성 정보를 공유하기 전에 다른 사람들이 약속을 예약하기 전에 직원이 옵트인하도록 요구할 수 있습니다.

이 설정을 사용하려면 설정  **설정** **Microsoft 365 관리 센터** \> \> 이동한 다음 예약 **을** 선택합니다.

이 설정이 켜져 있으면 직원은 예약 일정에 대한 멤버십을 승인하도록 요청하는 이메일을 받습니다.  

이 기능은 점차적으로 Microsoft 365 및 Office 365 고객을 대상으로 전 세계에 배포되고 있습니다. 사용자 환경에서 아직 모든 옵션을 사용할 수 없는 경우 곧 다시 확인하세요.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Bookings 사서함을 설정할 때 기본 도메인 변경

Bookings 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인이 사용됩니다. 그러나 기본 도메인은 외부 받는 사람에게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 예를 들어 초대에 스팸 플래그가 지정되고 받는 사람의 정크 폴더로 이동될 수 있으므로 받는 사람이 초대를 볼 수 없습니다.

Bookings 사서함을 만들기 전에 기본 도메인을 변경하는 것이 좋습니다. [도메인 FAQ를 참조하세요](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

Bookings 사서함을 만든 후 기본 도메인을 변경해야 하는 경우 PowerShell을 사용합니다.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

사서함 cmdlet [설정](/powershell/module/exchange/mailboxes/set-mailbox) 에 대한 PowerShell 설명서를 참조하세요.

> [!NOTE]
> Exchange 하이브리드 구성을 사용하는 경우 기본 도메인을 변경할 때 온-프레미스 Exchange와 Exchange Online 간의 메일 흐름을 철저히 테스트하는 것이 좋습니다.

## <a name="send-feedback"></a>피드백 보내기

다음에 대한 의견을 보내주세요.

* 사용자 환경 또는 사용 편의성
* 기능 간격 또는 누락된 기능
* 버그 또는 문제
  
피드백을 보내려면 Teams 왼쪽 탐색 모음의 맨 아래에 있는 **도움말** 옵션을 선택한 다음 **, 모든** **문제에 대한 문제 보고를** 선택합니다. 피드백 보고서의 시작 부분에서 예약 문제를 쉽게 식별할 수 있도록 "Bookings"에 대한 피드백을 보내고 있음을 나타냅니다.

## <a name="related-articles"></a>관련 기사

[브라우저에서 Teams 가상 약속에 대한 조인 환경 관리](/microsoft-365/frontline/browser-join)


  [최종 사용자를 위한 Bookings 설명서](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
