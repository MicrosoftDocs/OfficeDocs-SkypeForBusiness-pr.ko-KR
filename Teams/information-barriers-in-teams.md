---
title: Microsoft Teams
description: 이 문서에서는 이 문서의 정보 장벽이 Microsoft Teams 및 이러한 장벽이 사용자에 미치는 영향을 Teams.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e829cb078ee334c36c69aa489c9dec6f3c5eaa10
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007788"
---
# <a name="information-barriers-in-microsoft-teams"></a>Microsoft Teams

IB(정보 장벽)는 관리자가 개인 또는 그룹이 서로 통신하지 못하도록 구성할 수 있는 정책입니다. 예를 들어 한 부서에서 다른 부서와 공유하지 말아야 하는 정보를 처리하는 경우 IB가 유용합니다. 또한 그룹이 격리되거나 그룹 외부의 모든 사용자와 통신하지 못하게 하는 경우 IB가 유용합니다.

이러한 Microsoft Teams 정보 장벽은 다음과 같은 종류의 무단 공동 작업을 결정하고 방지할 수 있습니다.

- 팀 또는 채널에 사용자 추가
- 팀 또는 채널 콘텐츠에 대한 사용자 액세스
- 1:1 및 그룹 채팅에 대한 사용자 액세스
- 모임에 대한 사용자 액세스
- 검색 및 검색을 방지하면 사용자가 사람 선택기에서 표시되지 않습니다.

