---
title: 'Teams IT 및 규정 준수 관리자를 위한 환자 앱 감사 '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Teams 관리자를 위한 환자 앱 감사에 대해 자세히 알아보기
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ce1851b6d424203f6a4aed8a871209e3a65ce5f8
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803516"
---
# <a name="audit-logs-for-patients-app"></a>환자 앱에 대한 감사 로그

> [!NOTE]
> 2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 유지되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 목록 앱을 사용하여 목록을 다시 [만들 수 있습니다.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 확인해 하세요. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 목록 앱 [관리를 참조하세요.](../../manage-lists-app.md)

환자 앱 활동에 대한 감사 로그를 사용하면 인시던트 후 대응 팀이 환자의 EMR(전자 의료 기록) 또는 PHI(환자 의료 정보)의 변경 내용을 검토하고 생산성 도구에서 PHI 액세스에 대한 정책 또는 절차의 변경 또는 개선이 필요한지 확인할 수 있습니다. 감사 로그 이벤트는 Patients 앱 사용자 인터페이스를 통해 수행된 작업을 다루고 있습니다.

## <a name="meet-hipaa-requirements"></a>HIPAA 요구 사항 충족

HIPAA 지침에 따라 의료 공급자는 변경 내용을 감사할 수 있도록 PHI에 대한 모든 액세스 기록을 유지해야 합니다. Microsoft는 Microsoft Teams를 사용하여 HIPAA 요구 사항 및 제어를 충족할 수 있도록 엔터프라이즈 고객에게 최선을 다하고 있습니다. 환자 앱을 통해 PHI에 대한 액세스는 완전히 추적되어 감사 로그 검색 기능 문서에 설명된 바와 같이 Microsoft 365 준수 센터에서 로그를 사용할 [수](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 있습니다.

> [!IMPORTANT]
> 환자 개인 정보를 유지 관리해야 하는 부담은 법률에 따라 의료 공급자에게 있습니다. 이 법률은 환자에게 개인 정보를 보호할 수 있는 권한을 부여하며 IT 관리자 또는 HIPAA 컨트롤러가 액세스하거나 변경된 환자 기록에 액세스하거나 변경한 간호사, 의료인 또는 소셜 직원을 쉽게 결정할 수 있도록 요구합니다. PHI 액세스 위반의 가장 일반적인 예 중 하나는 VIP 환자에 대한 액세스입니다. 감사 로그 기능은 PHI 액세스 위반에 대한 조사를 수행하고 HIPAA 요구 사항을 충족하는 데 필요합니다.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>환자 앱에 대한 감사 로그 사용

감사는 몇 가지 이전 구성에 따라 달라집니다.

1. 관리자는 FHIR 서비스 공급자와 함께 EMR을 환자 앱에서 사용하는 형식으로 설정해야 합니다. Microsoft [Teams에 Electronic Healthcare 레코드 통합을 참조합니다.](patients-app.md)
2. 의료 공급자 관리자는 Teams 관리 센터에서 환자 앱을 사용하도록 설정해야 합니다. 자세한 [내용은 Microsoft Teams의](../../teams-app-setup-policies.md) 앱 설정 정책 관리 및 관련 문서를 참조하세요.
3. 관리자는 감사 로그 검색을 시작하거나 해제하기 전에 설명한 활동 로그 [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) 감사를 사용하도록 설정하는 방법과 동일하게 활동 감사를 사용하도록 [설정해야 합니다.](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) 감사 로깅이 이미 설정되어 있는 경우 환자 앱에는 특별한 것이 필요하지 않습니다. 의료 공급자가 팀 내에서 앱을 설치하고 실행하면 감사 로그는 PHI 활동을 기록합니다.
4. 그러면 관리자는 환자 앱의 가용성을 발표해야 하며 의료 근로자는 감사에 포함되는 활동 생성을 시작해야 합니다.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>감사 실행

활동 로그 검색을 실행하는 방법에 대한 지침은 감사 로그 [검색을 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>환자 앱에 대한 기록된 활동

환자 앱에는 다음 표에 나열된 자체 기록된 활동이 있습니다.

|친숙한 이름 |작업|설명|
|:---|:---|:---|
| 환자 목록 보기 | PatientListView | 사용자가 환자 목록을 보게 됩니다.|
| 삭제된 환자 목록 | PatientListDelete | 사용자가 환자 목록을 삭제했습니다.|
| 목록에 환자 추가 | PatientListAddPatient | 환자 목록에 환자가 추가되었습니다. |
| 환자에 대한 메모 추가 | PatientNoteAdd | 환자 레코드에 메모가 추가되었습니다. |
| 환자 스마마 생성 | PatientSchemaCreate | 환자 레코드에 사용되는 열 집합이 생성되었습니다. |
| 사용자가 내보내기 시작 | ExportInitiation | 환자 앱에서 환자 데이터를 Excel 파일로 내보낼 수 있습니다. 파일이 팀 Sharepoint 사이트에 저장됩니다. |
| 환자 목록 생성 | PatientListCreate | 사용자가 환자 목록을 만들었다.|
| 기본 환자 목록 설정| PatientListDefaultSet| 사용자가 특정 목록을 기본 목록으로 설정합니다.|
| 목록에서 환자 제거| PatientListRemovePatient | 환자 목록에서 환자가 제거되었습니다. |
| 환자 검색 | PatientSearch | EHR 서비스에서 환자 기록을 검색했습니다. |
| 업데이트된 환자 스마마 | PatientSchemaUpdate  | 환자 레코드에 사용되는 기존 열 집합을 업데이트했습니다. |<!-- | 환자를 다른 목록으로 이동| PatientMoved | 환자 레코드가 한 목록에서 다른 목록으로 이동됩니다. |-->
| 명명된 환자 목록 | PatientListRename | 환자 목록의 이름을 다시 습니다. |
| 환자 목록의 편집된 열 | PatientListEditColumns | 환자 목록의 열이 편집되었습니다(추가 또는 제거됨). |
| 환자 세부 정보 보기 | PatientView | 사용자가 환자 기록을 보게 됩니다.|
| 편집된 환자 세부 정보 | PatientDetailsEdit | 환자 기록에 대한 세부 정보가 편집됩니다. |
| EHR 연결 설정 | EHRConnectionSet | EHR FHIR 서비스 연결에 연결하는 데 사용되는 URL을 설정하세요. 예: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

필요에 따라 감사를 사용자 지정하여 이러한 기록된 활동을 검색하거나 필터링할 수 있습니다.

일반적으로 Microsoft Teams에 기록된 활동은 [Microsoft Teams 활동에 설명되어 있습니다.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>관련 항목

[감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)
