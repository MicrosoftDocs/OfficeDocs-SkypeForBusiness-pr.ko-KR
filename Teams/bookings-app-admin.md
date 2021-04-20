---
title: Microsoft Teams 및 Bookings 앱을 가상으로 방문
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
ms.openlocfilehash: e65e0b8c4af7397ebe0b152d2f977b2bf8cbb667
ms.sourcegitcommit: f0e5da6136656261567ffe0fa3f2fedd901209a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51891265"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams 및 Bookings 앱을 가상으로 방문

Microsoft Teams의 Bookings 앱은 의료 방문, 재무 컨설팅, 인터뷰, 고객 지원, 교육 현장 시간 등 개인 약속과 가상 약속을 예약할 수 있는 간단한 방법을 제공합니다.

스케줄러는 한 번의 경험으로 여러 부서 및 직원 일정을 관리할 수 있을 뿐만 아니라 내부 및 외부 참석자들과의 커뮤니케이션도 관리할 수 있습니다. 가상 약속 자체는 강력한 비디오 회의 기능을 제공하는 Microsoft Teams 모임을 통해 진행됩니다.

> [!NOTE]
> 스케줄러만 Teams에 Bookings 앱을 설치하면 됩니다. 직원이 가상 약속을 수행하거나 가상 약속에 참여하기 위해서는 앱이 필요하지 않습니다. Outlook 또는 Teams 일정이나 예약 확인 전자 메일에 있는 링크에서 약속에 참여할 수 있습니다.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Teams에서 Bookings 앱을 사용하기 위한 필수 구성 요소

- Exchange 사서함은 Exchange Online에 있어야 합니다. 온-프레미스 Exchange Server 사서함은 지원되지 않습니다.

- 조직에서 Microsoft Bookings가 켜져 있어야 합니다.

- 사용자에게 적절한 라이선스가 있어야 합니다. Office 365 A3, A5, E3 및 E5뿐만 아니라 Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3 및 E5가 지원됩니다.

- Bookings 앱의 모든 사용자와 모임에 참여하는 모든 직원에게 Teams 모임 예약을 지원하는 라이선스가 있어야 합니다.

- 시스템이 모든 [소프트웨어 및 브라우저 필수 요구 사항](hardware-requirements-for-the-teams-app.md)을 충족해야 합니다.

## <a name="availability-of-bookings-in-teams"></a>Teams의 Bookings 가용성

Teams용 Microsoft Bookings 앱은 데스크톱 및 웹에서 사용할 수 있습니다. [Microsoft Teams 내의 앱](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 및 **Teams 관리 센터 내의 앱 관리** 에서 찾을 수 있습니다..

### <a name="control-access-to-bookings-within-your-organization"></a>조직 내에서 Bookings에 대한 액세스 제어

Bookings 앱에 액세스할 수 있는 사용자와 앱의 특정 기능에 액세스할 수 있도록 제어하는 방법에는 여러 가지가 있습니다. Microsoft 365 관리 센터에서 Microsoft Bookings를 설정하거나 해제하는 방법과 선택한 사용자가 Bookings 일정을 만들 수 있도록 Bookings 앱 정책을 만드는 방법에 대한 자세한 내용은 [Microsoft Bookings에 액세스](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)를 참조하세요. 또한 [선택된 사용자를 위해 Bookings 앱을 고정하는 Teams 앱 정책을 만드는](teams-app-setup-policies.md) 방법에 대해서도 배울 수 있습니다.

## <a name="recommended-meeting-policy-settings"></a>권장 모임 정책 설정

Bookings에서 최상의 환경을 사용하려면 직원 모임 정책을 만들어 **조직의 모든 사용자** 를 자동으로 허용합니다. 이렇게 하면 직원이 자동으로 약속에 참여하고 외부 참석자를 위한 대기실 환경을 사용할 수 있습니다. [사용자가 모임에 참석하도록 자동으로 허용](meeting-policies-participants-and-guests.md#automatically-admit-people)하는 것에 대한 내용도 배울 수 있습니다.

### <a name="optional-staff-approvals-setting"></a>선택적 직원 승인 설정

추가 개인 정보 설정에서는 직원에게 예약 가능 여부 정보가 Bookings를 통해 공유되기 전에 그리고 약속을 예약하기 전에, 직원에게 옵트인(opt in)을 요구할 수 있습니다.  

이 설정을 사용하려면 **Microsoft 365 관리 센터** \> **설정** \> **설정** 으로 이동한 다음, **Bookings** 를 선택합니다.

이 설정을 켜면 직원은 예약 일정에 대한 멤버십을 승인할지 묻는 전자 메일을 받게 됩니다.  

이 기능은 점차적으로 Microsoft 365 및 Office 365 고객을 대상으로 전 세계에 배포되고 있습니다. 환경에서 아직 모든 옵션을 사용할 수 없는 경우 곧 다시 확인해 봐야 합니다.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Bookings 사서함을 설정할 때 기본 도메인 변경

Bookings 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인이 사용됩니다. 그러나 외부의 받는 사람에게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 초대장이 스팸으로 플래그가 지정될 수 있으며 받는 사람의 정크 폴더로 이동되어 받는 사람이 초대장을 못 볼 수 있습니다.

Bookings 사서함을 만들기 전에 기본 도메인을 변경하는 것이 좋습니다. 이 작업을 하는 방법에 대한 자세한 내용은 [도메인 FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)를 참조하세요.

Bookings 사서함을 이미 만든 후 기본 도메인을 변경해야 하는 경우 PowerShell을 사용하여 변경할 수 있습니다.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

자세한 내용은 [사서함 설정](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet에 대한 PowerShell 설명서를 참조하세요.

> [!NOTE]
> Exchange 하이브리드 구성을 사용하는 경우 기본 도메인을 변경할 때온-프레미스 Exchange와 Exchange Online 간의 메일 흐름을 철저히 테스트하는 것이 좋습니다.

## <a name="sending-feedback"></a>피드백 보내기

다음에 대한 의견을 보내주세요.

  - 사용자 환경 또는 사용 편의성
  - 기능 간격 또는 누락된 기능
  - 버그 또는 문제
  
사용자 의견을 보내려면 Teams 왼쪽 탐색 모음 아래 쪽에 있는 **도움말** 단추를 클릭한 다음 **모든** 문제에 대한 **문제 보고** 를 클릭하세요. 피드백 보고서 시작 부분에 "Booking"에 대한 피드백이라는 점을 표시하여 Booking 문제를 쉽게 식별하도록 할 수 있습니다.

## <a name="related-topics"></a>관련 주제


  [최종 사용자를 위한 Bookings 설명서](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)