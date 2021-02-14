---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이전 버전에서는 XMPP 배포와의 페더럴을 허용하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP(Extensible Messaging and Presence Protocol) 게이트웨이를 제공했습니다. XMPP 기능은 비즈니스용 Skype & 더 이상 사용할 수 없습니다. XMPP 기능을 계속 사용하려는 경우 레거시 버전(비즈니스용 Skype 서버 2015/ Lync Server 2013)이 있는 동시 사용 환경에서 사용할 수 있습니다. XMPP 기능은 레거시 에지 서버에서 실행되는 XMPP 프록시와 레거시 프런트 엔드 서버에서 실행되는 XMPP 게이트웨이의 두 부분으로 설치됩니다.
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752650"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="bfa89-106">XMPP 페더레이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="bfa89-106">Migrating XMPP federation</span></span>

<span data-ttu-id="bfa89-107">이전 버전에서는 XMPP 배포와의 페더럴을 허용하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP(Extensible Messaging and Presence Protocol) 게이트웨이를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="bfa89-108">XMPP 기능은 더 이상 사용할 수 없습니다. 비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="bfa89-109">XMPP 기능을 계속 사용하려는 경우 레거시 버전(비즈니스용 Skype 서버 2015 또는 Lync Server 2013)이 있는 동시 사용 환경에서 이 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="bfa89-110">XMPP 기능은 레거시 에지 서버에서 실행되는 XMPP 프록시와 레거시 프런트 엔드 서버에서 실행되는 XMPP 게이트웨이의 두 부분으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="bfa89-111">마이그레이션 관점에서 XMPP 기능을 사용하려는 사용자는 레거시 서버에 유지되고 비즈니스용 Skype 서버 2019 풀로 이동하지 말고 레거시 XMPP 게이트웨이를 계속 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="bfa89-112">이는 비즈니스용 Skype 서버 2015 또는 Lync Server 2013에서 XMPP 페더럴 파트너가 구성된 경우만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="bfa89-113">XMPP 기능을 계속 사용하려면 레거시 에지 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="bfa89-114">그러나 레거시 에지 서버(XMPP 프록시 사용)와 비즈니스용 Skype 2019 에지 서버를 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa89-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

