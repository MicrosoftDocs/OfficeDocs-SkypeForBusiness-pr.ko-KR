---
title: 영구 채팅 구성 요소 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '요약: 비즈니스용 Skype 서버 배포 마법사를 사용 하 여 비즈니스용 Skype 서버 2015 구성 요소 및 서비스를 설치 하는 방법을 알아보려면이 항목을 읽으십시오.'
ms.openlocfilehash: 5b8205cb2ab828001eae76eeaab8cd4f697c9315
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234750"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="3702f-103">영구 채팅 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="3702f-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3702f-104">**요약:** 비즈니스용 Skype 서버 배포 마법사를 사용 하 여 비즈니스용 Skype 서버 2015 구성 요소 및 서비스를 설치 하는 방법을 알아보려면이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3702f-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="3702f-105">영구 채팅 구성 요소를 설치 하기 전에 먼저 필수 하드웨어 및 소프트웨어를 설치 했는지 확인 하 고 영구 채팅 서버를 지원 하기 위해 적절 한 토폴로지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3702f-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="3702f-106">계획 및 요구 사항에 대 한 자세한 내용은 비즈니스용 [skype 환경에 대 한 요구 사항과](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 비즈니스용 [skype 서버 2015의 영구 채팅 서버](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)에 대 한 계획을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3702f-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="3702f-107">영구 채팅 서버를 포함 하도록 토폴로지를 업데이트 하 고 게시 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype Server 2015 토폴로지에 영구 채팅 서버 추가](add-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3702f-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="3702f-108">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3702f-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3702f-109">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3702f-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="3702f-110">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="3702f-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="3702f-111">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3702f-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="3702f-112">서비스 설치 및 시작</span><span class="sxs-lookup"><span data-stu-id="3702f-112">Install and start services</span></span>

<span data-ttu-id="3702f-113">비즈니스용 Skype 서버 배포 마법사를 사용 하 여 다음 단계를 수행 하려면 비즈니스용 Skype Server System 설치 또는 업데이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3702f-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="3702f-114">로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="3702f-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="3702f-115">비즈니스용 Skype 서버 구성 요소 설치 또는 제거</span><span class="sxs-lookup"><span data-stu-id="3702f-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="3702f-116">인증서 요청, 설치 또는 할당</span><span class="sxs-lookup"><span data-stu-id="3702f-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="3702f-117">서비스 시작</span><span class="sxs-lookup"><span data-stu-id="3702f-117">Start services</span></span>
    
<span data-ttu-id="3702f-118">배포 마법사를 사용 하 여 구성 요소를 설치 하 고, 인증서를 할당 하 고, 서비스를 시작 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015 설치](../../deploy/install/install.md) 및 [토폴로지의 서버에 비즈니스용 Skype server 2015 설치](../../deploy/install/install-skype-for-business-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3702f-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

