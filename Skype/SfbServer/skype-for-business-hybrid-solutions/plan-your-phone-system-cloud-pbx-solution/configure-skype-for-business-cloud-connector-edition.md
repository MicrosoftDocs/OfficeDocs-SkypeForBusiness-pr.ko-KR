---
title: 비즈니스용 Skype 클라우드 커넥터 버전 구성 및 관리
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 비즈니스용 Skype Online의 전화 시스템(클라우드 PBX) 음성 서비스와의 통합을 가능하게 하는 최소의 사내 토폴로지인 비즈니스용 Skype 클라우드 커넥터 Edition을 구성하는 방법을 학습합니다.
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094876"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="6986d-103">비즈니스용 Skype 클라우드 커넥터 버전 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="6986d-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="6986d-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="6986d-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="6986d-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="6986d-106">비즈니스용 Skype Online의 전화 시스템(클라우드 PBX) 음성 서비스와의 통합을 가능하게 하는 최소의 사내 토폴로지인 비즈니스용 Skype 클라우드 커넥터 Edition을 구성하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="6986d-107">시작하기 전에 Plan for Skype for Business Cloud Connector Edition 의 선행 [준비를 검토해야 합니다.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="6986d-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6986d-108">이 항목의 단계는 Cloud Connector Edition 1.4.1 이상에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="6986d-109">아직 Cloud Connector Edition 2.1로 업그레이드하지 않은 경우 새 버전의 클라우드 커넥터로 [업그레이드를 참조합니다.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="6986d-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="6986d-110">에서 설치 파일을 다운로드할 수 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="6986d-111">비즈니스용 Skype 클라우드 커넥터 버전 구성 단계</span><span class="sxs-lookup"><span data-stu-id="6986d-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="6986d-112">다음 표에는 Cloud Connector Edition을 설치 및 구성하는 데 필요한 단계가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="6986d-113">**단계**</span><span class="sxs-lookup"><span data-stu-id="6986d-113">**Step**</span></span>|<span data-ttu-id="6986d-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="6986d-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6986d-115">클라우드 커넥터 어플라이언스 준비</span><span class="sxs-lookup"><span data-stu-id="6986d-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="6986d-116">설치 파일을 다운로드하고, 인증서를 준비하고, Hyper-V, 클라우드 커넥터 배포를 위한 환경을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="6986d-117">클라우드 커넥터에서 단일 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="6986d-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="6986d-118">클라우드 커넥터 배포에서 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="6986d-119">클라우드 커넥터에서 여러 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="6986d-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="6986d-120">배포에 사이트를 추가하고 단일 사이트 배포와 다중 사이트 배포 간의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="6986d-121">Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합 구성</span><span class="sxs-lookup"><span data-stu-id="6986d-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="6986d-122">DNS 레코드를 추가하고, 하이브리드를 구성하고, PSTN 게이트웨이를 설정하고, 사용자가 전화 시스템 음성 메일을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="6986d-123">클라우드 커넥터 배포 확인</span><span class="sxs-lookup"><span data-stu-id="6986d-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6986d-124">배포가 올바르게 작동하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="6986d-125">클라우드 커넥터의 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="6986d-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="6986d-126">기존 클라우드 커넥터 배포를 버전 2.1로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="6986d-127">기존 클라우드 커넥터 배포의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="6986d-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6986d-128">클라우드 커넥터가 이미 배포된 후 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="6986d-129">클라우드 커넥터 버전에서 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="6986d-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="6986d-130">클라우드 커넥터에서 미디어 우회를 배포하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="6986d-131">클라우드 커넥터 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="6986d-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="6986d-132">클라우드 커넥터에서 사용되는 PowerShell cmdlet에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6986d-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="6986d-133">클라우드 커넥터 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6986d-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6986d-134">클라우드 커넥터 배포에서 발생하는 일반적인 문제에 대한 해결 방법</span><span class="sxs-lookup"><span data-stu-id="6986d-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
