---
title: Microsoft Teams에 대한 보존 정책 관리
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams의 보존 정책을 사용하여 조직이 내부 정책, 산업 규정 또는 법적 요구 사항을 준수해야 하는 메시지를 유지하고 책임으로 간주되거나 법적 비즈니스 가치가 없는 메시지를 삭제합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617760"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Microsoft Teams에 대한 보존 정책 관리

> [!NOTE]
> 보존 정책에 의해 채팅 또는 메시지가 삭제된 메시지가 Teams에 표시되면 보존 정책에 대한 Teams 메시지를 [참조하세요.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> 이 페이지의 정보는 이러한 보존 정책을 관리하는 IT 관리자를 위한 정보입니다.

Microsoft 365의 보존 정책 및 보존 레이블을 사용하면 조직의 정보를 보다 효과적으로 관리할 수 있습니다. 조직의 내부 정책, 산업 규정 또는 법적 요구 사항을 준수하는 데 필요한 데이터를 유지하도록 보존 설정을 구성할 수 있습니다. 책임으로 간주되는 데이터, 더 이상 보관할 필요 없음 또는 법적 또는 비즈니스 가치가 없는 데이터를 삭제하도록 보존 설정을 구성할 수도 있습니다.

Teams는 채팅 및 채널 메시지에 대한 보존 정책을 지원하기 때문에 관리자는 이 데이터를 보존하거나 삭제하거나 특정 기간 동안 보존할지 여부를 사전적으로 결정할 수 있습니다. 이러한 작업에 대한 보존 기간의 시작은 항상 메시지를 만들 때를 기반으로 합니다. Teams 보존 정책을 전체 조직 또는 특정 사용자 및 팀에 적용할 수 있습니다. 보존 레이블은 Teams에 지원되지 않습니다.

Microsoft 365의 보존 솔루션에 대한 자세한 내용은 보존 정책 및 보존 레이블에 대해 [자세히 알아보십시오.](/microsoft-365/compliance/retention)

Teams에 대한 보존 정책이 적용된 사용자는 Office 365 E3 또는 Office 365 A3와 같은 적절한 라이선스를 보유해야 합니다. 이러한 보존 정책에 대한 다른 라이선스 [](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 옵션은 보안 규정 준수에 대한 [Microsoft 365 라이선스 지침의 정보 거버넌스 섹션을 & 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) Teams에 대한 라이선스에 대한 자세한 내용은 [Microsoft Teams 서비스 설명 을 참조하세요.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Teams 보존 정책이 작업 보존 및 삭제를 지원하는 방법

채팅 또는 채널 메시지를 유지하도록 Teams 보존 정책을 구성하는 경우 사용자는 여전히 Teams 앱에서 메시지를 편집하고 삭제할 수 있습니다. 사용자가 Teams에서 미리 편집되거나 삭제된 메시지를 더 이상 볼 수 없습니다. 이러한 메시지의 데이터는 규정 준수 관리자가 eDiscovery 검색을 위해 설계된 보안 위치에 저장됩니다. 이 데이터의 영구 삭제는 구성된 보존 기간이 끝나기 전에 일어나지 않습니다. 또는 이 데이터를 보존하도록 다른 보존 정책이 구성된 경우 또는 [eDiscovery](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)보존의 대상이 됩니다.

채팅 및 채널 메시지를 삭제하도록 보존 정책이 구성되면 이러한 메시지는 자동으로 삭제될 수 있습니다. 메시지가 Teams 앱에 계속 표시되는 경우 해당 메시지는 거기에서 사라지고 보존 정책이 이러한 메시지를 삭제했다는 메시지가 [표시됩니다.](#end-user-experience) 메시지는 이전에 보존 작업의 대상이 됐고 사용자가 편집하거나 삭제한 경우 이제 이러한 메시지는 보안 위치에서 삭제되고 eDiscovery 검색에서 더 이상 반환되지 않습니다.

정책 구성 및 사용자 작업에 따라 이러한 정책이 작동하는 방법 및 Teams 보존 정책에 대해 포함 및 제외되는 메시지 데이터에 대한 자세한 내용은 Microsoft Teams 보존에 대한 자세한 정보를 [참조하세요.](/microsoft-365/compliance/retention-policies-teams) 또한 보존 정책이 메시지를 삭제하는 경우 지연이 있을 수 있는 이유도 설명하고 있습니다. 예를 들어 보존 정책에서 구성한 만료 기간이 지난 후 최대 7일 후에 Teams 앱의 사용자에게 메시지를 볼 수 있습니다.

보존 설정이 다른 여러 Teams 보존 정책을 설정한 경우 보존 원칙은 충돌을 해결합니다. 예를 들면 다음과 같습니다.

- 동일한 콘텐츠를 유지하거나 삭제하는 사이에 충돌이 있는 경우 콘텐츠는 항상 보안 위치에 유지되고 규정 준수 관리자를 위해 eDiscovery를 사용하여 검색할 수 있도록 합니다.
    
    이 원칙은 법적 또는 조사상의 이유로 eDiscovery에 보유된 메시지에도 적용됩니다.

- 동일한 콘텐츠를 유지하는 기간에 충돌이 있는 경우 가장 긴 보존 기간 동안 보안 위치에 유지됩니다.

이러한 보존 원칙은 Teams에 대한 여러 보존 정책이 있을 때 발생할 수 있는 대부분의 충돌을 해결하지만 자세한 내용은 보존 원칙 또는 우선 순위를 [참조하세요.](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Teams에 보존 정책을 사용하는 시기

대부분의 경우 조직은 비공개 채팅 데이터를 일반적으로 프로젝트 관련 대화가 주를 이루는 채널 메시지보다 더 많은 책임으로 간주합니다.

비공개 채팅(1:1 또는 1:다수 채팅) 및 채널 메시지에 대해 별도의 보존 정책을 설정할 수 있습니다. 조직의 특정 사용자 또는 팀에 적용되는 고유한 정책을 구성할 수도 있습니다. Teams 채팅의 경우 정책을 적용할 사용자를 선택할 수 있습니다. Teams 채널 메시지의 경우 정책을 적용할 팀을 선택할 수 있습니다.

예를 들어 채널 메시지의 경우 조직의 특정 팀에 보존 정책을 적용할 수 있으며 해당 정책은 1년 후 삭제 작업으로 구성됩니다. 그런 다음 다른 모든 팀에 다른 보존 정책을 적용하고 해당 정책은 3년 후 삭제 작업으로 구성됩니다.

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams에 대한 보존 정책 만들기 및 관리

Teams 채팅 및 채널 메시지에 대한 보존 정책을 만들거나 편집하려면 Teams 위치 보존 정책의 [지침을 사용합니다.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

이 페이지에는 Microsoft 365의 다른 워크로드에 대한 보존 정책을 만들고 관리하는 데 대한 추가 정보가 있습니다. 예를 들어 Teams에 액세스하고 OneDrive 또는 SharePoint에 저장된 파일을 보존하고 삭제하기 위해 Microsoft 365 그룹에 대한 보존 정책을 만들 수도 있습니다.  

## <a name="end-user-experience"></a>최종 사용자 환경

비공개 채팅(1:1 채팅) 또는 그룹 채팅의 경우 사용자는 보존 정책 구성보다 오래된 채팅이 삭제되고 "오그의 보존 정책으로 인해 이전 메시지를 삭제했습니다"라는 메시지가 아직 삭제되지 않은 메시지 위에 표시됩니다. 예를 들면 다음과 같습니다.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams 보존 정책으로 채팅 메시지가 삭제된다고 팀에 알리는 사용자":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams의 사용자 설명 메시지는 Teams 보존 정책의 결과로 삭제됩니다.":::

채널 메시지의 경우 사용자(채널 구성원)는 메시지가 만료되면 삭제된 메시지가 보기에서 사라지는 것을 볼 수 있습니다. 삭제된 메시지가 스레드 대화의 부모 메시지인 경우 부모 메시지 대신 "보존 정책 때문에 이 메시지가 삭제되었습니다"라는 메시지가 표시됩니다. 예를 들면 다음과 같습니다.

:::image type="content" source="media/retention-policies-image3.png" alt-text="보존 전 채널 스크린샷":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="보존 후 채널 스크린샷":::

> [!NOTE]
> 사용자가 삭제된 메시지의 결과로 표시되는 표시된 메시지는 현재 구성할 수 없습니다.

이러한 표시된 메시지의 링크는 보존 정책에 [대한 Teams 메시지로 이동됩니다.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) 최종 사용자에 대한 이 설명서는 메시지를 삭제한 이유에 대한 기본 질문에 답변하는 데 도움이 됩니다. 그러나 보존 정책 배포의 일부로 사용자 및 지원 센터에 구성된 설정의 영향을 전달해야 합니다.

## <a name="related-topics"></a>관련 항목

- [보존 정책 및 보존 레이블 시작](/microsoft-365/compliance/get-started-with-retention)
- [Microsoft Teams 보존에 대해 자세히 알아보기](/microsoft-365/compliance/retention-policies-teams)
- [보존 정책 만들기 및 구성](/microsoft-365/compliance/create-retention-policies)
