---
title: Microsoft 팀에 대 한 통화 분석 설정
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Microsoft 팀 통화 품질 문제를 식별 하 고 해결 하기 위한 사용자 단위 통화 분석을 설정 합니다.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085314"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="b33c8-103">Microsoft 팀에 대 한 통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="b33c8-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="b33c8-104">Microsoft 팀 관리자는 사용자별 통화 분석을 사용 하 여 **개별 사용자**의 팀 통화 품질 및 연결 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="b33c8-105">통화 분석을 최대한 활용 하려면 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="b33c8-106">사용자에 대 한 통화 분석을 볼 수 있도록 헬프 데스크 에이전트 같은 사용자에 게 특수 지원 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="b33c8-107">이러한 지원 역할은 팀의 나머지 관리 센터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="b33c8-108">Tsv 또는 .csv 데이터 파일을 업로드 하 여 사용자 단위 통화 분석에 빌드, 사이트 및 테 넌 트 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="b33c8-109">사용자 단위 통화 분석을 사용할 준비가 되 면 [사용자 단위 통화 분석을 읽어 낮은 통화 품질 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="b33c8-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="b33c8-110">지원 및 헬프 데스크 직원에 대 한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="b33c8-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="b33c8-111">팀 관리자는 모든 사용자에 대 한 분석 정보에 대 한 모든 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="b33c8-112">직원 및 헬프 데스크 에이전트를 지원 하기 위해 할당할 수 있는 일부 특수화 된 Azure Active Directory 역할을 만들어 팀 관리 센터의 나머지 부분에 대 한 액세스 권한 없이 사용자 단위 통화 분석에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="b33c8-113">사용자 단위 통화 분석 (계층 1 지원)의 제한 된 보기를 사용 해야 하는 사용자에 게 **팀 의사 소통 지원 전문가** 역할을 배정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="b33c8-114">사용자 단위 통화 분석 (계층 2 지원)에 대 한 전체 액세스 권한이 필요한 사용자에 게 **팀 의사 소통 지원 엔지니어** 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="b33c8-115">두 역할 모두 팀 관리 센터의 나머지 부분에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="b33c8-116">각 역할이 수행 하는 작업에 대 한 자세한 내용은 [각 팀이 역할을 지 원하는](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b33c8-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="b33c8-117">팀 관리자 역할에 대 한 자세한 내용은 팀 [관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b33c8-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="b33c8-118">Azure Active Directory에서 관리자 역할을 할당 하는 방법에 대 한 자세한 내용은 [Azure Active directory에서 역할 보기 및 지정](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b33c8-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="b33c8-119">Azure Active Directory에서 관리 역할을 할당 하는 방법에 대 한 자세한 내용은 [Azure Active directory에서 역할 보기 및 지정](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b33c8-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="b33c8-120">Tsv 또는 .csv 파일을 업로드 하 여 빌드, 사이트 및 테 넌 트 정보 추가</span><span class="sxs-lookup"><span data-stu-id="b33c8-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="b33c8-121">.Csv 또는 tsv 파일을 업로드 하 여 사용자 단위 통화 분석에 빌드, 사이트 및 테 넌 트 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="b33c8-122">모든 정보를 포함 하 여, call analytics는 IP 주소를 실제 위치로 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="b33c8-123">관리자 및 헬프데스크 상담원은이 정보를 사용 하 여 통화 문제에 대 한 추세를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="b33c8-124">예를 들어 동일한 건물의 사용자가 비슷한 통화 품질 문제를 겪고 있는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b33c8-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="b33c8-125">팀 또는 비즈니스용 Skype 관리자 인 경우 팀 또는 비즈니스용 Skype 통화 품질 대시보드 (CQD)에서 기존 테 넌 트를 사용 하 고 데이터 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="b33c8-126">먼저 CQD에서 파일을 다운로드 한 다음이를 통화 분석에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="b33c8-127">기존 데이터 파일을 다운로드 하려면 **Microsoft 팀 관리 센터**에서  >  **Call Quality Dashboard**  >  **지금 업로드**대시보드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="b33c8-128">**내 업로드** 목록에서 원하는 파일 옆에 있는 **다운로드** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="b33c8-129">새 파일을 업로드 하려면 **Microsoft 팀 관리 센터**  >  **위치로**이동한 다음 **위치 데이터 업로드** 또는 **위치 데이터 바꾸기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33c8-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="b33c8-130">Tsv 또는 .csv 파일을 처음부터 만드는 경우 [테 넌 트 업로드 및 데이터 작성](CQD-upload-tenant-building-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b33c8-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b33c8-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b33c8-131">Related topics</span></span>

[<span data-ttu-id="b33c8-132">사용자 단위 통화 분석을 사용 하 여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b33c8-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="b33c8-133">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b33c8-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
