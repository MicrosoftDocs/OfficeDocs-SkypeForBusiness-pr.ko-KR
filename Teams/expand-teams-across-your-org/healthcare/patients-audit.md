---
title: '팀 IT 및 규정 준수 관리자를 위한 환자 앱 감사 '
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
description: 팀 용 환자 앱 관리자
ms.openlocfilehash: 03aa421a72ab1402e0574a65117fa1eb182f1a47
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147711"
---
# <a name="audit-logs-for-patients-app"></a>환자 앱에 대한 감사 로그

환자 앱에 대 한 감사 로그 작업은 사고에 대 한 응답 팀이 환자의 전자 보험 레코드 (EMR) 또는 환자 의료 정보 (화이)에 대 한 변경 내용을 검토 하 고, 사용 하지 않는 경우에 대 한 정책 또는 절차의 변경 또는 개선 여부를 결정 합니다. 생산성 도구는 필요 합니다. 감사 로그 이벤트는 환자 앱 사용자 인터페이스를 통해 수행 되는 작업을 다룹니다.

## <a name="meet-hipaa-requirements"></a>HIPAA 요구 사항 충족

HIPAA 지침에 따라 건강 서비스 공급자는 변경 내용을 감사할 수 있도록 모든 access의 레코드를 모두에 게 유지 해야 합니다. Microsoft는 Microsoft 팀을 사용 하 여 기업 고객에 게 적용 되며, HIPAA 요구 사항 및 컨트롤을 충족 하는 데 도움을 줍니다. 환자 앱을 통한 온-오프에 대 한 액세스는 완전히 추적 되며 로그는 [감사 로그 검색 기능](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 문서에 설명 된 대로 M365 보안 및 준수 센터에서 사용할 수 있습니다.

> [!IMPORTANT]
> 환자 개인 정보를 유지 관리 하는 것은 법에 따라 건강 보험 업체에 게 부과 됩니다. 법은 개인정보 보호 통해 환자 IT 관리자 또는 HIPAA 컨트롤러가 어떤 nurse, clinician 또는 소셜 작업자에 게 액세스 하거나 변경 환자 기록을 쉽게 확인할 수 있어야 합니다. 환자 액세스 위반의 가장 일반적인 예 중 하나는 VIP에 대 한 액세스입니다. 감사 로그 기능은 발생 한 액세스 위반에 대 한 조사를 수행 하 고 HIPAA 요구 사항을 충족 하기 위해 필요 합니다.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>환자 앱에 대 한 감사 로그 사용

감사는 다음과 같은 몇 가지 이전 구성에 따라 달라 집니다.

1. 관리자는 환자 앱에서 사용 되는 형식으로 EMR 서비스 공급자와 함께 작업 해야 합니다. [Microsoft 팀에 전자 의료 기록 통합을](patients-app.md)참조 하세요.
2. 의료 제공자 관리자는 팀 관리 센터에서 환자 앱을 사용 하도록 설정 해야 합니다. 자세한 내용은 Microsoft 팀 및 관련 문서 [에서 앱 설정 정책 관리](../../teams-app-setup-policies.md) 를 참조 하세요.
3. 관리자는 [office 365 감사 로그 검색](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)을 시작 하 고 설정 [하기 전에](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) 설명 된 대로 office 365의 활동 로그 감사를 사용 하도록 설정 하는 것과 동일한 방법으로 O365에서 작업 감사를 사용 하도록 설정 해야 합니다. 감사 로깅이 이미 설정 되어 있는 경우 환자 앱에는 특별 한 항목이 필요 하지 않습니다. 건강 보험 제공 자가 팀 내에서 앱을 설치 하 고 실행할 때마다 감사 로그는 해당 화이 활동을 기록 합니다.
4. 관리자는 환자 앱의 가용성을 알리기 위해 의료 관련 자가 감사에 포함할 활동을 생성 하기 시작 해야 합니다.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>감사 실행

활동 로그 검색을 실행 하는 방법에 대 한 지침은 [감사 로그 검색](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)을 참조 하세요.

## <a name="logged-activities-for-patients-app"></a>환자 앱에 대 한 기록 활동

환자 앱에는 다음 표에 나열 된 고유 작업을 기록 합니다.

|친근 한 이름 |작업|설명|
|:---|:---|:---|
| 본 환자 목록 | PatientListView | 사용자가 환자 목록을 봤습니다.|
| 삭제 된 환자 목록 | PatientListDelete | 사용자가 환자 목록을 삭제 했습니다.|
| 목록에 환자 추가 됨 | PatientListAddPatient | 환자 목록에 환자를 추가 했습니다. |
| 환자에 대 한 참고 추가 됨 | PatientNoteAdd | 환자 레코드에 메모가 추가 되었습니다. |
| 생성 되는 환자 스키마 | PatientSchemaCreate | 환자 레코드에 사용 되는 열 집합을 만들었습니다. |
| 사용자가 내보내기를 시작 함 | ExportInitiation | 환자 앱에서 Excel 파일로 환자 데이터를 내보냈습니다. 파일이 팀 sharepoint 사이트에 저장 됩니다. |
| 생성 되는 환자 목록 | PatientListCreate | 사용자가 환자 목록을 만들었습니다.|
| 기본 환자 목록 설정| PatientListDefaultSet| 사용자가 특정 목록을 기본 목록으로 설정 합니다.|
| 목록에서 환자를 제거 함| PatientListRemovePatient | 환자 목록에서 환자를 제거 했습니다. |
| 검색 환자 | PatientSearch | EHR 서비스에서 환자 기록을 검색 했습니다. |
| 환자 스키마 업데이트 | PatientSchemaUpdate  | 환자 레코드에 사용 되는 기존 열 집합을 업데이트 했습니다. |<!-- | 환자를 다른 목록으로 이동| PatientMoved | 환자 레코드가 목록 간에 이동 되었습니다. |-->
| 환자 목록 이름 바꾸기 | PatientListRename | 환자 목록 이름이 변경 되었습니다. |
| 환자 목록의 열 편집 | PatientListEditColumns | 환자 목록의 열이 편집 (추가 또는 제거) 되었습니다. |
| 환자 정보 보기 | PatientView | 사용자가 환자 레코드를 봤습니다.|
| 환자 세부 정보 편집 됨 | PatientDetailsEdit | 환자 레코드에 대 한 세부 정보가 편집 되었습니다. |
| EHR 연결 설정 | EHRConnectionSet | EHR FA r 서비스 연결에 연결 하는 데 사용 되는 URL을 설정 합니다. 예: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

필요에 따라 감사를 사용자 지정 하 여 이러한 로깅된 활동을 검색 하거나 필터링 할 수 있습니다.

Microsoft 팀에 대 한 기록 된 활동은 일반적으로 [Microsoft 팀 활동](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)에 설명 되어 있습니다.

## <a name="related-topics"></a>관련 주제

[Office 365 감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)
