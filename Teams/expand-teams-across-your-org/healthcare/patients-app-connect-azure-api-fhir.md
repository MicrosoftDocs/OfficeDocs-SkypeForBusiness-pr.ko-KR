---
title: 환자 앱을 Azure API에 연결 하 여 FA r
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 팀의 환자 앱을 Azure API에 연결 하는 방법 (신속한 의료 상호 운용성 리소스)에 대해 알아보세요.
ms.openlocfilehash: e532aa9f9fbecb472db63a1ddad4cd71518a8041
ms.sourcegitcommit: d7fab927e96954f294f28dfb33c0889f736b3ab5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259133"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>환자 앱을 Azure API에 연결 하 여 FA r

다음 단계에 따라 Microsoft 팀의 환자 앱이 FTO r 인스턴스에 대 한 Azure API에 액세스할 수 있도록 허용 합니다. 이 문서에서는 테 넌 트에 [FTO r 인스턴스를](https://azure.microsoft.com/services/azure-api-for-fhir/) 설정 하 고 구성 하는 Azure API를 사용 하 고 있다고 가정 합니다.  테 넌 트에 FTO r 인스턴스에 대 한 Azure API를 아직 만들지 않은 경우 [빠른 시작: azure 포털을 사용 하 여 AZURE Api 배포](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)를 참조 하세요.


1. 환자 앱에 관리자 동의를 부여 하려면 [여기](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 를 클릭 하세요. 메시지가 표시 되 면 테 넌 트 관리자 또는 전역 관리자 자격 증명을 사용 하 여 로그인 한 다음 **적용** 을 클릭 하 여 필요한 사용 권한을 부여 합니다.

    ![환자 앱에 대 한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request.png)

    수락한 후 창을 닫습니다. 다음과 같은 페이지를 볼 수 있습니다. 페이지에서 오류 메시지를 무시할 수 있습니다. 이는 무해 하며 동의가 부여 되었음을 의미 합니다. (이 URL에 대해 사용자에 게 친숙 한 페이지를 사용 하는 것입니다. 계속 조정!)

    ![환자 앱에 대 한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request-granted.png)
2. 관리자 자격 증명을 사용 하 여 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.
3. 왼쪽 탐색 창에서 **Azure Active Directory**를 선택한 다음 **엔터프라이즈 응용 프로그램**을 선택 합니다.
    **환자 (dev)** 라는 행을 찾은 다음 **개체 ID** 열의 값을 클립보드에 복사 합니다.
    ![Azure 포털의 환자 (dev) 행 스크린샷](../../media/patients-app-azure-portal-object-id.png)
4. 환자 app을 검색 하거나 리소스를 탐색 하 여 연결 하려는 FTO r 리소스 인스턴스로 이동 하 여 해당 인스턴스에 대 한 설정을 엽니다 (선택 사항).

    ![Azure 포털의 FTO r 인스턴스 설정에 대 한 Azure API 스크린샷](../../media/patients-app-azure-portal-instance-settings.png)

5. **인증**을 클릭 한 다음 3 단계에서 복사한 개체 Id를 **허용 된 개체 id** 상자에 붙여 넣습니다. 이렇게 하면 환자 앱이 FTO r 서버에 액세스할 수 있습니다. 개체 ID를 붙여 넣으면 Azure Active Directory에서 유효성을 검사 하 고 녹색 확인 표시가 그 옆에 나타납니다.

    ![Azure 포털의 인증 설정 스크린샷](../../media/patients-app-azure-portal-authentication.png)

6. **저장**을 클릭 합니다. 이렇게 하면 인스턴스가 다시 배포 되 고 몇 분 정도 걸릴 수 있습니다.
7. **개요**를 클릭 한 다음 **fa r 메타 데이터 끝점**에서 URL을 복사 합니다. 메타 데이터 태그를 제거 하 여 FA r 서버 URL을 가져옵니다. 예를 https://test02-teamshealth.azurehealthcareapis.com/들어. 

    ![Azure 포털의 메타 데이터 끝점 스크린샷](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 팀에서 팀에 로드 된 환자 app 인스턴스로 이동 하 고 **설정을**클릭 한 다음 **링크** 상자에 fgo r 서버 끝점 URL을 입력 합니다. 그런 다음 연결 **을 클릭 하 여 연결** 을 설정 하 고 검색 하 여 목록에 환자 추가 합니다.  

    ![팀의 환자 앱 설정 스크린샷](../../media/patients-app-teams.png)
    
    이 단계에서 팀에 연결 하는 동안 오류가 [발생 하는](mailto:teamsforhealthcare@service.microsoft.com)경우 오류에 대 한 자세한 스크린샷, 전자 메일에서 "환자 APP-emr 모드 문제 해결"의 제목 줄이 있는 [Fiddler](https://www.telerik.com/download/fiddler) 및 다른 재현 단계의 로그를 보냅니다.

## <a name="related-topics"></a>관련 항목

- [환자 앱 개요](patients-app-overview.md)
- [Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)
