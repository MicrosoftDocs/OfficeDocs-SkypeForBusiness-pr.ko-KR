---
title: Director(계획 도구)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Director는 사용자 요청을 인증할 수 있지만 사용자 계정을 저장하지는 않는 비즈니스용 Skype 서버 2015 통신 소프트웨어를 실행하는 서버입니다.
ms.openlocfilehash: 76315e9f63e1121119f3823187c379985c4914f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834938"
---
# <a name="director-planning-tool"></a><span data-ttu-id="b98d5-103">Director(계획 도구)</span><span class="sxs-lookup"><span data-stu-id="b98d5-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="b98d5-104">Director는 사용자 요청을 인증할 수 있지만 사용자 계정을 저장하지는 않는 비즈니스용 Skype 서버 2015 통신 소프트웨어를 실행하는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="b98d5-105">이 역할은 선택 사항이며 다음 두 시나리오에서 Director를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="b98d5-106">에지 서버를 배포하여 외부 사용자의 액세스를 사용하도록 설정하는 경우 Director도 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="b98d5-107">이 시나리오에서 감독은 외부 사용자를 인증한 다음 트래픽을 내부 서버로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="b98d5-108">외부 사용자를 인증하는 데 Director를 사용하는 경우 프런트 엔드 풀 서버는 이러한 사용자에 대한 인증 수행 오버헤드를 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="b98d5-109">또한 서비스 거부 공격과 같은 악의적인 트래픽으로부터 내부 프런트 엔드 풀을 보호하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="b98d5-110">네트워크가 이러한 공격에서 잘못된 외부 트래픽으로 넘쳐나면 이 트래픽은 감독에서 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="b98d5-111">중앙 사이트에 여러 프런트 엔드 풀을 배포하는 경우 해당 사이트에 Director를 추가하면 인증 요청을 간소화하고 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="b98d5-112">이 시나리오에서는 모든 요청이 먼저 Director로 이동한 다음 올바른 프런트 엔드 풀로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b98d5-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

