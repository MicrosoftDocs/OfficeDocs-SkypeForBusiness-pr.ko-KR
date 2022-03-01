---
title: 데이터 FAQ 이동
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Shifts 데이터가 저장되는 위치, 데이터 보존, 검색 및 암호화를 포함하여 Shifts 데이터에 대해 자주 묻는 질문에 대한 답변을 얻습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3f26413aa746b37474e7035e313fc8ffff2fb93c
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039956"
---
# <a name="shifts-data-faq"></a>데이터 FAQ 이동

이 문서에서는 Shifts 데이터가 저장되는 위치, 데이터 보존, 검색 및 암호화를 비롯한 Shifts 데이터에 대한 질문과 대답을 다 제공합니다.

## <a name="where-is-shifts-data-stored"></a>Shifts 데이터는 어디에 저장하나요?

Shifts 데이터는 아시아 태평양(APAC), 유럽 연합(EU) 또는 미국의 세 가지 지역(지역) 중 하나에 저장됩니다. 각 지역은 HA(고가용성) 및 DR(재해 복구)을 위해 두 개 이상의 Azure 데이터 센터 지역에 데이터를 저장합니다. 현재 미국/북아메리카 지역은 미국 중북부 및 중남부에 있는 데이터 센터를 사용 중입니다. 자세한 내용은 저장된 고객 Microsoft 365 [위치를 참조합니다](/microsoft-365/enterprise/o365-data-locations).

현재 Shifts는 오스트레일리아, 캐나다, 프랑스, 일본 및 영국에 데이터 거주를 제공합니다. 지원을 더 많은 위치로 확장하기 위해 적극적으로 작업하고 있습니다.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Shifts 데이터가 저장되는 위치를 선택할 수 있나요?

처음 Teams 설정하면 구독 수준에서 설정되는 국가 또는 지역을 선택합니다. Shifts는 이 선택을 존중하고 해당 지역을 지원하는 경우 해당 Teams 설정한 로콜 및 지역을 사용하게 됩니다. 해당 지역에 아직 없는 경우 지원되는 가까운 지역에 데이터를 저장합니다. 앞으로는 인근 지역에 저장된 경우 기존 데이터를 프로비전된 지역으로 마이그레이션할 Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Shifts에서 사용자의 개인 데이터에 액세스하고 내보내거나 삭제할 수 있나요?

Shifts는 GDPR(일반 데이터 보호 규정)을 준수합니다.개인 데이터에 대한 작업을 수행하기 위해 개인(데이터 주체라고도 하는)의 공식 요청을 DSR(데이터 주체 요청)이라고 합니다. DSR에 대한 응답으로 Shifts에서 개인 데이터를 찾아서 행동할 수 있습니다.

콘텐츠 검색 eDiscovery 도구를 사용하여 Microsoft 365 규정 준수 센터 시간 클록 데이터를 검색하고 내보낼 수 Excel. 다른 모든 Shifts 데이터의 경우 데이터의 스크린샷을 찍을 수 있습니다.

자세한 내용은 [GDPR 및 CCPA에 Office 365](/microsoft-365/compliance/gdpr-dsr-office365) 데이터 주체 요청을 참조합니다.

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>조직에 대한 Shifts를 해제하면 Shifts 데이터가 어떻게 하나요?

조직의 Shifts를 해제 *하면 데이터가 삭제* 되지 않습니다. Shifts를 해제한 다음 나중에 Shifts를 켜면 Shifts 데이터를 계속 사용할 수 있습니다.

테넌트를 삭제하면 보존 기간이 끝나면 모든 Shifts 데이터가 삭제됩니다.

Shifts 데이터만 삭제하는 옵션은 없습니다. 팀에서 팀을 삭제하면 Teams 기간이 끝나면 해당 팀과 연결된 데이터를 변경합니다. 자세한 내용은 데이터 보존[,](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) 삭제 및 삭제를 Microsoft 365.

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>삭제된 Shifts 일정을 복구할 수 있나요?

백업하는 그룹(또는 Microsoft 365 팀)이 복원된 경우 삭제된 일정을 복구할 Teams.

