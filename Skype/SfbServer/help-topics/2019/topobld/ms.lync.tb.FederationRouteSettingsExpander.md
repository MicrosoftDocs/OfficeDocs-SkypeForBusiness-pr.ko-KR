---
title: 페더레이션 경로 지정 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 사이트 페더레이션 경로 할당을 설정 하려면 먼저 Edge 서버 또는 Edge 서버 풀에 페더레이션을 사용 하도록 설정 해야 합니다. Edge 서버 또는 풀에서 페더레이션을 사용할 수 없는 경우에는 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.
ms.openlocfilehash: fafc576e3fd3a3c33d17728437c8472eaf1a57e9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793696"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="23e79-104">페더레이션 경로 지정 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="23e79-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="23e79-105">사이트 페더레이션 경로 할당을 설정 하려면 먼저 Edge 서버 또는 Edge 서버 풀에 페더레이션을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="23e79-106">Edge 서버 또는 풀에서 페더레이션을 사용할 수 없는 경우에는 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="23e79-107">Edge 서버 또는 풀의 페더레이션 설정이 구성 된 경우 다음 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="23e79-108">**모든 사이트에 페더레이션 경로 할당 허용** 이 설정은 모든 사이트에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="23e79-109">이 사이트에서 구성 하는 설정이 모든 사이트에 적합 한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="23e79-110">**SIP 페더레이션 사용** 이 옵션을 선택 하 여 SIP 페더레이션 경로를 사용 하도록 설정한 다음 디렉터 또는 Edge 풀을 페더레이션 경로로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="23e79-111">**XMPP 페더레이션 사용** XMPP 페더레이션 경로를 사용 하도록 설정 하려면이 옵션을 선택 하 고 페더레이션 경로로 디렉터 또는 Edge 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="23e79-112">XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23e79-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="23e79-113">자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23e79-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

