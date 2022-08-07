---
title: Microsoft Teams 룸 프리미엄 관리되는 서비스에 Teams 룸 디바이스 등록
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 룸 프리미엄 관리되는 서비스에 Microsoft Teams 룸 계정을 등록하는 방법에 대해 알아봅니다.
f1keywords: ''
ms.openlocfilehash: f721406381e1eb99584563473196893bc21cf39b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271003"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Microsoft Teams 룸 프리미엄 관리되는 서비스에 디바이스 등록

Teams 룸 Premium 관리 서비스에 Microsoft Teams 룸 디바이스를 등록하려면 관리 서비스 관리자에게 하나 이상의 사용자를 할당한 다음 해당 사용자를 사용하여 등록 단계를 완료해야 합니다.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>관리 서비스 관리자 역할에 사용자 할당

다음 단계를 완료하여 사용자를 관리 서비스 관리자 역할에 할당합니다.

1. Microsoft 365 관리 센터 로그인하는 데 사용한 것과 동일한 관리자 권한으로 [Teams 룸 Premium Portal](https://portal.rooms.microsoft.com/)에 로그인합니다.
2. **설정 설정** >  > **역할** 로 이동한 다음 **관리 서비스 관리자** 를 선택합니다.
3. **관리 서비스 관리자** 에서 **할당 탭을** 선택한 다음 **추가** 를 선택합니다.
4. 마법사에 따라 할당 이름을 지정하고 할당에 추가할 사용자를 선택합니다. 할당은 모든 회의실 및 회의실 그룹에 적용됩니다.
5. 할당 마법사의 끝에서 할당 **추가** 를 선택합니다.

관리 서비스 관리자 역할이 할당된 사용자는 Teams 룸 Premium 관리 서비스 포털의 일상적인 관리 및 모니터링을 담당합니다.

사용자를 관리 서비스 관리자 역할에 할당한 후 [Teams 룸 디바이스 등록](enroll-a-device.md)을 계속하여 관리되는 서비스 포털에 Teams 룸 디바이스를 추가합니다.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
