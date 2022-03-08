---
title: 에서 Bookings 앱을 Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: ITPro
ms.topic: article
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
ms.reviewer: ''
description: 조직의 사용자를 위해 Teams 예약 앱을 관리하는 방법에 대해 자세히 알아보십시오.
ms.openlocfilehash: 3032704fe935f1d4d316741400e8a4b5841f8685
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070587"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>에서 Bookings 앱을 Microsoft Teams

에 있는 Bookings Microsoft Teams 간단한 방법으로 대면 및 가상 약속을 예약할 수 있습니다. 예를 들어 의료 방문, 재무 상담, 인터뷰, 고객 지원 및 교육 사무실 시간. 자세한 내용은 가상 Teams [및 Bookings 앱을 참조하세요](expand-teams-across-your-org/bookings-virtual-visits.md).

스케줄러는 단일 환경의 내부 및 외부 참석자들과 여러 부서 및 직원 일정 및 통신을 관리할 수 있습니다. 가상 약속은 강력한 Microsoft Teams 기능을 제공하는 모임을 통해 개최됩니다.

> [!NOTE]
> 스케줄러만 Teams에 Bookings 앱을 설치하면 됩니다. 가상 약속을 수행하거나 참여하는 직원은 앱이 필요하지 않습니다. 예약 확인 전자 메일의 Outlook 또는 Teams 또는 Teams 모임 링크에서 약속에 참가할 수 있습니다.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>에서 Bookings 앱을 사용하기 위한 Teams

* Exchange 사서함이 Exchange Online. 사서함의 Exchange Server 프레미스가 지원되지 않습니다.
* Microsoft Bookings는 조직에서 사용할 수 있습니다.
* 사용자에게 적절한 라이선스가 있습니다. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 및 비즈니스 표준이 지원됩니다.
* Bookings 앱의 모든 사용자와 모임에 참가하는 모든 직원에게는 모임 예약을 지원하는 라이선스가 Teams 있습니다.
* [소프트웨어 및 브라우저](hardware-requirements-for-the-teams-app.md)의 구성요소입니다.

## <a name="availability-of-bookings-in-teams"></a>Teams의 Bookings 가용성

Microsoft Bookings for Teams 데스크톱 및 웹에서 사용할 수 있습니다. 관리 센터의 앱 Teams [](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 관리 Teams 있습니다.

### <a name="control-access-to-bookings-within-your-organization"></a>조직 내에서 Bookings에 대한 액세스 제어

Bookings 앱에 액세스할 수 있는 사용자와 앱의 특정 기능에 액세스할 수 있도록 제어하는 방법에는 여러 가지가 있습니다. Microsoft Bookings 앱을 사용할 수 있도록 설정하거나 해당 앱을 사용하지 않도록 설정할 Microsoft 365 관리 센터. 또는 예약 앱 정책을 만들어 사용자가 Bookings 일정을 만들 수 있도록 허용할 수 있습니다. Microsoft [Bookings에 대한 액세스 권한을 참조합니다](/microsoft-365/bookings/get-access).

선택한 사용자를 위해 Bookings 앱을 고정하는 Teams 앱 설정 정책을 [만들 수도 있습니다](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>권장 모임 정책 설정

Bookings에 대한 최상의 환경을 사용하도록 설정하려면 Teams 모임 정책을 만들어 조직의 모든 사람을 자동으로 인정하고 해당 정책을  직원에게 할당합니다. 이 정책을 통해 직원이 약속에 자동으로 참가하고 외부 참석자에 대한 로비 환경을 사용하도록 설정할 수 있습니다. 모임에 자동으로 참석을 인정하는 [방법을 참조하세요](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>선택적 직원 승인 설정

Bookings가 일정 가용성 정보를 공유하기 전에 다른 사람이 예약을 예약하기 전에 직원에게 옵트인을 요구할 수 있습니다.

이 설정을 사용하도록 설정하려면  \> Microsoft 365 관리 센터 설정 **설정** \> **다음 예약을** **선택합니다**.

이 설정이 설정되어 있는 경우 직원은 예약 일정에 대한 멤버 자격을 승인해야 하는 전자 메일을 수신합니다.  

이 기능은 점차적으로 Microsoft 365 및 Office 365 고객을 대상으로 전 세계에 배포되고 있습니다. 사용자 환경에서 아직 모든 옵션을 사용할 수 없는 경우 곧 다시 확인하세요.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Bookings 사서함을 설정할 때 기본 도메인 변경

Bookings 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인이 사용됩니다. 그러나 기본 도메인은 외부 받는 사람에게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 예를 들어 초대가 스팸으로 플래그를 지정하고 받는 사람의 정크 폴더로 이동될 수 있으므로 받는 사람이 초대를 볼 수 없습니다.

Bookings 사서함을 만들기 전에 기본 도메인을 변경하는 것이 좋습니다. 도메인 [FAQ를 참조합니다](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Bookings 사서함을 만들고 나서 기본 도메인을 변경해야 하는 경우 PowerShell을 사용 합니다.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

사서함 cmdlet 설정에 대한 [PowerShell](/powershell/module/exchange/mailboxes/set-mailbox) 설명서를 참조하세요.

> [!NOTE]
> 하이브리드 구성을 사용하는 Exchange 기본 도메인을 변경할 때 Exchange Exchange Online 메일 흐름을 철저히 테스트하는 것이 좋습니다.

## <a name="send-feedback"></a>피드백 보내기

다음에 대한 의견을 보내주세요.

* 사용자 환경 또는 사용 편의성
* 기능 간격 또는 누락된 기능
* 버그 또는 문제
  
피드백을 보내기 위해 왼쪽  탐색 Teams 아래쪽에 있는 도움말 옵션을 선택한 다음 모든 문제에 대한 문제 보고 **를 선택합니다.**  피드백 보고서의 시작부에 "Bookings"에 대한 피드백을 보내고 있으므로 예약 문제를 쉽게 식별할 수 있습니다.

## <a name="related-articles"></a>관련 기사

[모바일 브라우저에서 가상 Teams 조인 환경 관리](expand-teams-across-your-org/mobile-browser-join.md)


  [최종 사용자를 위한 Bookings 설명서](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
