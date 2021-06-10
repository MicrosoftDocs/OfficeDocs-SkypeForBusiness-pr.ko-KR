---
title: CQD(통화 품질 대시보드)에 대한 건물 맵 만들기
ms.author: serdars
author: SerdarSoysal
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
description: CQD(통화 품질 대시보드)에서 테넌트 업로드 및 데이터 작성에 사용할 수 있는 건물 맵을 만드는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584037"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="4e2db-103">CQD(통화 품질 대시보드)에 대한 건물 맵 만들기</span><span class="sxs-lookup"><span data-stu-id="4e2db-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="4e2db-104">온라인 Microsoft Teams 비즈니스용 Skype 모든 클라이언트는 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="4e2db-105">결과적으로 클라이언트가 내부 회사 네트워크에 연결되어 있는지 여부에 관계없이 기본적으로 모든 클라이언트가 CQD(통화 품질 대시보드)에서 외부로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="4e2db-106">CQD를 사용할 때 엔드포인트의 위치와 관리할 수 있는 네트워크에 연결되어 있는지 또는 관리할 수 없는 네트워크에 연결되어 있는지 여부를 알아야 합니다. 관리할 수 있는 네트워크만 개선할 수 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="4e2db-107">서브넷을 업로드하고 CQD에 정보를 구축하면 CQD를 사용하여 엔드포인트가 내부(관리되는) 네트워크에 연결되어 있는지 또는 외부(관리되지 않는) 네트워크에 연결되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="4e2db-108">조직에 대한 건물 맵을 만들고 [CQD에](CQD-upload-tenant-building-data.md)업로드하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="4e2db-109">매핑 도구 구축</span><span class="sxs-lookup"><span data-stu-id="4e2db-109">Building mapping tools</span></span>

<span data-ttu-id="4e2db-110">조직의 서브넷을 매핑하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="4e2db-111">도움이 필요한 경우 이 블로그 게시물에 설명된 CQDTools PowerShell [모듈을 사용할 수 있습니다.](https://aka.ms/cqdtools)</span><span class="sxs-lookup"><span data-stu-id="4e2db-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="4e2db-112">이러한 도구는 PowerShell을 기반으로 하여 AD(Active Directory) 사이트 및 서비스 및 Microsoft DHCP 서비스를 사용하여 건물 파일을 미리 채우는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="4e2db-113">이러한 도구는 다음 작업에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="4e2db-114">AD 사이트 및 서비스를 쿼리하고 내부에 포함된 정보를 기반으로 건물 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="4e2db-115">Microsoft DHCP 서버 또는 서버를 쿼리하여 서브넷 정보를 끌어오고 자동으로 건물 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="4e2db-116">기존 건물 파일의 유효성을 검사하여 중복 및 겹치는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="4e2db-117">CQD에서 매핑되지 않은 서브넷을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2db-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e2db-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4e2db-118">Related topics</span></span>

[<span data-ttu-id="4e2db-119">업로드 CQD에서 테넌트 및 건물 데이터 저장</span><span class="sxs-lookup"><span data-stu-id="4e2db-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)