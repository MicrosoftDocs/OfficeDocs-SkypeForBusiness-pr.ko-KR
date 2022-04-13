---
title: 'Microsoft Teams용 제로 트러스트 보안 가이드: 공유 컴퓨터에서 Teams 안전하게 사용하기'
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 작업 공간의 공유 컴퓨터에서 Microsoft Teams를 안전하게 사용하기 위한 제로 트러스트 지침입니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83fc071aa50ed076fc2a6798cfaee9d4770a36a5
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817679"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>공유 컴퓨터에서 Microsoft Teams 를 안전하게 사용

가능한 경우 *권장* 기업은 클라이언트 디바이스에 제로 트러스트 접근 방식을 사용하여 디바이스 관리 기능, 디바이스 상태 점검 및 정책 시행, 디바이스 수준 암호화 및 기타 보안 기능을 사용할 수 있습니다.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="명시적 검증, 최소 권한, 위반 가정(핵심 제로 트러스트 원칙)을 파란색 원으로 표시하는 제로 트러스트 그림":::

관리자는 검증, 최소 권한을 주장하고 사용자와 데이터 모두에 대한 위험을 최소화하는 조치로 이어지는 표준인 타협을 *가정* 함으로써 안전한 조건을 만들 수 있습니다.

> [!TIP]
> 제로 트러스트 원리에 대한 자세한 내용은 [ 이 비디오](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)를 참조하시기 바랍니다.

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>공용 컴퓨터에서 Microsoft Teams를 안전하게 사용하기 위한 팁

모든 시나리오에서 이것이 가능하거나 실용적이지 않을 수 있다는 점을 인식한 보안 관리자는 공유 컴퓨터 또는 관리되지 않는 장치의 Teams를 최대한 사용하기 위한 지침을 따르는 것이 중요합니다.

가능한 한 신속하게 지침을 준수하도록 계획을 수립해야 합니다.

1. 운영 체제 플랫폼 보안 기능 활용
    1. 운영 체제가 운영 체제 제공자의 자동 업데이트를 설치하도록 구성되어 있는지 확인합니다(Microsoft 시스템의 경우 [**Windows 업데이트**](https://support.microsoft.com/help/12373/windows-update-faq)를 통해 이 작업을 수행할 수 있습니다). 
    1. [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview)와 같은 장치 암호화 기능이 활성화되어 있고 장치에 액세스하는 데 사용되는 키가 보호되어 있는지 확인합니다. 대부분의 최신 [**Windows 10 장치는 bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)를 지원합니다. 
    1. 디바이스에서 [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)에서 제공하는 것과 같은 바이러스 백신 기능을 사용합니다.
    1. 시스템의 각 사용자마다 [별도 사용자 계정](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)을 사용하는 것이 좋습니다.
    1. 비관리 기능(예: 웹 검색, 팀 실행 등)에 대해 관리자 권한을 부여하거나 사용하지 *않습니다*.

위의 지침을 충족할 수 없는 경우 다른 브라우저 보안 모범 사례를 사용하는 것이 좋습니다.

1. 브라우저 보안 기능을 적용합니다.
    1. 개인 검색 세션을 사용하여 디스크에 유지되는 데이터 및 기록을 최소화합니다. 예를 들어 [Microsoft Edge의 inPrivate 브라우징](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Google Chrome의 시크릿 브라우징](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) 또는 비공개 브라우징을위한 특정 브라우저 기능을 사용합니다.
    1. 비공개 검색을 *기본값* 으로 사용하도록 시스템 동작을 변경하는 것이 좋습니다.

2. 다운로드 가능한 Teams 클라이언트가 아닌 [Teams 웹 앱](https://teams.microsoft.com)(*웹* 클라이언트라고도 함)을 찾아서 사용합니다.

3. 공유 시스템 사용을 마쳤으면 다음을 수행해야 합니다.
    1. [Teams에서 로그아웃](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)
    1. 모든 브라우저 탭과 창을 닫습니다.
    1. 장치에서 로그아웃합니다.

위의 항목은 모든 사례를 다루는 종합 모범 사례 또는 보안 제어 목록이 아니며, 사용자 환경에서 추가로 작업을 수행해야 할 수 있습니다(예: 보안 관리자는 [Office 365용 Microsoft Defender 플랜 1 또는 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide)가 있는 경우 Teams에 안전한 링크 또는 안전한 첨부 파일을 사용하도록 선택할 수 있습니다). 하지만 공유 장치에서 Teams를 사용하기 위한 지침을 작성할 때 이러한 지침을 사용하여 시작할 수 있습니다.

## <a name="more-information"></a>추가 정보

[구성 관리자의 BitLocker](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[Intune의 Windows 10용 BitLocker](/mem/intune/protect/encrypt-devices)

[Intune의 끝점 보안](/mem/intune/protect/endpoint-security)

Windows 보안에서 Microsoft Defender 바이러스 백신을 [사용](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)하고 [검사를 실행](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)합니다.

[Microsoft Defender 보안 센터 문서](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Teams 웹 클라이언트/teams 웹 앱](./get-clients.md#browser-client)

[보안 및 Microsoft Teams](./teams-security-guide.md)
