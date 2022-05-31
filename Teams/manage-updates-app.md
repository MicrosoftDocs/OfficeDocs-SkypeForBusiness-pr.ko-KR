---
title: 조직의 업데이트 앱 관리
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: 조직의 사용자에 대한 Teams 업데이트 앱을 관리하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8c538a4de417bcc6b19e579162357e56c444abdb
ms.sourcegitcommit: b8098d6ea36f10ee3a630a230ebd84bc2d96e37a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2022
ms.locfileid: "65781063"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams 조직의 업데이트 앱 관리

## <a name="what-is-the-updates-app"></a>업데이트 앱이란?

Microsoft Teams 앱의 업데이트는 조직 구성원이 업데이트를 만들고, 검토하고, 제출할 수 있는 중앙 집중식 위치를 제공합니다. 템플릿을 만들면 Updates 앱을 사용하여 조직에 필요한 모든 항목을 추적할 수 있습니다. 업데이트는 데스크톱과 모바일 모두에서 사용할 수 있습니다.

Teams 사용자는 Teams 앱 스토어에서 업데이트를 받을 수 있습니다. **제출** 페이지에 제출해야 하는 모든 업데이트가 표시됩니다.

[![데스크톱용 Teams 제출 페이지의 이미지입니다.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

사용자는 **검토** 페이지에서 할당한 업데이트를 볼 수 있습니다.

[![데스크톱용 Teams 검토 페이지의 이미지입니다.](media/updates-home-small.png)](media/updates-home.png#lightbox)

사용자에게 업데이트가 할당되면 Teams 활동 피드에 표시됩니다. 또한 사용자는 업데이트 앱에서 모든 현재 업데이트 요청 및 이전 제출을 볼 수 있습니다. 또한 누구나 템플릿을 만들고 업데이트 요청을 보낼 수 있습니다.

업데이트에는 일반적인 비즈니스 시나리오에 대한 기본 제공 템플릿과 고유한 템플릿을 만드는 옵션이 함께 제공됩니다. 누구나 새로운 유형의 업데이트에 대한 템플릿을 만들 수 있습니다.

## <a name="example-scenario"></a>시나리오 예

의류 매장의 직원은 매일 매장을 열고 닫을 책임이 있습니다. 매일 아침 Shift 리더는 업데이트 앱에서 기본 제공 템플릿인 Microsoft Store 열기 업데이트를 채웁니다. 이 업데이트에서는 전날 밤 폐점과 관련된 문제를 설명하고, 매장의 청결에 대한 질문에 답하고, 보충이 필요한 모든 물품을 보고합니다. 업데이트를 제출하면 저장소에 대한 요구 사항과 문제를 빠르고 효율적으로 전달할 수 있습니다. 일일 업데이트는 또한 매장 동료에게 잘 진행되고 있는 일을 강조할 수 있는 기회를 제공합니다.

매장의 제조 시설에서 직원들은 모바일 장치를 사용하여 업데이트로 안전 검사를 수행합니다.

![모바일 장치의 주간 안전 연습 템플릿 이미지입니다.](media/updates-mobile.png)

한편, 원격 작업자 팀이 매장의 웹 사이트를 업데이트하고 있습니다. 표준 시간대에 분산되어 있으므로 매일 스탠드업 모임이 편리하지 않습니다. 대신 각 팀 구성원은 진행 상황에 대한 매일 업데이트 보고서를 팀 리더에게 제출합니다.

## <a name="required-permissions-and-licenses"></a>필요한 권한 및 라이선스

업데이트를 배포하려면 다음 항목에 대한 권한이 필요합니다.

- Microsoft Dataverse 데이터베이스를 만들 수 있는 권한입니다.

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/) 계정입니다.

- 대상 환경의 관리자 역할입니다.

- Power Automate, Office 365 또는 Dynamics 365에 대한 라이선스입니다.

- 사용자가 새 템플릿을 설정하려면 Microsoft Forms 대한 라이선스가 필요합니다.

## <a name="storage-with-microsoft-dataverse"></a>Microsoft Dataverse를 사용하여 Storage

CDM(Common Data Model)은 Microsoft Dataverse의 비즈니스 및 분석 애플리케이션에서 사용하는 공유 데이터 언어입니다. Microsoft와 파트너가 게시한 표준화되고 확장 가능한 데이터 스키마 집합으로 구성되며, 이를 통해 애플리케이션 및 비즈니스 프로세스에서 데이터의 일관성과 그 의미를 구현할 수 있습니다. [공통 데이터 모델에](/common-data-model/) 대해 자세히 알아봅니다.

템플릿에서 만든 업데이트는 제목, 세부 정보, 템플릿 ID 등과 같은 데이터를 Microsoft Dataverse에 계속 저장합니다.  [Microsoft Forms 데이터 스토리지에](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe) 대해 자세히 알아봅니다.

>[!Note]
>Microsoft Forms 사이트에서 양식 서식 파일을 삭제하면 업데이트 템플릿이 중단되고 사용자가 업데이트를 제출할 수 없습니다. 사용자는 Microsoft Forms 삭제된 템플릿을 열려고 할 때 "CDB TableNotFound" 오류가 발생합니다.

## <a name="updates-teams-app-permissions"></a>앱 권한 Teams 업데이트

업데이트 Teams 앱을 사용하면 다음 기능에 액세스할 수 있습니다.

- 메시지에 제공하는 메시지 및 데이터를 수신합니다.

- 메시지 및 알림을 보냅니다.

- Teams이 제공한 헤더 없이 개인 앱 및 대화 상자를 렌더링합니다.

- 이름, 전자 메일 주소, 회사 이름 및 기본 설정 언어와 같은 프로필 정보에 액세스합니다.

- Teams 구성원이 채널에 제공하는 메시지 및 데이터를 수신합니다.

- 채널에서 메시지 및 알림을 보냅니다.

- 다음과 같은 Teams 정보에 액세스합니다.
  - 팀 이름
  - 채널 목록
  - 명단(팀 구성원의 이름 및 전자 메일 주소)

- 팀의 정보를 사용하여 팀에 연락하세요.

## <a name="disable-the-updates-app"></a>업데이트 앱 사용 안 함

업데이트 앱은 기본적으로 사용할 수 있습니다. Teams 관리 센터에서 앱을 비활성화할 수 있습니다.

  1. Teams 관리 센터에 로그인합니다.

  2. **Teams 앱** > **앱 관리** 로 이동합니다.

  3. 업데이트 앱을 검색합니다.

     [![Teams 앱 > 앱 관리가 강조 표시된 관리 가운데 탐색의 스크린샷](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. **업데이트를** 선택합니다.

  5. 조직에 대한 앱을 비활성화하려면 토글을 선택합니다.
    ![업데이트를 사용하거나 사용하지 않도록 설정하는 토글 이미지입니다.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>업데이트를 Teams 고정

### <a name="use-the-tailored-frontline-app-experience-to-pin-updates-and-other-apps-to-teams"></a>맞춤형 최전방 앱 환경을 사용하여 업데이트 및 기타 앱을 Teams

Teams 맞춤형 최전방 앱 환경은 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)가 있는 사용자를 위해 Teams 가장 관련성이 큰 앱을 고정합니다. 고정된 앱에는 업데이트, 승인, Walkie Talkie, 작업 및 교대 근무가 포함됩니다. 기본적으로 이 기능은 최전방 근로자에게 요구 사항에 맞는 기본 제공 환경을 제공합니다.

앱은 사용자가 빠르고 쉽게 액세스할 수 있는 앱 바(Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트의 아래쪽에 있는 막대)에 고정됩니다.

설정한 앱 정책의 작동 방식을 포함하여 자세한 내용은 [최전방 작업자를 위한 Teams 앱 조정](pin-teams-apps-based-on-license.md)을 참조하세요.

### <a name="use-an-app-setup-policy-to-pin-updates-to-teams"></a>앱 설정 정책을 사용하여 업데이트를 Teams 고정

앱 설정 정책을 사용하면 사용자의 사용자에게 가장 중요한 앱을 고정하는 Teams 사용자 지정할 수 있습니다.

사용자에 대한 업데이트 앱을 고정하려면 전역(조직 전체 기본값) 정책을 편집하거나 사용자 지정 앱 설정 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조하세요.

## <a name="retention-policy"></a>보존 정책

업데이트 앱에서 만든 업데이트는 현재 백업을 지원하지 않는 기본 Microsoft Dataverse 환경에 저장됩니다. [환경을 백업 및 복원하는 방법에 대해 자세히 알아보세요. PowerPlatform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).

양식에 저장된 데이터는 템플릿 작성자가 Microsoft Forms 웹앱의 **삭제된 양식** 탭에서 정리할 때까지 삭제되지 않습니다.

## <a name="conditional-access-policies"></a>조건부 액세스 정책

현재 Teams 업데이트 앱은 Microsoft Teams 대해 설정된 조건부 액세스 정책을 지원하지 않습니다.

## <a name="data-limitations"></a>데이터 제한 사항

각 사용자는 최대 400개의 업데이트 템플릿을 만들 수 있으며, 각 템플릿은 Microsoft Forms 현재 기능에 따라 최대 50,000개의 요청을 수집할 수 있습니다.

## <a name="security"></a>보안

Teams 업데이트 앱에서 사용자는 새 업데이트를 만들고 보내고 받은 업데이트를 볼 수 있습니다. 사용자는 요청의 뷰어가 아닌 한 다른 사용자가 만든 업데이트에 액세스할 수 없습니다.

> [!Note]
> 업데이트 보고서가 만들어진 채팅 또는 채널의 일부이거나 템플릿 작성자가 수동으로 뷰어로 추가하는 경우 사용자에게 요청의 뷰어 역할이 부여됩니다. 보고서를 만들 때 해당 역할이 부여되지 않은 경우 요청에 대해 조치를 취할 수 없습니다.
