---
title: 이사 (계획 도구)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: 디렉터는 사용자 요청을 인증할 수 있는 비즈니스용 Skype 서버 2015 통신 소프트웨어를 실행 하는 서버 이며, 어떠한 사용자 계정도 홈이 아닙니다.
ms.openlocfilehash: 7ce22dadf636d4e7b5e609fc5b3fea9a1891fadd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816477"
---
# <a name="director-planning-tool"></a><span data-ttu-id="1b282-103">이사 (계획 도구)</span><span class="sxs-lookup"><span data-stu-id="1b282-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="1b282-104">디렉터는 사용자 요청을 인증할 수 있는 비즈니스용 Skype 서버 2015 통신 소프트웨어를 실행 하는 서버 이며, 어떠한 사용자 계정도 홈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="1b282-105">이 역할은 선택 사항이 며 다음 두 가지 시나리오에서 디렉터 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="1b282-106">외부 사용자가 Edge 서버를 배포 하 여 액세스를 사용 하도록 설정 하는 경우에도 디렉터를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="1b282-107">이 시나리오에서 디렉터는 외부 사용자를 인증 한 다음 해당 트래픽을 내부 서버에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="1b282-108">디렉터를 사용 하 여 외부 사용자를 인증 하는 경우 프런트 엔드 풀 서버는 이러한 사용자의 인증을 수행 하는 오버 헤드에서 부담 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="1b282-109">또한 서비스 거부 공격과 같은 악의적인 트래픽에 대 한 내부 프런트 엔드 풀을 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="1b282-110">네트워크에 이러한 공격으로 인 한 잘못 된 외부 트래픽이 발생 하는 경우,이 소통량이 디렉터에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="1b282-111">중앙 사이트에 여러 프런트 엔드 풀을 배포 하는 경우 해당 사이트에 디렉터를 추가 하면 인증 요청을 합리화 하 고 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="1b282-112">이 시나리오에서는 모든 요청이 먼저 디렉터로 이동한 다음 올바른 프런트 엔드 풀에 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1b282-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

