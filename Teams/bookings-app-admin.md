---
title: Microsoft 팀 및 예약 앱을 사용한 가상 방문
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
ms.reviewer: ''
description: 예약 앱을 사용 하 여 Microsoft 팀 및 가상 방문
ms.openlocfilehash: 684c442765b868ca96e9d1bf243817f9378f0b5d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790620"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft 팀 및 예약 앱을 사용한 가상 방문

Microsoft 팀의 예약 앱은 의료 방문, 재무 consultations, 인터뷰, 고객 지원팀, 교육 office 시간 등의 사용자 및 가상 약속을 간단히 예약할 수 있는 방법을 제공 합니다.

스케줄러는 여러 부서 및 교직원 일정을 관리할 수 있으며, 단일 환경에서 내부 및 외부 참석자와 통신 하는 것도 가능 합니다. 가상 약속 자체는 강력한 videoconferencing 기능을 제공 하는 Microsoft 팀 모임을 통해 유지 됩니다.

> [!NOTE]
> 스케줄러만 팀에 예약 앱을 설치 해야 합니다. 가상 약속을 수행 하거나 참여 하는 직원은 앱이 필요 하지 않습니다. 이는 단순히 Outlook 또는 팀 일정 또는 예약 확인 전자 메일의 링크를 통해 약속을 참가할 수 있습니다.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>팀에서 예약 앱을 사용 하기 위한 필수 구성 요소

- Exchange 사서함이 Exchange Online에 있어야 합니다. 온-프레미스 Exchange Server 사서함은 지원 되지 않습니다.

- 조직의 Microsoft 예약이 설정 되어 있어야 합니다.

- 사용자에 게 적절 한 라이선스가 있어야 합니다. Office 365 A3, A5, E3, E5, Microsoft 365 Business Standard, A3, A5, E3, E5도 지원 됩니다.

- 예약 앱의 모든 사용자와 모임에 참여 하는 모든 직원에 게 팀 모임 예약을 지 원하는 라이선스가 있어야 합니다.

- 시스템은 모든 [소프트웨어 및 브라우저 필수 조건을](hardware-requirements-for-the-teams-app.md)충족 해야 합니다.

## <a name="availability-of-bookings-in-teams"></a>팀에서 예약의 가용성

데스크톱 및 웹에서 팀 용 Microsoft 예약 앱을 사용할 수 있습니다. [Microsoft 팀 내의 앱](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 및 팀 내에서 **앱 관리** 센터에서 찾을 수 있습니다.

### <a name="control-access-to-bookings-within-your-organization"></a>조직 내 예약에 대 한 액세스 제어

예약 앱에 액세스할 수 있는 사람과 앱의 특정 기능을 제어 하는 방법에는 여러 가지가 있습니다. Microsoft 365 관리 센터에서 Microsoft 예약을 설정 하거나 해제 하는 방법과 선택한 사용자가 예약 일정을 만들 수 있도록 예약 앱 정책을 만드는 방법에 대 한 자세한 내용은 [Microsoft 예약에 대 한 액세스 권한을](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)참조 하세요. 또한 [선택 된 사용자를 위해 예약 앱을 고정 하는 팀 앱 정책을 만드는](teams-app-setup-policies.md)방법에 대해 알아볼 수 있습니다.

## <a name="recommended-meeting-policy-settings"></a>권장 되는 모임 정책 설정

예약에 대 한 최상의 환경을 사용 하려면 **조직 내 모든 사용자** 를 자동으로 허용 하는 교직원 용 모임 정책을 만듭니다. 이렇게 하면 직원이 자동으로 약속에 참가 하 고 외부 참석자에 대해 로비 환경을 사용할 수 있습니다. [사람들에 게 모임에 자동으로 admitting](meeting-policies-in-teams.md#automatically-admit-people)에 대해 자세히 알아볼 수 있습니다.

### <a name="optional-staff-approvals-setting"></a>교직원 승인 설정 (선택 사항)

추가 개인 정보 설정으로, 일정 사용 가능 시간이 예약을 통해 공유 되 고 약속에 대해 예약할 수 있으려면 먼저 직원이 옵트인 하도록 선택할 수 있습니다.  

이 설정을 사용 하려면 **Microsoft 365 관리 센터** \> **설정** \> **설정** 으로 이동한 다음 **예약** 을 선택 합니다.

이 설정을 켠 상태에서 교직원은 예약 일정에 대 한 회원 가입을 승인 하 라는 전자 메일을 받게 됩니다.  

이 기능은 Microsoft 365 및 Office 365 고객에 게 전세계에 점진적으로 출시 됩니다. 현재 환경에서 모든 옵션을 아직 사용할 수 없는 경우에는 다시 확인 하세요.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>예약 사서함을 설정할 때 기본 도메인 변경

예약 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인을 사용 합니다. 그러나이 경우 외부 받는 사람에 게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 초대는 스팸으로 플래그 지정 되 고 받는 사람의 정크 메일 폴더로 이동 하므로 받는 사람에 게 초대가 표시 되지 않을 수 있습니다.

예약 사서함을 만들기 전에 기본 도메인을 변경 하는 것이 좋습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 [도메인 FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)를 참조 하세요.

예약 사서함을 이미 만든 후에 기본 도메인을 변경 해야 하는 경우 PowerShell을 사용 하 여 다음을 수행할 수 있습니다.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

자세한 내용은 [사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet에 대 한 PowerShell 설명서를 참조 하세요.

> [!NOTE]
> Exchange 하이브리드 구성을 사용 하는 경우 기본 도메인을 변경할 때 온-프레미스 Exchange 및 Exchange Online 간의 메일 흐름을 철저히 테스트 하는 것이 좋습니다.

## <a name="sending-feedback"></a>피드백 보내기

의견을 보내 주세요.

  - 사용자 환경 또는 간편한 사용
  - 기능 간격 또는 누락 된 기능
  - 버그 또는 문제
  
피드백을 보내려면 팀 왼쪽 탐색 모음의 아래쪽에 있는 **도움말** 단추를 클릭 한 다음 **모든** 문제에 대 한 **문제 보고** 를 클릭 합니다. 예약 문제를 쉽게 확인할 수 있도록 "예약"에 대 한 피드백 보고서의 시작 부분을 참고 하세요.

## <a name="related-topics"></a>관련 항목

[최종 사용자를 위한 예약 문서](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
