---
title: 관리 Teams 룸 서비스에 Microsoft Teams 룸 프리미엄 디바이스 등록
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 관리되는 서비스에 Microsoft Teams 룸 계정을 등록하는 Microsoft Teams 룸 프리미엄 대해 자세히 알아보습니다.
f1keywords: ''
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766971"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>관리되는 Microsoft Teams 룸 프리미엄 디바이스 등록

관리되는 Microsoft Teams 룸 디바이스를 Teams 룸 Premium 관리 서비스 관리자에게 한 사용자를 할당한 다음 해당 사용자를 사용하여 등록 단계를 완료해야 합니다.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>관리 서비스 관리자 역할에 사용자 할당

다음 단계를 완료하여 Managed Service Administrator 역할에 사용자를 할당합니다.

1. Teams 룸 Premium 로그인하는 [](https://portal.rooms.microsoft.com/) 데 사용한 관리자 권한과 동일한 관리자 권한으로 Microsoft 365 관리 센터.
2. 역할 설정 **설정** 관리 서비스  >    >   **관리자를 선택합니다.**
3. **관리 서비스 관리자에서** 과제 **탭을** 선택한 다음 추가를 **선택합니다.**
4. 마법사를 따라 과제의 이름을 지정하고 추가해야 하는 사용자를 선택합니다. 과제는 모든 회의실 및 회의실 그룹에 적용됩니다.
5. 과제 마법사의 끝에서 과제 추가 **를 선택합니다.**

관리 서비스 관리자 역할이 할당된 사용자는 관리되는 서비스 포털의 매일 관리 및 모니터링을 Teams 룸 Premium 책임이 있습니다.

관리 서비스 관리자 역할에 사용자를 할당한 후 디바이스 [](#enroll-a-teams-rooms-device) 등록 섹션을 계속 Teams 룸 서비스 포털에 디바이스를 추가합니다.

## <a name="enroll-a-teams-rooms-device"></a>디바이스 Teams 룸 등록

 관리되는 Teams 룸 Premium 디바이스를 등록하려면 디바이스 소프트웨어 설치 모니터링 [을 참조하세요.](monitor-software-installation-guide.md)

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
