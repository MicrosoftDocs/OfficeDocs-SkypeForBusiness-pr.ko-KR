---
title: 페더레이션 경로 지정 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
description: 사이트 페더레이션 경로 할당을 설정하려면 먼저 에지 서버 또는 에지 서버 풀에서 페더레이션을 사용하도록 설정해야 합니다. 에지 서버 또는 풀에서 페더레이션을 사용하도록 설정하지 않은 경우 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.
ms.openlocfilehash: 4e0bc987cb64c52fae816b39a87b5fed081bf143
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215559"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="14974-104">페더레이션 경로 지정 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="14974-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="14974-p102">사이트 페더레이션 경로 할당을 설정하려면 먼저 에지 서버 또는 에지 서버 풀에서 페더레이션을 사용하도록 설정해야 합니다. 에지 서버 또는 풀에서 페더레이션을 사용하도록 설정하지 않은 경우 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14974-p102">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool. If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>
  

<span data-ttu-id="14974-107">에 지 서버 또는 풀에서 페더레이션 설정을 구성한 경우 다음 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14974-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="14974-108">**모든 사이트에 대해 페더레이션 경로 할당 허용** 이 설정은 모든 사이트에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14974-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="14974-109">이 사이트에서 구성하는 설정이 모든 사이트에 대해 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14974-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="14974-110">**SIP 페더레이션 사용** SIP 페더레이션 경로를 사용 하도록 설정 하려면이 옵션을 선택한 후에 디렉터 또는에 지 풀을 페더레이션 경로로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14974-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="14974-111">**XMPP 페더레이션 사용** XMPP 페더레이션 경로를 사용 하도록 설정 하려면이 옵션을 선택한 다음 디렉터 또는에 지 풀을 페더레이션 경로로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14974-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    

