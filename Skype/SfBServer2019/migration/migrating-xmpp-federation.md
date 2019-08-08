---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이전 버전에서는 XMPP 배포와의 페더레이션을 허용 하는 별도의 서버 역할로 배포 될 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다. XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 & 없습니다. XMPP 기능을 계속 사용 하려면 레거시 버전 (비즈니스용 Skype Server 2015/Lync Server 2013)을 사용 하 여 availed 하는 환경에서이를 확인할 수 있습니다. XMPP 기능은 레거시 Edge 서버에서 실행 되는 XMPP 프록시로, 레거시 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 부분으로 설치 됩니다.
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238138"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="73ba2-106">XMPP 페더레이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="73ba2-106">Migrating XMPP federation</span></span>

<span data-ttu-id="73ba2-107">이전 버전에서는 XMPP 배포와의 페더레이션을 허용 하는 별도의 서버 역할로 배포 될 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="73ba2-108">XMPP 기능은 더 이상 사용할 수 없으며 비즈니스용 Skype 서버 2019에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="73ba2-109">XMPP 기능을 계속 사용 하려면 레거시 버전 (비즈니스용 Skype Server 2015 또는 Lync Server 2013)을 사용 하는 공존 환경에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="73ba2-110">XMPP 기능은 레거시 Edge 서버에서 실행 되는 XMPP 프록시로, 레거시 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 부분으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="73ba2-111">마이그레이션 측면에서 XMPP 기능을 사용 하려는 사용자는 레거시 서버에 남아 있어야 하 고 비즈니스용 Skype Server 2019 풀로 이동할 수 없으며 레거시 XMPP 게이트웨이를 계속 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="73ba2-112">이는 XMPP 페더레이션 파트너가 비즈니스용 Skype 서버 2015 또는 Lync Server 2013에서 구성 된 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="73ba2-113">XMPP 기능을 계속 사용 하려면 레거시 Edge 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="73ba2-114">그러나 XMPP 프록시를 사용 하는 레거시 Edge 서버와 비즈니스용 Skype 2019 Edge 서버를 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ba2-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

