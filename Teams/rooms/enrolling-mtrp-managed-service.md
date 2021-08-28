---
title: 관리 Teams 룸 서비스에 Microsoft Teams 룸 Premium 디바이스 등록
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
description: 관리되는 서비스에 Microsoft Teams 룸 계정을 등록하는 Microsoft Teams 룸 Premium 대해 자세히 알아보습니다.
f1keywords: ''
ms.openlocfilehash: a6aa59a798e06c407c1bbde6734ec9ab3ecedcd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58637023"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>관리되는 Microsoft Teams 룸 Premium 디바이스 등록

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

관리되는 서비스에서 디바이스를 Teams 룸 Premium 단계를 완료합니다.

1. 관리 서비스 [Teams 룸 Premium](https://portal.rooms.microsoft.com/) 사용자와 함께 포털에 로그인합니다.
2. **에서 선택합니다.** 포털의 오른쪽 위 모서리에 있는 아이콘을 클릭하여 도움말 메뉴를 실행합니다. 도움말 메뉴에는 [](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) 자세한 등록 지침이 포함된 설치 가이드가 포함되어 있습니다.

    1. 설치 **가이드의** 전제요소 섹션을 검토합니다. 통신에 필요한 URL 목록에 나열된 **URL이** 방화벽의 트래픽 허용 목록에 추가되어 있는지 확인합니다.
    2. **디바이스에서 TPM(신뢰할 수 있는 설정** 모듈) 기능을 사용하도록 설정하려면 TPM 사용 섹션의 지침을 따릅니다.
    3. 프록시 게이트웨이를  사용하도록 디바이스를 구성하려면 프록시 설정 섹션의 지침에 따라 프록시 게이트웨이를 사용하도록 구성합니다.
    4. 프로세스 섹션의  지침에 따라 모니터링 에이전트 소프트웨어를 설치하고 디바이스에 자체 등록 키를 구성합니다.

3. 모니터링 에이전트 및 고유한 XML 키가 디바이스에서 구성된  후 상태 > 룸 이름 > 룸으로 이동한 다음 **등록을** **선택합니다.**

    > [!NOTE]
    > Teams 룸 서비스 관리자가 포털을 사용하여  디바이스를 등록할 때까지 디바이스가 온보링 상태로 유지됩니다.

## <a name="link-to-installation-guide"></a>설치 가이드에 연결

도움말 **메뉴는** 설치 가이드에 대한 링크를 제공합니다. [](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf)

- 룸 원격 분석이 관리 서비스로 전송될 수 있도록 제공하려면 허용 나열해야 하는 URL에 대한 지침입니다.
- 관리되는 Microsoft Teams 룸 Premium 디바이스를 등록하는 일환으로 모니터링 에이전트 및 고유한 XML 키를 적용하기 위한 지침입니다.
- 문제 해결 지침.
