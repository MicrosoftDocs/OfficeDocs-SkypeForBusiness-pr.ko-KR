---
title: 비즈니스용 Skype 서버에서 영구 채팅 구성 요소 설치
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '요약: 이 항목을 통해 비즈니스용 Skype 서버 배포 마법사를 사용하여 비즈니스용 Skype 서버 2015 구성 요소 및 서비스를 설치하는 방법을 설명합니다.'
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802088"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="ff19c-103">비즈니스용 Skype 서버에서 영구 채팅 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="ff19c-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ff19c-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 배포 마법사를 사용하여 비즈니스용 Skype 서버 2015 구성 요소 및 서비스를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff19c-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="ff19c-105">영구 채팅 구성 요소를 설치하기 전에 사전 구성 요소 하드웨어 및 소프트웨어를 이미 설치하고 영구 채팅 서버를 지원하기 위한 적절한 토폴로지가 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff19c-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="ff19c-106">계획 및 요구 사항에 대한 자세한 내용은 비즈니스용 [Skype](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 환경 요구 사항 및 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)영구 채팅 서버 계획에 대한 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff19c-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="ff19c-107">영구 채팅 서버를 포함하기 위해 토폴로지 업데이트 및 게시 방법에 대한 자세한 내용은 영구 채팅 서버 추가를 비즈니스용 [Skype 서버 2015](add-persistent-chat-server.md)토폴로지에서 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff19c-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="ff19c-108">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff19c-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ff19c-109">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff19c-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="ff19c-110">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="ff19c-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ff19c-111">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff19c-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="ff19c-112">서비스 설치 및 시작</span><span class="sxs-lookup"><span data-stu-id="ff19c-112">Install and start services</span></span>

<span data-ttu-id="ff19c-113">비즈니스용 Skype 서버 배포 마법사를 사용하여 비즈니스용 Skype 서버 시스템 설치 또는 업데이트를 선택해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ff19c-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="ff19c-114">로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="ff19c-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="ff19c-115">비즈니스용 Skype 서버 구성 요소 설치 또는 제거</span><span class="sxs-lookup"><span data-stu-id="ff19c-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="ff19c-116">인증서 요청, 설치 또는 할당</span><span class="sxs-lookup"><span data-stu-id="ff19c-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="ff19c-117">서비스 시작</span><span class="sxs-lookup"><span data-stu-id="ff19c-117">Start services</span></span>
    
<span data-ttu-id="ff19c-118">배포 마법사를 사용하여 구성 요소를 설치하고, 인증서를 할당하고, 서비스를 시작하는 방법에 대한 자세한 내용은 토폴로지의 서버에 [비즈니스용 Skype 서버 2015](../../deploy/install/install.md) 설치 및 비즈니스용 [Skype 서버 2015](../../deploy/install/install-skype-for-business-server.md)설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff19c-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

