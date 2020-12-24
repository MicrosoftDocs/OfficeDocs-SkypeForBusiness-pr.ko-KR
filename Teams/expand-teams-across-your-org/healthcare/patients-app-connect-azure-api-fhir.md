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
description: Microsoft Teams의 환자 앱을 FHIR용 Azure API(Fast Healthcare 상호 연동성 리소스)에 연결하는 방법을 설명합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731156"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="f8de4-103">환자 앱을 FHIR용 Azure API에 연결</span><span class="sxs-lookup"><span data-stu-id="f8de4-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="f8de4-104">2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="f8de4-105">환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="f8de4-106">환자 앱과 연결된 모든 데이터는 이 그룹에 유지되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="f8de4-107">사용자는 목록 앱을 사용하여 목록을 다시 [만들 수 있습니다.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="f8de4-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="f8de4-108">목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="f8de4-109">시작을 위해 목록에서 환자 서식 파일을 확인해 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8de4-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="f8de4-110">조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 목록 앱 [관리를 참조하세요.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="f8de4-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="f8de4-111">다음 단계에 따라 Microsoft Teams의 환자 앱이 FHIR 인스턴스용 Azure API에 액세스할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="f8de4-112">이 문서에서는 [FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 인스턴스용 Azure API가 테넌트에 설정 및 구성되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="f8de4-113">테넌트에서 FHIR용 Azure API 인스턴스를 아직 만들지 않은 경우 빠른 시작: Azure Portal을 사용하여 [FHIR용 Azure API](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8de4-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="f8de4-114">환자 [앱에](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 대한 관리자 동의를 부여하려면 여기를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="f8de4-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="f8de4-115">메시지가 표시될 때 테넌트 관리자 또는 전역 관리자 자격 증명을 사용하여 로그인한 다음 **수락을** 클릭하여 필요한 사용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![환자 앱에 대한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="f8de4-117">수락한 후 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-117">After you accept, close the window.</span></span> <span data-ttu-id="f8de4-118">다음과 같은 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="f8de4-119">페이지에서 오류 메시지를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="f8de4-120">이는 무해하며 동의가 부여된 것 을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="f8de4-121">(이 URL에 대해 보다 친숙한 페이지에서 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="f8de4-122">계속 지켜봐 주세요!)</span><span class="sxs-lookup"><span data-stu-id="f8de4-122">Stay tuned!)</span></span>

    ![환자 앱에 대한 사용 권한 요청 스크린샷](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="f8de4-124">관리자 자격 [증명을 사용하여 Azure Portal에](https://portal.azure.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="f8de4-125">왼쪽 탐색에서 **Azure Active Directory를 선택한** 다음 엔터프라이즈 **애플리케이션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8de4-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="f8de4-126">**Patients(개발)라는** 행을 찾아 개체 **ID** 열의 값을 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Azure Portal의 환자(개발) 행 스크린샷](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="f8de4-128">환자 앱을 연결하려는 FHIR용 Azure API 리소스 인스턴스로 이동한 다음(해당 앱을 검색하거나 리소스를 검색하여) 해당 인스턴스에 대한 설정을 여습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure Portal의 FHIR 인스턴스용 Azure API 인스턴스 설정 스크린샷](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="f8de4-130">**인증을** 클릭한 다음 3단계에서 복사한 개체 ID를 허용된 개체 ID 상자에 **붙여넣습니다.**</span><span class="sxs-lookup"><span data-stu-id="f8de4-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="f8de4-131">이렇게 하면 환자 앱이 FHIR 서버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="f8de4-132">개체 ID를 붙여넣은 후 Azure Active Directory에서 유효성을 검사하고 옆에 녹색 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure Portal의 인증 설정 스크린샷](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="f8de4-134">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-134">Click **Save**.</span></span> <span data-ttu-id="f8de4-135">몇 분 정도 걸릴 수 있는 인스턴스를 다시 재배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="f8de4-136">**개요를** 클릭한 다음 FHIR 메타데이터 엔드포인트에서 **URL을 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8de4-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="f8de4-137">메타데이터 태그를 제거하여 FHIR 서버 URL을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="f8de4-138">예: `https://test02-teamshealth.azurehealthcareapis.com/`</span><span class="sxs-lookup"><span data-stu-id="f8de4-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Azure Portal의 메타데이터 엔드포인트](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="f8de4-140">Teams에서 팀에 로드된 Patients 앱 인스턴스로 이동하여 설정을 클릭한 다음 링크 **상자에** FHIR 서버 엔드포인트 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="f8de4-141">그런 다음 **연결을 설정하고** 검색하고 환자를 목록에 추가하려면 연결을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8de4-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="f8de4-142">Teams의 환자 앱 설정</span><span class="sxs-lookup"><span data-stu-id="f8de4-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="f8de4-143">이 단계에서 Teams에 연결할 때 오류가 발생하면 "Patients App – EMR mode troubleshooting"의 제목 줄이 있는 전자 메일의 오류, [Fiddler의](https://www.telerik.com/download/fiddler) 로그 및 기타 재현 단계에 대한 자세한 [스크린샷을](mailto:teamsforhealthcare@service.microsoft.com)teamsforhealthcare@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f8de4-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8de4-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f8de4-144">Related topics</span></span>

- [<span data-ttu-id="f8de4-145">환자 앱 개요</span><span class="sxs-lookup"><span data-stu-id="f8de4-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="f8de4-146">Microsoft Teams에 전자 의료 레코드 통합</span><span class="sxs-lookup"><span data-stu-id="f8de4-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
