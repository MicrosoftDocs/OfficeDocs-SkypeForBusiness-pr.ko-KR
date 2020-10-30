---
title: 환자 앱을 FHIR용 Azure API에 연결
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀의 환자 앱을 Azure API에 연결 하는 방법 (신속한 의료 상호 운용성 리소스)에 대해 알아보세요.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 29447791a8ba169bfc50173b249b3f8b987c7a17
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803556"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>환자 앱을 FHIR용 Azure API에 연결

> [!NOTE]
> 2020 년 10 월 30 일에 효력을 환자 앱이 만료 되어 팀의 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 으로 대체 되었습니다. 환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다. 환자 앱과 연결 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.
>
>목록을 사용 하는 경우 의료 기관에서 팀은 팀 모임에서 일반 환자 모니터링과의 interdisciplinary에 이르기까지 시나리오에 대 한 환자 목록을 만들 수 있습니다. 목록에서 환자 서식 파일을 확인 하 여 시작 하세요. 조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.

다음 단계에 따라 Microsoft 팀의 환자 앱이 FTO r 인스턴스에 대 한 Azure API에 액세스할 수 있도록 허용 합니다. 이 문서에서는 테 넌 트에 [FTO r 인스턴스를](https://azure.microsoft.com/services/azure-api-for-fhir/) 설정 하 고 구성 하는 Azure API를 사용 하 고 있다고 가정 합니다.  테 넌 트에 FTO r 인스턴스에 대 한 Azure API를 아직 만들지 않은 경우 [빠른 시작: azure 포털을 사용 하 여 AZURE Api 배포](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)를 참조 하세요.


1. 환자 앱에 관리자 동의를 부여 하려면 [여기](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 를 클릭 하세요. 메시지가 표시 되 면 테 넌 트 관리자 또는 전역 관리자 자격 증명을 사용 하 여 로그인 한 다음 **적용** 을 클릭 하 여 필요한 사용 권한을 부여 합니다.

    ![환자 앱에 대 한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request.png)

    수락한 후 창을 닫습니다. 다음과 같은 페이지를 볼 수 있습니다. 페이지에서 오류 메시지를 무시할 수 있습니다. 이는 무해 하며 동의가 부여 되었음을 의미 합니다. (이 URL에 대해 사용자에 게 친숙 한 페이지를 사용 하는 것입니다. 계속 조정!)

    ![환자 앱에 대 한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request-granted.png)
    
2. 관리자 자격 증명을 사용 하 여 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.

3. 왼쪽 탐색 창에서 **Azure Active Directory** 를 선택한 다음 **엔터프라이즈 응용 프로그램** 을 선택 합니다.

    **환자 (dev)** 라는 행을 찾은 다음 **개체 ID** 열의 값을 클립보드에 복사 합니다.
    
    ![Azure 포털의 환자 (dev) 행 스크린샷](../../media/patients-app-azure-portal-object-id.png)
    
4. 환자 app을 검색 하거나 리소스를 탐색 하 여 연결 하려는 FTO r 리소스 인스턴스로 이동 하 여 해당 인스턴스에 대 한 설정을 엽니다 (선택 사항).

    ![Azure 포털의 FTO r 인스턴스 설정에 대 한 Azure API 스크린샷](../../media/patients-app-azure-portal-instance-settings.png)

5. **인증** 을 클릭 한 다음 3 단계에서 복사한 개체 Id를 **허용 된 개체 id** 상자에 붙여 넣습니다. 이렇게 하면 환자 앱이 FTO r 서버에 액세스할 수 있습니다. 개체 ID를 붙여 넣으면 Azure Active Directory에서 유효성을 검사 하 고 녹색 확인 표시가 그 옆에 나타납니다.

    ![Azure 포털의 인증 설정 스크린샷](../../media/patients-app-azure-portal-authentication.png)

6. **저장** 을 클릭합니다. 이렇게 하면 인스턴스가 다시 배포 되 고 몇 분 정도 걸릴 수 있습니다.

7. **개요** 를 클릭 한 다음 **fa r 메타 데이터 끝점** 에서 URL을 복사 합니다. 메타 데이터 태그를 제거 하 여 FA r 서버 URL을 가져옵니다. 예를 들어 https://test02-teamshealth.azurehealthcareapis.com/ . 

    ![Azure 포털의 메타 데이터 끝점 스크린샷](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 팀에서 팀에 로드 된 환자 app 인스턴스로 이동 하 고 **설정을** 클릭 한 다음 **링크** 상자에 fgo r 서버 끝점 URL을 입력 합니다. 그런 다음 연결 **을 클릭 하 여 연결** 을 설정 하 고 검색 하 여 목록에 환자 추가 합니다.  

    ![팀의 환자 앱 설정 스크린샷](../../media/patients-app-teams.png)
    
    이 단계에서 팀에 연결 하는 동안 오류가 [발생 하는](mailto:teamsforhealthcare@service.microsoft.com)경우 오류에 대 한 자세한 스크린샷, 전자 메일에서 "환자 APP-emr 모드 문제 해결"의 제목 줄이 있는 [Fiddler](https://www.telerik.com/download/fiddler) 및 다른 재현 단계의 로그를 보냅니다.

## <a name="related-topics"></a>관련 항목

- [환자 앱 개요](patients-app-overview.md)
- [Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)
