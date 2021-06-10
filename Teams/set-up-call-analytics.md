---
title: 통화에 대한 호출 분석 Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: 통화 품질 문제를 식별하고 문제를 Microsoft Teams 사용자당 통화 분석을 설정합니다.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117136"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="1b79d-103">통화에 대한 호출 분석 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b79d-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="1b79d-104">관리자 Microsoft Teams 사용자별 통화 분석을 사용하여 개별 사용자의 통화 품질 및 연결 Teams 문제를 해결할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1b79d-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="1b79d-105">호출 분석을 활용하기 위해 다음을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="1b79d-106">사용자에 대한 호출 분석을 볼 수 있도록 헬프데스크 에이전트와 같은 사용자에게 특수한 지원 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="1b79d-107">이러한 지원 역할은 관리 센터의 나머지 Teams 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="1b79d-108">.tsv 또는 데이터 파일을 업로드하여 사용자당 호출 분석에 건물, 사이트 및 .csv 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="1b79d-109">사용자당 통화 분석을 사용할 준비가 됐을 때 사용자당 통화 분석을 사용하여 통화 품질이 좋지 않은 문제를 [해결하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="1b79d-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="1b79d-110">지원 및 헬프데스크 직원에게 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="1b79d-111">관리자 Teams 모든 사용자에 대한 분석 정보를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="1b79d-112">지원 담당자 및 Azure Active Directory 지원 팀에 할당할 수 있는 몇 가지 전문화된 역할이 만들어졌습니다(나머지 관리자 센터에 대한 액세스 없이도 사용자당 통화 분석에 액세스할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="1b79d-113">사용자 **Teams** 호출 분석의 제한된 보기가 있는 사용자에게 통신 지원 전문가 역할을 할당합니다(계층 1 지원).</span><span class="sxs-lookup"><span data-stu-id="1b79d-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="1b79d-114">사용자 **Teams** 호출 분석에 대한 전체 액세스가 필요한 사용자에게 통신 지원 엔지니어 역할을 할당합니다(계층 2 지원).</span><span class="sxs-lookup"><span data-stu-id="1b79d-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="1b79d-115">두 역할 모두 관리 센터의 나머지 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="1b79d-116">이러한 각 역할이 무엇을 하는지 알아보고 각 지원 역할이 Teams [를 읽어보세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="1b79d-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="1b79d-117">관리자 역할에 대한 Teams 자세한 내용은 [Teams](using-admin-roles.md)관리자 역할 사용 을 Teams.</span><span class="sxs-lookup"><span data-stu-id="1b79d-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="1b79d-118">에서 관리자 역할을 할당하는 방법을 알아보 Azure Active Directory 에서 역할 보기 및 [할당을 Azure Active Directory.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="1b79d-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="1b79d-119">에서 관리 역할을 할당하는 방법을 알아보 Azure Active Directory 에서 역할 보기 [및 할당을 Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="1b79d-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="1b79d-120">업로드.tsv 또는 .csv 파일에서 건물, 사이트 및 테넌트 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="1b79d-121">파일 또는 .tsv 파일을 업로드하여 사용자당 호출 분석에 건물, 사이트 및 테넌트 정보를 .csv 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="1b79d-122">이 모든 정보를 사용하여 호출 분석은 IP 주소를 물리적 위치에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="1b79d-123">관리자 및 헬프데스크 에이전트는 이 정보를 사용하여 통화 문제의 추세를 파악하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="1b79d-124">예를 들어 같은 건물에 있는 사용자가 비슷한 통화 품질 문제가 있는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="1b79d-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="1b79d-125">사용자 또는 Teams 비즈니스용 Skype CQD(전화 품질 대시보드)에서 기존 테넌트 및 Teams 비즈니스용 Skype 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="1b79d-126">먼저 CQD에서 파일을 다운로드한 다음, 업로드하여 분석을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="1b79d-127">기존 데이터 파일을 다운로드하려면 지금 Microsoft Teams 관리 센터 전화 품질 **대시보드** 업로드  >    >  **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="1b79d-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="1b79d-128">내 **업로드 목록에서** 원하는 파일 **옆에** 있는 다운로드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="1b79d-129">새 파일을 업로드하려면 Microsoft Teams 관리 센터 위치로 이동한 다음 위치 업로드 데이터 바꾸기  >   **를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="1b79d-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="1b79d-130">.tsv 또는 .csv 파일을 만드는 경우 테넌트 및 업로드 [참조합니다.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="1b79d-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b79d-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1b79d-131">Related topics</span></span>

[<span data-ttu-id="1b79d-132">사용자당 통화 분석을 사용하여 통화 품질이 좋지 않은 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="1b79d-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="1b79d-133">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1b79d-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)