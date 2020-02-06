---
title: 비즈니스용 Skype 클라우드 커넥터 에디션 구성 및 관리
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
description: 비즈니스용 Skype Online에서 Office 365 (클라우드 PBX) 음성 서비스의 휴대폰 시스템을 사용 하 여 온-프레미스 음성 인프라를 통합할 수 있도록 하는 비즈니스용 Skype 클라우드 커넥터 에디션을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 5966fb4cc6bd7bd09e82f4a2907420f657a9097c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799738"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="68c68-103">비즈니스용 Skype 클라우드 커넥터 에디션 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="68c68-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="68c68-104">비즈니스용 Skype Online에서 Office 365 (클라우드 PBX) 음성 서비스의 휴대폰 시스템을 사용 하 여 온-프레미스 음성 인프라를 통합할 수 있도록 하는 비즈니스용 Skype 클라우드 커넥터 에디션을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="68c68-105">시작 하기 전에 [비즈니스용 Skype 클라우드 커넥터 에디션 계획](plan-skype-for-business-cloud-connector-edition.md)의 필수 구성 요소를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68c68-106">이 항목의 단계는 클라우드 커넥터 에디션 1.4.1 이상에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="68c68-107">Cloud Connector Edition 2.1으로 아직 업그레이드 하지 않은 경우 [새 버전의 클라우드 커넥터로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68c68-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="68c68-108">에서 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)설치 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="68c68-109">비즈니스용 Skype 클라우드 커넥터 에디션을 구성 하는 단계</span><span class="sxs-lookup"><span data-stu-id="68c68-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="68c68-110">다음 표에는 클라우드 커넥터 에디션을 설치 하 고 구성 하는 데 필요한 단계가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="68c68-111">**단계만**</span><span class="sxs-lookup"><span data-stu-id="68c68-111">**Step**</span></span>|<span data-ttu-id="68c68-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="68c68-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="68c68-113">클라우드 커넥터 어플라이언스 준비</span><span class="sxs-lookup"><span data-stu-id="68c68-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="68c68-114">설치 파일을 다운로드 하 고, 인증서를 준비 하 고, Hyper-v를 구성 하 고, 클라우드 커넥터 배포를 위한 환경을 준비 하세요.</span><span class="sxs-lookup"><span data-stu-id="68c68-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="68c68-115">클라우드 커넥터에서 단일 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="68c68-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="68c68-116">클라우드 커넥터 배포에 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="68c68-117">클라우드 커넥터에서 여러 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="68c68-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="68c68-118">배포에 사이트를 추가 하 고 단일 및 다중 사이트 배포 간의 차이점에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="68c68-119">Office 365 테넌트와 클라우드 커넥터 통합을 구성</span><span class="sxs-lookup"><span data-stu-id="68c68-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="68c68-120">Office 365 음성 메일에서 DNS 레코드를 추가 하 고, 하이브리드을 구성 하 고, PSTN 게이트웨이를 설정 하 고, 전화 시스템용 사용자를 사용할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="68c68-121">클라우드 커넥터 배포 확인</span><span class="sxs-lookup"><span data-stu-id="68c68-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="68c68-122">배포가 올바르게 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="68c68-123">클라우드 커넥터의 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="68c68-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="68c68-124">기존 클라우드 커넥터 배포를 버전 2.1으로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="68c68-125">기존 클라우드 커넥터 배포의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="68c68-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="68c68-126">클라우드 커넥터를 이미 배포한 후에 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="68c68-127">클라우드 커넥터 에디션에 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="68c68-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="68c68-128">클라우드 커넥터에서 미디어 바이패스를 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="68c68-129">클라우드 커넥터 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="68c68-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="68c68-130">클라우드 커넥터에 사용 되는 PowerShell cmdlet에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="68c68-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="68c68-131">클라우드 커넥터 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="68c68-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="68c68-132">클라우드 커넥터 배포에 발생 한 일반적인 문제에 대 한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="68c68-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

