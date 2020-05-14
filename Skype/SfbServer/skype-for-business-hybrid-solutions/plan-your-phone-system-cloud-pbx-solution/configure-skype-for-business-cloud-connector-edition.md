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
description: 비즈니스용 skype Online에서 온-프레미스 음성 인프라와 전화 시스템 (클라우드 PBX) 음성 서비스의 통합을 사용 하도록 설정 하는 데 필요한 비즈니스용 Skype 클라우드 커넥터 버전을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219518"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="eff89-103">비즈니스용 Skype 클라우드 커넥터 에디션 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="eff89-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="eff89-104">비즈니스용 skype Online에서 온-프레미스 음성 인프라와 전화 시스템 (클라우드 PBX) 음성 서비스의 통합을 사용 하도록 설정 하는 데 필요한 비즈니스용 Skype 클라우드 커넥터 버전을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="eff89-105">시작 하기 전에 [비즈니스용 Skype 클라우드 Connector Edition 계획](plan-skype-for-business-cloud-connector-edition.md)의 필수 구성 요소를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eff89-106">이 항목의 단계는 Cloud Connector Edition 1.4.1 이상에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="eff89-107">클라우드 Connector Edition 2.1로 아직 업그레이드 하지 않은 경우 [새 버전의 클라우드 커넥터로 업그레이드를](upgrade-to-a-new-version-of-cloud-connector.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eff89-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="eff89-108">에서 설치 파일을 다운로드할 수 있습니다 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="eff89-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="eff89-109">비즈니스용 Skype 클라우드 커넥터 버전을 구성 하는 단계</span><span class="sxs-lookup"><span data-stu-id="eff89-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="eff89-110">다음 표에는 클라우드 커넥터 Edition을 설치 하 고 구성 하는 데 필요한 단계가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="eff89-111">**단계**</span><span class="sxs-lookup"><span data-stu-id="eff89-111">**Step**</span></span>|<span data-ttu-id="eff89-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="eff89-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="eff89-113">클라우드 커넥터 어플라이언스 준비</span><span class="sxs-lookup"><span data-stu-id="eff89-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="eff89-114">설치 파일을 다운로드 하 고 인증서를 준비 하며 Hyper-v를 구성 하 고 클라우드 커넥터 배포를 위한 환경을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="eff89-115">클라우드 커넥터에서 단일 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="eff89-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="eff89-116">클라우드 커넥터 배포에 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="eff89-117">클라우드 커넥터에서 여러 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="eff89-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="eff89-118">배포에 사이트를 추가 하 고 단일 및 다중 사이트 배포 간의 차이점에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="eff89-119">Microsoft 365 또는 Office 365 조직과의 클라우드 커넥터 통합 구성</span><span class="sxs-lookup"><span data-stu-id="eff89-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="eff89-120">DNS 레코드 추가, 하이브리드 구성, PSTN 게이트웨이 설정 및 전화 시스템 음성 메일에 대해 사용자를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="eff89-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="eff89-121">클라우드 커넥터 배포 확인</span><span class="sxs-lookup"><span data-stu-id="eff89-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="eff89-122">배포가 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="eff89-123">클라우드 커넥터의 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="eff89-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="eff89-124">기존 클라우드 커넥터 배포를 버전 2.1으로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="eff89-125">기존 클라우드 커넥터 배포의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="eff89-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="eff89-126">클라우드 커넥터를 이미 배포한 후에 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="eff89-127">클라우드 커넥터 Edition에 미디어 바이패스 배포</span><span class="sxs-lookup"><span data-stu-id="eff89-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="eff89-128">클라우드 커넥터에 미디어 바이패스를 배포 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="eff89-129">클라우드 커넥터 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="eff89-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="eff89-130">클라우드 커넥터에 사용 되는 PowerShell cmdlet에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="eff89-131">클라우드 커넥터 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="eff89-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="eff89-132">클라우드 커넥터 배포 시 발생 하는 일반적인 문제에 대 한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="eff89-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

