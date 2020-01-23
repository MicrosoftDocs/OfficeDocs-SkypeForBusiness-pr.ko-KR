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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="ee902-103">환자 앱을 Azure API에 연결 하 여 FA r</span><span class="sxs-lookup"><span data-stu-id="ee902-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="ee902-104">다음 단계에 따라 Microsoft 팀의 환자 앱이 FTO r 인스턴스에 대 한 Azure API에 액세스할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="ee902-105">이 문서에서는 테 넌 트에 [FTO r 인스턴스를](https://azure.microsoft.com/services/azure-api-for-fhir/) 설정 하 고 구성 하는 Azure API를 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="ee902-106">테 넌 트에 FTO r 인스턴스에 대 한 Azure API를 아직 만들지 않은 경우 [빠른 시작: azure 포털을 사용 하 여 AZURE Api 배포](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee902-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="ee902-107">환자 앱에 관리자 동의를 부여 하려면 [여기](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 를 클릭 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee902-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="ee902-108">메시지가 표시 되 면 테 넌 트 관리자 또는 전역 관리자 자격 증명을 사용 하 여 로그인 한 다음 **적용** 을 클릭 하 여 필요한 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![환자 앱에 대 한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="ee902-110">수락한 후 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-110">After you accept, close the window.</span></span> <span data-ttu-id="ee902-111">다음과 같은 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="ee902-112">페이지에서 오류 메시지를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="ee902-113">이는 무해 하며 동의가 부여 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="ee902-114">(이 URL에 대해 사용자에 게 친숙 한 페이지를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="ee902-115">계속 조정!)</span><span class="sxs-lookup"><span data-stu-id="ee902-115">Stay tuned!)</span></span>

    ![환자 앱에 대 한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="ee902-117">관리자 자격 증명을 사용 하 여 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="ee902-118">왼쪽 탐색 창에서 **Azure Active Directory**를 선택한 다음 **엔터프라이즈 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="ee902-119">**환자 (dev)** 라는 행을 찾은 다음 **개체 ID** 열의 값을 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="ee902-120">![Azure 포털의 환자 (dev) 행 스크린샷](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="ee902-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="ee902-121">환자 app을 검색 하거나 리소스를 탐색 하 여 연결 하려는 FTO r 리소스 인스턴스로 이동 하 여 해당 인스턴스에 대 한 설정을 엽니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="ee902-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure 포털의 FTO r 인스턴스 설정에 대 한 Azure API 스크린샷](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="ee902-123">**인증**을 클릭 한 다음 3 단계에서 복사한 개체 Id를 **허용 된 개체 id** 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="ee902-124">이렇게 하면 환자 앱이 FTO r 서버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="ee902-125">개체 ID를 붙여 넣으면 Azure Active Directory에서 유효성을 검사 하 고 녹색 확인 표시가 그 옆에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 포털의 인증 설정 스크린샷](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="ee902-127">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-127">Click **Save**.</span></span> <span data-ttu-id="ee902-128">이렇게 하면 인스턴스가 다시 배포 되 고 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="ee902-129">**개요**를 클릭 한 다음 **fa r 메타 데이터 끝점**에서 URL을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="ee902-130">메타 데이터 태그를 제거 하 여 FA r 서버 URL을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="ee902-131">예를 https://test02-teamshealth.azurehealthcareapis.com/들어.</span><span class="sxs-lookup"><span data-stu-id="ee902-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure 포털의 메타 데이터 끝점 스크린샷](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="ee902-133">팀에서 팀에 로드 된 환자 app 인스턴스로 이동 하 고 **설정을**클릭 한 다음 **링크** 상자에 fgo r 서버 끝점 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="ee902-134">그런 다음 연결 **을 클릭 하 여 연결** 을 설정 하 고 검색 하 여 목록에 환자 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![팀의 환자 앱 설정 스크린샷](../../media/patients-app-teams.png)
    
    <span data-ttu-id="ee902-136">이 단계에서 팀에 연결 하는 동안 오류가 [발생 하는](mailto:teamsforhealthcare@service.microsoft.com)경우 오류에 대 한 자세한 스크린샷, 전자 메일에서 "환자 APP-emr 모드 문제 해결"의 제목 줄이 있는 [Fiddler](https://www.telerik.com/download/fiddler) 및 다른 재현 단계의 로그를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee902-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee902-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ee902-137">Related topics</span></span>

- [<span data-ttu-id="ee902-138">환자 앱 개요</span><span class="sxs-lookup"><span data-stu-id="ee902-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="ee902-139">Microsoft Teams에 전자 의료 레코드 통합</span><span class="sxs-lookup"><span data-stu-id="ee902-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