기본적으로 삭제된 Microsoft 365 그룹은 30일 동안 유지됩니다. 이 30일 기간은 그룹을 복원할 수 있기 때문에 "soft-delete"라고 합니다. 자세한 내용은 삭제된 그룹 복원을 [Microsoft 365 참조합니다](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Shifts 데이터에 대한 사용자 지정 보존 정책을 사용할 수 있나요?

현재 Shifts는 사용자 지정 보존 정책을 지원하지 않습니다.

Teams 보존 정책에 대한 자세한 내용은 Teams 및 보존 정책 관리를 참조 [](/microsoft-365/compliance/retention-policies-teams) [Teams.](../../retention-policies.md)

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>라이선스가 해지된 사용자의 Shifts 데이터를 검색할 수 있나요?

현재 라이선스가 해지된 사용자의 데이터를 검색하는 기능을 제공하지 않습니다. 이 기능은 현재 진행하고 있는 기능입니다.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts는 미사용 데이터 및 전송 시 데이터에 어떤 유형의 암호화를 사용하나요?

Shifts 데이터는 Azure Cosmos DB 및 Azure Storage. 자세한 내용은 [미사용 Azure](/azure/security/fundamentals/encryption-atrest) 데이터 암호화 및 Azure Cosmos [DB를 참조하세요](/azure/cosmos-db/database-encryption-at-rest).

Shifts는 전송되는 Microsoft 365 암호화에 대한 지침에 따릅니다. 자세한 내용은 전송 중 데이터 암호화 [를 참조하세요](/compliance/assurance/assurance-encryption-in-transit).

미사용 및 전송 중 데이터의 교대 근무 암호화는 SOC2 규정 준수 감사를 통해 해에 확인됩니다.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Shifts 데이터의 변경 불가능한 복사본에 액세스할 수 있나요?

Shifts 데이터의 변경 불가능한 복사본은 저장하지 않습니다. 예를 들어 관리자는 노트 추가, 교대 근무 시간 변경, 작업 할당 등 일정을 변경할 수 있습니다.

## <a name="can-shifts-data-be-edited"></a>Shifts 데이터를 편집할 수 있나요?

변경할 수 없는 Shift의 특정 측면과 변경할 수 있는 특정 측면이 있습니다. 예를 들어 노트 및 색과 같은 교대 근무 세부 정보를 Shifts 앱에서 변경할 수 있는 방법과 유사하게 편집할 수 있습니다. 요청이 철회되지 않는 한 교대 근무 요청을 편집할 수 없습니다.

변경된 필드를 확인하려면 Shifts 이벤트에 대한 Microsoft 365 감사 로그를 검색할 수 있습니다. 감사 로그에서 Shifts 활동에 대해 기록된 이벤트에 Microsoft 365 자세한 내용은 작업의 [Shifts를 Teams 참조하세요](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>조직에서는 인력 관리 시스템을 사용하여 일과를 계획합니다. Shifts 데이터와 통합하고 액세스할 수 있나요?

Shifts Graph API를 사용하면 Shifts 데이터를 WFM(외부 인력 관리) 시스템과 통합할 수 있습니다. 자세한 내용은 [Shifts Graph 참조합니다](/graph/api/resources/shift).

또한 관리되는 Shifts 커넥터 및 오픈 소스 Shifts 커넥터도 제공합니다. 이러한 커넥터를 사용하면 WFM 시스템을 Shifts와 직접 통합할 수 있습니다. Shifts 커넥터 및 지원되는 WFM 시스템에 대한 자세한 내용은 [Shifts 커넥터를 참조합니다](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Shifts 데이터는 지정된 기간 후에 영구적으로 삭제할 수 있나요?

현재는 Shifts 데이터를 삭제하지 않습니다. [Shifts Graph API](/graph/api/resources/shift)를 사용하여 특정 기간 동안 데이터를 Power Apps 앱을 만들 수 있습니다[](/powerapps/maker/). 그러나 기본적으로 지원하지 않습니다.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Shifts 데이터를 테넌트-테넌트 마이그레이션에서 이동할 수 있나요?

Shifts 데이터는 특정 요청에 따라 한 테넌트에서 다른 테넌트로 마이그레이션할 수 있습니다. 테넌트-테넌트 마이그레이션은 바로 지원되지 않지만 고객 요청으로 제기될 수 있습니다.

## <a name="related-articles"></a>관련 기사

- [Teams의 교대 근무](../shifts-for-teams-landing-page.md)
- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
