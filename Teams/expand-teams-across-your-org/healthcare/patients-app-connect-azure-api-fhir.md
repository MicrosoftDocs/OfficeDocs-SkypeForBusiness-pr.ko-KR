---
title: 환자 앱을 FHIR용 Azure API에 연결
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft Teams의 환자 앱을 FHIR용 Azure API(Fast Healthcare Interoperability Resources)에 연결하는 방법에 대해 설명합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096270"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>환자 앱을 FHIR용 Azure API에 연결

> [!NOTE]
> 2020년 10월 30일부터 환자 앱이 폐기되고 Teams 내 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)으로 대체되었습니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 보존되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용하여 목록을 다시 만들 수 있습니다.
>
>목록 기능을 사용하면 의료 조직의 관리 팀은 라운드 및 분야별 팀 모임에서 일반 환자 모니터링에 이르는 다양한 시나리오에 대한 환자 목록을 작성할 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 체크 아웃합니다. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 [목록 앱 관리](../../manage-lists-app.md)를 참조하세요.

다음 단계를 수행하여 Microsoft Teams의 Patients 앱이 FHIR 인스턴스용 Azure API에 액세스할 수 있도록 허용합니다. 이 문서에서는 테넌트에서 [FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 인스턴스에 대한 Azure API를 설정하고 구성했다고 가정합니다.  테넌트에서 FHIR 인스턴스에 대한 Azure API를 아직 만들지 않은 경우 Azure Portal을 사용하여 FHIR용 Azure API 배포 빠른 [시작을 참조하세요.](/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. 환자 [앱에](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 대한 관리자 동의를 부여하려면 여기를 클릭합니다. 메시지가 표시될 때 테넌트 관리자 또는 전역 관리자 자격  증명을 사용하여 로그인한 다음 수락을 클릭하여 필요한 권한을 부여합니다.

    ![환자 앱에 대한 권한 요청 스크린샷](../../media/patients-app-permissions-request.png)

    수락한 후 창을 닫습니다. 다음과 같이 표시될 수 있는 페이지가 표시됩니다. 페이지의 오류 메시지를 무시할 수 있습니다. 무해하며 동의가 부여된 경우를 나타냅니다. (이 URL에 대한 사용자 친화적인 페이지에서 작업 중입니다. 계속 지켜봐 주세요!)

    ![환자 앱에 대한 권한 요청 스크린샷](../../media/patients-app-permissions-request-granted.png)

2. 관리자 자격 [증명을 사용하여 Azure Portal에](https://portal.azure.com) 로그인합니다.

3. 왼쪽 탐색에서 **Azure Active Directory를** 선택한 다음 **엔터프라이즈 애플리케이션 을 선택합니다.**

    **Patients(개발)라는** 행을 찾아 개체 **ID** 열의 값을 클립보드에 복사합니다.

    ![Azure Portal의 환자(개발) 행 스크린샷](../../media/patients-app-azure-portal-object-id.png)

4. 환자 앱을 연결하려는 FHIR용 Azure API 리소스 인스턴스로 이동하여(검색하거나 리소스를 검색하여) 해당 인스턴스에 대한 설정을 를 펜션합니다.

    ![Azure Portal의 FHIR 인스턴스 설정용 Azure API 스크린샷](../../media/patients-app-azure-portal-instance-settings.png)

5. **인증을** 클릭한 다음 3단계에서 복사한 개체 ID를 허용된 개체 ID 상자에 **붙여넣습니다.** 이렇게 하면 Patients 앱이 FHIR 서버에 액세스할 수 있습니다. 개체 ID를 붙여넣은 후 Azure Active Directory에서 유효성을 검사하고 옆에 녹색 확인 표시가 나타납니다.

    ![Azure Portal의 인증 설정 스크린샷](../../media/patients-app-azure-portal-authentication.png)

6. **저장** 을 클릭합니다. 이 경우 몇 분 정도 걸릴 수 있는 인스턴스를 다시 재배포합니다.

7. **개요를** 클릭한 다음 FHIR 메타데이터 엔드포인트에서 **URL을 복사합니다.** 메타데이터 태그를 제거하여 FHIR 서버 URL을 얻습니다. 예를 `https://test02-teamshealth.azurehealthcareapis.com/` 들어.

    ![Azure Portal의 메타데이터 엔드포인트](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. Teams에서 팀에 로드된 Patients 앱 인스턴스로 이동하여 설정을 클릭한 다음  링크 상자에 FHIR 서버 엔드포인트 URL을 입력합니다. 그런 다음 연결을 **클릭하여** 연결을 설정하고 환자를 검색하고 목록에 추가합니다.  

    ![ Teams의 환자 앱 설정](../../media/patients-app-teams.png)

    이 단계에서 Teams에 연결할 때 오류가 발생하는 경우 "Patients App – EMR 모드 문제 해결"의 제목 줄이 있는 전자 메일의 [오류, Fiddler의](https://www.telerik.com/download/fiddler) 로그 및 기타 다시프로 단계의 자세한 스크린샷을 [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>관련 항목

- [환자 앱 개요](patients-app-overview.md)
- [Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)