>[!NOTE]
>- 테넌트에서 정보 장벽 그룹을 만들 수 없습니다.
>- 봇, Azure Active Directory(Azure AD) 앱, 활동 피드 알림을 보내는 API 및 사용자를 추가하는 일부 API는 버전 1에서 지원되지 않습니다.
>- 개인 채널은 구성하는 정보 장벽 정책을 준수합니다.
>- 웹 사이트에 연결된 SharePoint 장벽에 대한 지원에 대한 자세한 Teams 사이트와 연결된 세그먼트를 Microsoft Teams [참조하세요.](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="background"></a>배경

B의 기본 드라이버는 금융 서비스 업계에서 온 것입니다. 금융 산업 규제[기관(FINRA)은]( https://www.finra.org)구성원 회사 내에서 B 및 이해 상충을 검토하고 이러한 충돌 관리에 대한 지침을 제공합니다(FINRA 2241, 부채 조사 규제 [고지 15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)

그러나 B를 도입한 이후 다른 많은 영역에서 유용하게 사용할 수 있습니다. 다른 일반적인 시나리오는 다음과 같습니다.

- **교육:** 한 학교의 학생은 다른 학교의 학생에 대한 연락처 세부 정보를 볼 수 없습니다.
- **법률**: 한 클라이언트의 변호사가 획득한 데이터의 기밀성을 유지하고 다른 클라이언트를 나타내는 동일한 회사에 대한 변호사가 액세스하지 못하게 합니다.
- **정부**: 부서 및 그룹 전체에서 정보 액세스 및 제어가 제한됩니다.
- **Professional** 서비스: 회사의 사용자 그룹은 고객 참여 중에 게스트 액세스를 통해 클라이언트 또는 특정 고객과만 채팅할 수 있습니다.

예를 들어 Enrico는 금융 부문에 속하고 Pradeep은 재무 고문 세그먼트에 속합니다. Enrico와 Pradeep은 조직의 IB 정책이 이러한 두 세그먼트 간의 통신 및 공동 작업을 차단하기 때문에 서로 통신할 수 없습니다. 그러나 Enrico 및 Pradeep는 HR에서 Lee와 통신할 수 있습니다.

![세그먼트 간의 통신을 방지하는 정보 장벽을 보여주는 예제입니다.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>정보 장벽을 사용하는 경우

다음과 같은 상황에서 B를 사용할 수 있습니다.

- 팀은 특정 다른 팀과 데이터를 통신하거나 공유하지 못하도록 방지해야 합니다.
- 팀은 팀 외부의 다른 사용자와 데이터를 통신하거나 공유하지 말아야 합니다.

정보 장벽 정책 평가 서비스는 통신이 IB 정책을 준수하는지 여부를 결정합니다.

## <a name="managing-information-barrier-policies"></a>정보 장벽 정책 관리

IB 정책은 PowerShell cmdlet을 Microsoft 365 SCC(준수 센터)에서 관리됩니다. 자세한 내용은 정보 [장벽에 대한 정책 정의를 참조하세요.](/office365/securitycompliance/information-barriers-policies)

>[!IMPORTANT]
>정책을 설정하거나 정의하기 전에 범위가 설정된 디렉터리 검색을 Microsoft Teams. 정보 장벽에 대한 정책을 설정하거나 정의하기 전에 범위가 지정된 디렉터리 검색을 사용하도록 설정한 후 적어도 몇 시간 정도 기다릴 수 있습니다. 자세한 내용은 정보 장벽 [정책 정의를 참조하세요.](/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>정보 장벽 관리자 역할

IB 준수 관리 역할은 IB 정책을 관리할 책임이 있습니다. 이 역할에 대한 자세한 내용은 규정 준수 [센터의 Microsoft 365 참조하세요.](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>정보 장벽 트리거

IB 정책은 다음 이벤트가 Teams 활성화됩니다.

- **구성원이** 팀에 추가됩니다. 팀에 사용자를 추가할 때마다 사용자의 정책이 다른 팀 구성원의 IB 정책에 대해 평가되어야 합니다. 사용자가 성공적으로 추가된 후 사용자는 추가 확인 없이 팀의 모든 함수를 수행할 수 있습니다. 사용자의 정책이 팀에 추가되지 못하도록 차단하는 경우 사용자가 검색에 표시되지 않습니다.

    ![팀에 추가할 새 멤버를 검색하고 일치하지 않습니다.](media/information-barriers-add-members.png)

- **새 채팅이 요청됩니다.** 사용자가 하나 이상의 다른 사용자와 새 채팅을 요청할 때마다 채팅은 IB 정책을 위반하지 않는지 확인하도록 평가됩니다. 대화가 IB 정책을 위반하는 경우 대화가 시작되지 않습니다.

    다음은 1:1 채팅의 예입니다.

    ![1:1 채팅에서 차단된 통신을 보여주는 스크린샷.](media/information-barriers-one-one-chat.png)

    다음은 그룹 채팅의 예입니다.

    ![그룹 채팅을 보여주는 스크린샷.](media/information-barriers-group-chat.png)

- **사용자가** 모임에 참가하도록 초대됩니다. 사용자가 모임에 참가하도록 초대하면 사용자에게 적용되는 IB 정책이 다른 팀 구성원에게 적용되는 IB 정책에 대해 평가됩니다. 위반이 있는 경우 사용자는 모임에 참가할 수 없습니다.

    ![모임에서 차단된 사용자를 보여주는 스크린샷입니다.](media/information-barriers-meeting.png)

- **두 개** 이상의 사용자 간에 화면이 공유됩니다. 사용자가 다른 사용자와 화면을 공유하는 경우 공유가 다른 사용자의 IB 정책을 위반하지 않는지 평가해야 합니다. IB 정책을 위반하는 경우 화면 공유는 허용되지 않습니다.

    정책이 적용되기 전에 화면 공유의 예는 다음과 같습니다.

    ![사용자 채팅을 보여주는 스크린샷.](media/ib-before-screen-share-policy.png)

    정책이 적용된 후 화면 공유의 예는 다음과 같습니다. 화면 공유 및 통화 아이콘은 표시되지 않습니다.

    ![차단된 설정이 있는 사용자 char을 보여주는 스크린샷입니다.](media/ib-after-screen-share-policy.png)

- **사용자가** 전화 통화를 Teams : 사용자가 VOIP를 통해 다른 사용자 또는 사용자 그룹에 음성 통화를 시작할 때마다 호출이 다른 팀 구성원의 IB 정책을 위반하지 않는지 확인하도록 평가됩니다. 위반이 있는 경우 음성 통화가 차단됩니다.

- **게스트 Teams**: IB 정책도 Teams 적용됩니다. 조직의 전역 주소 목록에서 게스트를 검색해야 하는 경우 그룹에서 게스트 [액세스 Microsoft 365 참조하세요.](/microsoft-365/admin/create-groups/manage-guest-access-in-groups) 게스트를 검색할 수 있는 경우 [IB 정책을 정의할 수 있습니다.](/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>정책 변경이 기존 채팅에 미치는 영향

IB 정책 관리자가 정책을 변경하거나 사용자의 프로필 변경(예: 작업 변경)으로 인해 정책 변경이 활성화된 경우 정보 장벽 정책 평가 서비스는 자동으로 구성원을 검색하여 팀의 구성원 자격이 정책을 위반하지 않도록 합니다.

사용자 간에 기존 채팅 또는 다른 통신이 있으며 새 정책이 설정되거나 기존 정책이 변경된 경우 서비스는 기존 통신을 평가하여 통신이 계속 발생할 수 있는지 확인합니다. 

- **1:1** 채팅: 두 사용자 간의 통신이 더 이상 허용되지 않습니다(통신을 차단하는 정책의 한 사용자 또는 둘 다에게 애플리케이션으로 인하여) 추가 통신이 차단됩니다. 기존 채팅 대화는 읽기 전용이 됩니다.

    다음은 채팅이 표시되는 예제입니다.

    ![사용자 채팅을 보여주는 스크린샷을 사용할 수 있습니다.](media/ib-before-1-1chat-policy.png)

    채팅이 비활성화되어 있는 경우를 보여주는 예제는 다음과 같습니다.

    ![사용자 채팅을 보여주는 스크린샷은 비활성화됩니다.](media/ib-after-1-1chat-policy.png)

- **그룹 채팅**: 한 사용자와 그룹 간 통신이 더 이상 허용되지 않는 경우(예: 사용자가 작업을 변경하기 때문에) 참여가 정책을 위반하는 다른 사용자와 함께 그룹 채팅에서 제거될 수 있으며 그룹과의 추가 통신은 허용되지 않습니다. 사용자는 여전히 이전 대화를 볼 수 있지만 그룹과의 새 대화를 보거나 참가할 수 없습니다. 통신을 방지하는 새 정책 또는 변경된 정책이 두 개 이상의 사용자에게 적용되는 경우 정책의 영향을 받는 사용자는 그룹 채팅에서 제거될 수 있습니다. 이전 대화를 볼 수 있습니다.

  이 예제에서는 Enrico가 조직 내의 다른 부서로 이동하여 그룹 채팅에서 제거됩니다.

  ![사용자가 제거된 그룹 채팅의 스크린샷입니다.](media/information-barriers-user-changes-job.png)

  Enrico는 더 이상 그룹 채팅에 메시지를 보낼 수 없습니다.

  ![사용자가 그룹에서 제거되어 그룹 채팅에 메시지를 보낼 수 없는 경우의 스크린샷입니다.](media/information-barriers-user-changes-job-2.png)

- **팀**: 그룹에서 제거된 모든 사용자가 팀에서 제거되고 기존 또는 새 대화를 보거나 참가할 수 없습니다.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>시나리오: 기존 채팅의 사용자가 차단됩니다.

현재 사용자는 IB 정책이 다른 사용자를 차단하는 경우 다음 시나리오를 경험합니다.

- **사람 탭**: 사용자가 사람 탭에서 차단된 사용자를 볼 **수** 없습니다.

- **사람 선택기**: 차단된 사용자는 사람 선택기에서 표시되지 않습니다.

    ![정책이 Teams 표시하지 못하도록 사용자에게 경고하는 스크린샷.](media/information-barriers-people-picker.png)

- **활동 탭**: 사용자가 차단된 사용자의 활동 탭을 방문하는 경우 게시물이 나타나지 않습니다.  (활동 **탭은** 채널 게시물만 표시하며 두 사용자 간에 공통 채널이 없습니다.)

    다음은 차단된 활동 탭 보기의 예입니다.

    ![차단된 활동 탭을 보여주는 스크린샷입니다.](media/ib-after-activity-tab-policy.png)

- **오그 차트**: 사용자가 차단된 사용자가 나타나는 오그 차트에 액세스하는 경우 차단된 사용자가 오그 차트에 나타나지 않습니다. 대신 오류 메시지가 표시됩니다.

- **사람 카드:** 사용자가 대화에 참여하고 사용자가 나중에 차단된 경우 차단된 사용자의 이름을 마우스로 를 때 다른 사용자가 사람 카드 대신 오류 메시지가 표시됩니다. 카드에 나열된 작업(예: 통화 및 채팅)은 사용할 수 없습니다.

- **추천 연락처:** 차단된 사용자가 제안된 연락처 목록에 나타나지 않습니다(새 사용자에게 나타나는 초기 연락처 목록).

- **채팅 연락처:** 사용자가 채팅 대화 목록에서 차단된 사용자를 볼 수 있지만 차단된 사용자가 식별됩니다. 사용자가 차단된 사용자에서 수행할 수 있는 유일한 작업은 삭제하는 것입니다. 또한 사용자는 해당 대화를 선택하여 과거 대화를 볼 수 있습니다.

- **통화 연락처:** 사용자는 통화 연락처 목록에서 차단된 사용자를 볼 수 있지만 차단된 사용자를 식별합니다. 사용자가 블록에서 수행할 수 있는 유일한 작업은 해당 사용자를 삭제하는 것입니다.

    다음은 통화 연락처 목록에서 차단된 사용자의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![사용자 채팅을 보여주는 스크린샷입니다.](media/ib-before-chat-contacts-policy.png)

    다음은 통화 콘텐츠 목록의 사용자에 대해 사용하지 않도록 설정되는 채팅의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![채팅에서 차단된 사용자를 보여주는 스크린샷입니다.](media/ib-after-chat-contacts-policy.png)

- **Skype** Teams : 마이그레이션에서 비즈니스용 Skype Teams IB 정책에 의해 차단된 모든 사용자도 마이그레이션할 Teams. 그런 다음 위에서 설명한 대로 해당 사용자를 처리합니다.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams 및 SharePoint 사이트

팀이 만들어지면 파일 SharePoint 사이트가 프로비전되어 파일 Microsoft Teams 연결됩니다. 이 사이트 및 파일에는 기본적으로 SharePoint 정책이 적용되지 않습니다. 정보 장벽을 SharePoint OneDrive 사용 문서와 함께 정보 장벽 사용의 지침 및 [SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) 따르세요.

## <a name="information--barrier-modes-and-teams"></a>정보 장벽 모드 및 Teams

정보 장벽 모드는 팀에 추가하거나 제거할 수 있는 사용자 강화에 도움이 됩니다. 정보 장벽을 사용하여 Teams IB 모드가 지원됩니다.

- **열기**: 이 구성은 정보 장벽을 사용하도록 설정하기 전에 프로비전된 모든 기존 그룹에 대한 기본 IB 모드입니다. 이 모드에서는 적용할 수 있는 IB 정책이 없습니다.
- **암시적:** 이 구성은 팀이 정보 장벽을 사용하도록 설정한 후 프로비전된 경우 기본 IB 모드입니다. 암시적 모드를 사용하면 그룹에서 호환되는 모든 사용자를 추가할 수 있습니다.

Microsoft 365 정보 장벽 정책을 활성화하기 전에 만든 그룹은 기본적으로 자동으로 열기 *모드로* 설정됩니다. 테넌트에서 IB 정책을 활성화하면 그룹 및 사이트를 다시 평가하고 비준수 사용자가 이러한 그룹 및 사이트에서 자동으로 제거되는 모드를 업데이트해야 합니다. 조직의 규정 준수  요구 사항을 충족하도록 기존 Teams 그룹에서 열기 모드 구성을 변경해야 하는 경우 팀 팀에 연결된 SharePoint [IB](/sharepoint/information-barriers.md#view-and-manage-IB-mode-as-an-administrator-with-SharePoint-PowerShell) 모드를 업데이트해야 Teams 합니다.

세그먼트에 사용할 모드에 해당하는 *InformationBarrierMode* 매개 변수와 함께 *Set-UnifiedGroup* cmdlet을 사용합니다. *InformationBarrierMode* 매개 변수에 대해 허용되는 값 목록은 *열기* 및 *암시적입니다.*

예를 들어 특정  그룹에 대한 암시적 모드를 Microsoft 365 다음 PowerShell 명령을 사용하게 됩니다.

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

>[!NOTE]
>전역 관리자가 암시적에 연결된 기존 Microsoft 365 그룹의 IB 모드를 암시적으로 Microsoft Teams *경우* 연결된 사이트의 IB Teams 암시적 으로 업데이트해야 *합니다.* 자세한 내용은 정보 장벽 시작 ] 을 [참조하세요.](/microsoft-365/compliance-information-barriers.md#information-barriers-modes-preview)

사용자가 그룹에서 자동으로 제거되는 방법에 대한 자세한 내용은 정보 장벽 준수 도우미(미리 [보기) 문서를 참조하세요.](/sharepoint/information-barriers-compliance-assistant)

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

라이선스 및 사용 권한, 계획 및 가격 책정에 대한 자세한 내용은 보안 Microsoft 365 규정 준수에 대한 & [참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="known-issues"></a>알려진 문제

- **사용자가 모임에** 참가할 수 없습니다. IB 정책이 설정된 경우 모임 참석 제한보다 큰 경우 사용자가 모임에 참가할 [수](limits-specifications-teams.md)없습니다. 근본 원인은 IB가 사용자가 모임 채팅 로스터에 추가할 수 있는지 여부에 따라 확인하며, 해당 사용자를 모임에 추가할 수 있는 경우만 모임에 참가할 수 있도록 허용됩니다. 모임에 참가하는 사용자는 해당 사용자를 목록에 추가합니다. 따라서 모임을 다시 진행하기 위해 로스터를 빠르게 채울 수 있습니다. 채팅 로스터가 모임 참석 제한에 도달하면 [모임에](limits-specifications-teams.md)추가 사용자를 추가할 수 없습니다. 조직에서 IB를 사용하도록 설정하고 채팅 로스터가 모임에 대해 가득 차면 새 사용자(아직 참가명단에 없는 사용자)는 모임에 참가할 수 없습니다. 그러나 조직에 대해 IB를 사용하도록 설정하지 못하고 모임 채팅 로스터가 가득 차면 모임에서 채팅 옵션이 표시되지 않지만 새 사용자(아직 참석하지 않은 사용자)는 모임에 참가할 수 있습니다. 단기 솔루션은 모임 채팅 목록에서 비활성 구성원을 제거하여 새 사용자를 위한 공간을 만드는 것입니다. 그러나 나중에 모임 채팅 로스터의 크기를 늘려야 합니다.
- **사용자가 채널** 모임에 참가할 수 없습니다. IB 정책이 설정된 경우 사용자가 팀의 구성원이 아닌 경우 채널 모임에 참가할 수 없습니다. 근본 원인은 IB가 사용자가 모임 채팅 로스터에 추가할 수 있는지 여부에 따라 확인하며, 해당 사용자를 모임에 추가할 수 있는 경우만 모임에 참가할 수 있도록 허용됩니다. 채널 모임의 채팅 스레드는 Team/Channel 구성원만 사용할 수 있으며, 비회원은 채팅 스레드를 보거나 액세스할 수 없습니다. 조직에 대해 IB를 사용하도록 설정하고 팀이 아닌 구성원이 채널 모임에 참가하려고 하면 해당 사용자가 모임에 참가할 수 없습니다. 그러나 조직에서 IB를 사용하도록 설정하지 못하고 팀 구성원이 아닌 구성원이 채널 모임에 참가하려고 하면 사용자가 모임에 참가할 수 있지만 모임에 채팅 옵션이 표시되지 않습니다. 
- **조직에서 허용되는** 최대 세그먼트 수: 각 조직은 IB 정책을 구성할 때 최대 100개 세그먼트를 설정할 수 있습니다. 구성할 수 있는 정책 수에는 제한이 없습니다.
- **IB** 정책은 페더리드 사용자에 대해 작동하지 않습니다. 외부 조직과 페더전을 허용하는 경우 해당 조직의 사용자는 IB 정책에 의해 제한되지 않습니다. 조직의 사용자가 외부 페더러드 사용자가 구성한 채팅 또는 모임에 참가하는 경우 IB 정책도 조직의 사용자 간의 통신을 제한하지 않습니다.

## <a name="more-information"></a>추가 정보

- IB에 대한 자세한 내용은 정보 장벽 [을 참조하세요.](/office365/securitycompliance/information-barriers)
- IB 정책을 설정하기 위해 정보 장벽 시작 을 [참조하세요.](/office365/securitycompliance/information-barriers-policies)
- IB 정책을 편집하거나 제거하려면 정보 장벽 [정책 관리를 참조하세요.](/microsoft-365/compliance/information-barriers-edit-segments-policies)

## <a name="availability"></a>가용성

- 이 기능은 공용 클라우드에서 사용할 수 있습니다. 2021년 1월, 클라우드의 정보 장벽을 GCC 도입했습니다.
- 이 기능은 하이 및 DOD GCC 아직 사용할 수 없습니다.
