---
title: Microsoft Teams의 정보 장벽
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft Teams의 정보 장벽과 Teams에 어떤 영향을 줄 수 있는가에 대해 설명하고 있습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95c3c2e854a22ff3ff74595a56f84edaaeb1c5f1
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067153"
---
# <a name="information-barriers-in-microsoft-teams"></a>Microsoft Teams의 정보 장벽

IB(정보 장벽)는 관리자가 개인 또는 그룹이 서로 통신하지 못하도록 구성할 수 있는 정책입니다. 예를 들어 한 부서에서 다른 부서와 공유하지 말아야 하는 정보를 처리하는 경우 IB가 유용합니다. IB는 그룹이 격리되거나 이 그룹 외부의 사용자와 통신하지 못하게 하는 경우 유용합니다.

> [!NOTE]
> - IB(정보 장벽) 그룹은 테넌트에서 만들 수 없습니다.
> - 봇, Azure AD(Azure Active Directory) 앱 및 일부 API를 사용하여 사용자를 추가하는 것은 버전 1에서 지원되지 않습니다.
> - 개인 채널은 사용자가 구성하는 IB 정책을 준수합니다.
> - 새로 추가: Teams에 연결된 SharePoint 사이트의 장벽 지원에 대한 자세한 내용은 Microsoft Teams 사이트와 연결된 세그먼트를 [참조하세요.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

IB 정책은 또한 검색 및 검색을 방지합니다. 통신하지 말아야 하는 다른 사용자와 통신하려는 경우 사용자 선택기에서 해당 사용자를 찾을 수 없습니다.

## <a name="background"></a>배경

BS의 기본 드라이버는 금융 서비스 업계에서 비어 있습니다. [FINRA(금융]( https://www.finra.org)산업 규제 기관)는 구성원 회사 내의 BS 및 관심 충돌을 검토하고 이러한 충돌 관리에 대한 지침을 제공합니다(FINRA 2241, Debt Research 규제 고지 [15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


그러나 BS가 도입된 이후 다른 많은 영역에서 유용하게 사용할 수 있습니다. 기타 일반적인 시나리오는 다음과 같습니다.

- 교육: 한 학교의 학생은 다른 학교의 학생에 대한 연락처 세부 정보를 볼 수 없습니다.

- 법적: 한 클라이언트의 법률가가 획득한 데이터의 기밀성을 유지 관리하고 다른 클라이언트를 나타내는 동일한 회사에 대한 법률가가 데이터에 액세스하지 못하게 합니다.

- 정부: 정보 액세스 및 제어는 부서 및 그룹에서 제한됩니다.

- 전문 서비스: 회사의 사용자 그룹은 고객 참여 중에 게스트 액세스를 통해 클라이언트 또는 특정 고객과만 채팅할 수 있습니다.

예를 들어 Enrico는 금융 세그먼트에 속하고 Pradeep은 재무 고문 세그먼트에 속합니다. Enrico와 Pradeep은 조직의 IB 정책이 이러한 두 세그먼트 간의 통신 및 공동 작업을 차단하기 때문에 서로 통신할 수 없습니다. 그러나 Enrico와 Pradeep은 HR에서 이진국과 통신할 수 있습니다.

![세그먼트 간 통신을 방지하는 정보 장벽을 보여주는 예제](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>정보 장벽을 사용하는 경우

이와 같은 상황에서 BS를 사용할 수 있습니다.

- 팀이 특정 다른 팀과 데이터를 통신하거나 공유하지 못하도록 해야 합니다.
- 팀이 팀 외부의 사용자와 데이터를 통신하거나 공유하면 안 됩니다.

정보 장벽 정책 평가 서비스는 통신이 IB 정책을 준수하는지 여부를 판단합니다.

## <a name="managing-information-barrier-policies"></a>정보 장벽 정책 관리

IB 정책은 PowerShell cmdlet을 사용하여 Microsoft 365 SCC(준수 센터)에서 관리됩니다. 자세한 내용은 정보 [장벽에 대한 정책 정의를 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> 정책을 설정하거나 정의하기 전에 Microsoft Teams에서 범위가 설정된 디렉터리 검색을 사용하도록 설정해야 합니다. 정보 장벽에 대한 정책을 설정하거나 정의하기 전에 범위가 지정된 디렉터리 검색을 사용하도록 설정한 후 몇 시간 이상 기다릴 수 있습니다. 자세한 내용은 정보 장벽 [정책 정의를 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>정보 장벽 관리자 역할

IB 규정 준수 관리 역할은 IB 정책을 관리할 책임이 있습니다. 이 역할에 대한 자세한 내용은 [Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)준수 센터의 사용 권한을 참조하세요.

## <a name="information-barrier-triggers"></a>정보 장벽 트리거

IB 정책은 다음 Teams 이벤트가 진행될 때 활성화됩니다.

- **구성원이 팀에** 추가됩니다. 사용자를 팀에 추가할 때마다 사용자 정책이 다른 팀 구성원의 IB 정책에 대해 평가되어야 합니다. 사용자가 성공적으로 추가된 후 사용자는 추가 검사 없이 팀의 모든 기능을 수행할 수 있습니다. 사용자의 정책이 팀에 추가되지 못하도록 차단하면 사용자가 검색에 표시되지 않습니다.

    ![팀에 추가할 새 구성원을 검색하고 일치하는 것을 찾을 수 없는 경우의 스크린샷](media/information-barriers-add-members.png)

- **새 채팅이 요청됩니다.** 사용자가 한명 이상의 다른 사용자와 새 채팅을 요청할 때마다 IB 정책을 위반하지 않는지 확인하도록 채팅이 평가됩니다. 대화가 IB 정책을 위반하는 경우 대화가 시작되지 않습니다.

    다음은 1:1 채팅의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![1:1 채팅에서 차단된 통신을 보여주는 스크린샷](media/information-barriers-one-one-chat.png)

    다음은 그룹 채팅의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![그룹 채팅을 보여주는 스크린샷](media/information-barriers-group-chat.png)

- **사용자가 모임에** 참가하도록 초대됩니다. 사용자가 모임에 참가하도록 초대된 경우 사용자에게 적용되는 IB 정책은 다른 팀 구성원에게 적용되는 IB 정책에 대해 평가됩니다. 위반이 있는 경우 사용자는 모임에 참가할 수 없습니다.

    ![모임에서 차단된 사용자를 보여주는 스크린샷](media/information-barriers-meeting.png)

- **화면은** 두 개 이상의 사용자 간에 공유됩니다. 사용자가 다른 사용자와 화면을 공유하는 경우 다른 사용자의 IB 정책을 위반하지 않는지 확인하려면 공유를 평가해야 합니다. IB 정책을 위반하는 경우 화면 공유가 허용되지 않습니다. 
 
    정책이 적용되기 전에 화면 공유의 예는 다음과 같습니다. 

    > [!div class="mx-imgBorder"]
    > ![사용자 채팅을 보여주는 스크린샷](media/ib-before-screen-share-policy.png)

    정책이 적용된 후 화면 공유의 예는 다음과 같습니다. 화면 공유 및 통화 아이콘이 표시되지 않습니다.

    > [!div class="mx-imgBorder"]
    > ![차단된 설정이 있는 사용자 char를 보여주는 스크린샷](media/ib-after-screen-share-policy.png)

- **사용자가 Teams에서** 전화 통화를 합니다. 사용자가 VOIP를 통해 다른 사용자 또는 사용자 그룹에 음성 통화를 시작할 때마다 통화가 다른 팀 구성원의 IB 정책을 위반하지 않는지 확인하도록 평가됩니다. 위반이 있는 경우 음성 통화가 차단됩니다.

- **Teams의 게스트** - Teams의 게스트에게도 IB 정책이 적용됩니다. 조직의 전체 주소 목록에서 게스트를 검색할 수 있도록 해야 하는 경우 [Microsoft 365 그룹에서](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)게스트 액세스 관리를 참조하세요. 게스트를 검색할 수 있는 경우 [IB 정책을 정의할 수 있습니다.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>정책 변경이 기존 채팅에 미치는 영향

IB 정책 관리자가 정책을 변경하거나 사용자 프로필 변경(예: 작업 변경)으로 인해 정책 변경이 활성화된 경우 정보 장벽 정책 평가 서비스는 구성원을 자동으로 검색하여 팀의 멤버 자격이 정책을 위반하지 않도록 합니다.

사용자 간에 기존 채팅 또는 기타 통신이 있으며 새 정책이 설정되거나 기존 정책이 변경된 경우 서비스는 기존 통신을 평가하여 통신이 계속 발생하도록 합니다. 

- **1:1 채팅** - 두 사용자 간의 통신이 더 이상 허용되지 않습니다(통신을 차단하는 정책의 한 사용자 또는 둘 다에 대한 애플리케이션 때문에) 추가 통신이 차단됩니다. 기존 채팅 대화는 읽기 전용이 됩니다. 

    다음은 채팅이 표시되는 예제입니다.

    > [!div class="mx-imgBorder"]
    > ![사용자 채팅을 사용할 수 있는 스크린샷](media/ib-before-1-1chat-policy.png)

    다음은 채팅이 비활성화된 경우를 보여주는 예입니다.

    > [!div class="mx-imgBorder"]
    > ![사용자 채팅이 비활성화되어 있는 스크린샷](media/ib-after-1-1chat-policy.png)

- **그룹 채팅** - 한 사용자와 그룹 간 통신이 더 이상 허용되지 않는 경우(예: 사용자가 작업을 변경한 경우) 사용자는 참여가 정책을 위반하는 다른 사용자와 함께 그룹 채팅에서 제거될 수 있으며 그룹과의 추가 통신은 허용되지 않습니다. 사용자는 여전히 이전 대화를 볼 수 있지만 그룹과의 새 대화를 보거나 참가할 수 없습니다. 통신을 차단하는 새 정책 또는 변경된 정책이 두 개 이상의 사용자에게 적용되는 경우 정책의 영향을 받는 사용자는 그룹 채팅에서 제거될 수 있습니다. 이전 대화는 계속 볼 수 있습니다.

  이 예제에서는 Enrico가 조직 내의 다른 부서로 이동하여 그룹 채팅에서 제거되었습니다.

  ![사용자가 제거된 그룹 채팅의 스크린샷](media/information-barriers-user-changes-job.png)

  Enrico는 더 이상 그룹 채팅에 메시지를 보낼 수 없습니다.

  ![사용자가 그룹에서 제거되어 그룹 채팅에 메시지를 보낼 수 없는 경우의 스크린샷](media/information-barriers-user-changes-job-2.png)

- **팀** - 그룹에서 제거된 모든 사용자는 팀에서 제거되고 기존 또는 새 대화를 보거나 참가할 수 없습니다.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>시나리오: 기존 채팅의 사용자가 차단됩니다.

현재 사용자는 IB 정책이 다른 사용자를 차단하는 경우 다음과 같은 시나리오를 경험합니다.

- **사용자 탭** - 사용자 탭에서 차단된 사용자를 볼 **수** 없습니다.

- **사람 선택** - 차단된 사용자는 사용자 선택에 표시되지 않습니다.

    ![정책이 다른 사용자의 정보를 표시하지 못하도록 사용자에게 알리는 Teams의 스크린샷](media/information-barriers-people-picker.png)
    
- **활동 탭** - 사용자가 차단된 사용자의 활동 탭을 방문하는 경우 게시물이 나타나지 않습니다.  (활동 **탭에는** 채널 게시물만 표시하며 두 사용자 간에 공통 채널이 없습니다.)

    다음은 차단된 활동 탭 보기의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![차단된 활동 탭을 보여주는 스크린샷](media/ib-after-activity-tab-policy.png)


- **Org 차트** - 사용자가 차단된 사용자가 나타나는 오그라드 차트에 액세스하는 경우 차단된 사용자가 설정 차트에 나타나지 않습니다. 대신 오류 메시지가 표시됩니다.

- **인원** 카드 - 사용자가 대화에 참여하고 사용자가 나중에 차단된 경우 차단된 사용자의 이름 위에 마우스를 다가 사용자 카드 대신 다른 사용자에게 오류 메시지가 표시됩니다. 카드에 나열된 작업(예: 통화 및 채팅)은 사용할 수 없습니다.

- **추천 연락처** - 차단된 사용자가 제안된 연락처 목록(새 사용자에 대해 나타나는 초기 연락처 목록)에 나타나지 않습니다.

- **채팅 연락처** - 사용자는 채팅 연락처 목록에서 차단된 사용자를 볼 수 있지만 차단된 사용자가 식별됩니다. 사용자가 차단된 사용자에 수행할 수 있는 유일한 작업은 해당 사용자를 삭제하는 것입니다. 또한 사용자는 해당 사용자를 클릭하여 과거 대화를 볼 수 있습니다.

- **통화 연락처** - 사용자는 통화 연락처 목록에서 차단된 사용자를 볼 수 있지만 차단된 사용자가 식별됩니다. 사용자가 차단에서 수행할 수 있는 유일한 작업은 해당 사용자를 삭제하는 것입니다.

    다음은 통화 연락처 목록에서 차단된 사용자의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![사용자 채팅을 보여주는 스크린샷](media/ib-before-chat-contacts-policy.png)

    다음은 통화 콘텐츠 목록에서 사용자에 대해 사용하지 않도록 설정되는 채팅의 예입니다.

    > [!div class="mx-imgBorder"]
    > ![채팅에서 차단된 사용자를 보여주는 스크린샷](media/ib-after-chat-contacts-policy.png)

- **Skype to Teams** 마이그레이션 - 비즈니스용 Skype에서 Teams로 마이그레이션하는 동안 IB 정책에 의해 차단된 모든 사용자도 Teams로 마이그레이션됩니다. 이러한 사용자는 위에서 설명한 대로 처리됩니다.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams 정책 및 SharePoint 사이트

팀이 만들어지면 파일 환경을 위해 SharePoint 사이트가 프로비전 및 Microsoft Teams와 연결됩니다. 이 SharePoint 사이트 및 파일에는 기본적으로 IB 정책이 적용됩니다. IB 정책을 사용하도록 설정하기 위해 관리자가 SharePoint 및 OneDrive에서 IB 정책을 사용하도록 요청하는  양식을 이미 작성했습니다(정보 장벽의 전제 구성성 섹션 [참조).](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) SharePoint 및 OneDrive에서 IB 정책이 켜져 있는 경우 IB 정책은 Microsoft Teams로 팀을 만들 때 프로비전되는 SharePoint 사이트에서 적용됩니다.

팀의 SharePoint 사이트의 **IB** 정책 예: Contoso Bank corporation에서 'Sesha@contosobank.onmicrosoft.com' 사용자는 Investment Banking 세그먼트에 속하고 사용자 'Nikita@contosobank.onmicrosoft.com'는 권고 세그먼트에 속합니다. 조직의 IB 정책은 이러한 두 세그먼트 간의 통신 및 공동 작업을 차단합니다.
Sesha 사용자가 Investment Banking 세그먼트에 대한 팀을 만드는 경우 이를 뒷부분으로 하는 팀과 SharePoint 사이트는 Investment Banking 사용자만 액세스할 수 있습니다. 사용자 Nikita는 사이트 링크가 있는 경우에도 해당 사이트에 액세스할 수 없습니다.

자세한 내용은 SharePoint에서 정보 장벽 [사용을 참조하세요.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="required-licenses-and-permissions"></a>필요한 라이선스 및 사용 권한

계획 및 가격을 포함한 라이선스 및 사용 권한에 대한 자세한 내용은 보안 및 규정 준수에 대한 [Microsoft 365 라이선스 & 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="known-issues"></a>알려진 문제
- **사용자가** 모임에 참가할 수 없습니다. IB 정책을 사용하도록 설정한 경우 모임 참석자 수 제한보다 큰 경우 사용자가 모임에 참가할 [수](limits-specifications-teams.md)없습니다. 근본 원인은 IB가 사용자를 모임 채팅 로스터에 추가할 수 있는지 여부에 따라 확인하며, 해당 사용자를 로스터에 추가할 수 있는 경우만 모임에 참가할 수 있도록 허용됩니다. 한 번 모임에 참가하는 사용자가 해당 사용자를 목록에 추가합니다. 따라서 모임이 재개될 경우 로스터를 빠르게 채울 수 있습니다. 채팅 로스터가 모임 [](limits-specifications-teams.md)참석 제한에 도달하면 모임에 추가 사용자를 추가할 수 없습니다. 테넌트에 대해 IB를 사용하도록 설정하고 채팅 로스터가 모임에 대해 가득 차면 새 사용자(아직 로스터에 없는 사용자)는 모임에 참가할 수 없습니다. 하지만 테넌트에 대해 IB를 사용하도록 설정하지 않은 경우 모임 채팅 로스터가 가득 차면 새 사용자(아직 로스터에 없는 사용자)가 모임에 참가할 수 있지만 모임에 채팅 옵션이 표시되지 않습니다. 단기 해결 방법은 모임 채팅 목록에서 비활성 구성원을 제거하여 새 사용자를 위한 공간을 만드는 것입니다. 그러나 나중에 모임 채팅 로스터의 크기를 늘려나가게 됩니다.

- **사용자가 채널** 모임에 참가할 수 없습니다. IB 정책을 사용하도록 설정한 경우 사용자가 팀의 구성원이 아닌 경우 채널 모임에 참가할 수 없습니다. 근본 원인은 IB가 사용자를 모임 채팅명단에 추가할 수 있는지 여부에 따라 확인하며, 해당 사용자를 로스터에 추가할 수 있는 경우만 모임에 참가할 수 있도록 허용됩니다. 채널 모임의 채팅 스레드는 팀/채널 구성원만 사용할 수 있으며, 구성원이 아닌 구성원은 채팅 스레드를 보거나 액세스할 수 없습니다. 테넌트에 대해 IB를 사용하도록 설정하고 팀 구성원이 아닌 구성원이 채널 모임에 참가하려고 하면 해당 사용자가 모임에 참가할 수 없습니다. 그러나 테넌트에  대해 IB를 사용할 수 없는 경우 팀 구성원이 아닌 구성원이 채널 모임에 참가하려고 하면 사용자가 모임에 참가할 수 있지만 모임에 채팅 옵션이 표시되지 않습니다.

## <a name="more-information"></a>추가 정보

- IB에 대한 자세한 내용은 정보 [장벽을 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- IB 정책을 설정하는 경우 정보 [장벽에 대한 정책 정의를 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- IB 정책을 편집하거나 제거하려면 정보 장벽 정책 [편집(또는 제거)을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)
