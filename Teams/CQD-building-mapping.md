---
title: CQD (통화 품질 대시보드) 용 건물 지도 만들기
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 테 넌 트를 업로드 하 고 CQD (통화 품질 대시보드에서) 데이터를 작성 하는 데 사용할 수 있는 건물 지도를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086099"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="4444f-103">CQD (통화 품질 대시보드) 용 건물 지도 만들기</span><span class="sxs-lookup"><span data-stu-id="4444f-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="4444f-104">Microsoft 팀 또는 비즈니스용 Skype Online 배포의 경우 모든 클라이언트가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="4444f-105">따라서 기본적으로 모든 클라이언트는 클라이언트가 내부 회사 네트워크에 연결 되어 있는지 여부에 관계 없이 CQD (통화 품질 대시보드) 외부로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="4444f-106">CQD를 사용 하는 경우 끝점의 위치를 알고 있어야 하며 관리할 수 있는 네트워크에 연결 되었는지 또는 관리할 수 없는 네트워크만을 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="4444f-107">CQD에 서브넷 및 빌드 정보를 업로드 하면 CQD를 사용 하 여 끝점이 내부 (관리) 네트워크 또는 외부 (관리) 네트워크에 연결 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="4444f-108">이 때문에 조직에 대 한 건물 지도를 만들고 [CQD에 업로드](CQD-upload-tenant-building-data.md)하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="4444f-109">빌드 매핑 도구</span><span class="sxs-lookup"><span data-stu-id="4444f-109">Building mapping tools</span></span>

<span data-ttu-id="4444f-110">조직의 서브넷을 매핑하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="4444f-111">도움이 필요한 경우이 [블로그 게시물](https://aka.ms/cqdtools)에서 설명 하는 CQDTools PowerShell 모듈을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="4444f-112">이러한 도구는 PowerShell을 기반으로 하며 AD (Active Directory) 사이트 및 서비스와 Microsoft DHCP 서비스를 사용 하 여 문서 파일을 미리 채울 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="4444f-113">이러한 도구는 다음 작업을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="4444f-114">광고 사이트 및 서비스를 쿼리하고에 포함 된 정보를 기반으로 문서 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="4444f-115">Microsoft DHCP 서버를 쿼리하여 서브넷 정보를 가져오고 자동으로 문서 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="4444f-116">기존 문서 파일의 유효성을 검사 하 고 중복 항목이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="4444f-117">CQD에서 매핑되지 않은 서브넷을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4444f-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4444f-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4444f-118">Related topics</span></span>

[<span data-ttu-id="4444f-119">테 넌 트 업로드 및 CQD에 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="4444f-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)