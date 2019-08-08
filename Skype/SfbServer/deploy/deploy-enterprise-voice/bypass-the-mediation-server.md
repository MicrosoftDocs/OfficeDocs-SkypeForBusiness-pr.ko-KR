---
title: 비즈니스용 Skype 서버에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 비즈니스용 Skype Server Enterprise Voice에서 항상 중재 서버를 우회 하도록 미디어 바이패스를 사용 하도록 설정 합니다.
ms.openlocfilehash: dfffda1130fc1fb119e6cbf5d9b12af766b9c038
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234036"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="94031-103">비즈니스용 Skype 서버에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="94031-104">비즈니스용 Skype Server Enterprise Voice에서 항상 중재 서버를 우회 하도록 미디어 바이패스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="94031-105">이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우 비즈니스용 Skype 끝점 및 트렁크 연결에서 미디어 바이패스를 구성한 피어 간에 연결이 양호한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="94031-106">비즈니스용 Skype 끝점 및 모든 피어가 미디어 바이패스에 대해 사용 하도록 설정 되어 있는 중재 서버와의 연결이 적절 하지 않은 경우에는 사이트 및 지역 정보를 사용 하도록 전역 미디어 우회 설정을 구성 해야 합니다. 미디어 바이패스를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="94031-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="94031-107">이를 통해 미디어가 중재 서버를 우회 하는 시기를 결정 하는 데 더 많은 제어가 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="94031-108">이렇게 하려면 [비즈니스용 Skype 서버에서 미디어 구성 건너뛰기 전역 설정 단계를 사용 하 여 사이트 및 지역 정보를 사용 하](use-site-and-region-information.md) 고 [서브넷을 네트워크 사이트와 연결](deploy-network.md#BKMK_AssociateSubnets) 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="94031-109">항상 중재 서버를 우회 하기 위해 미디어 우회를 전역적으로 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="94031-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="94031-110">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="94031-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="94031-111">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="94031-112">목록에서 **전역** 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="94031-113">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="94031-114">**항상 무시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="94031-115">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="94031-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94031-116">See also</span></span>

[<span data-ttu-id="94031-117">비즈니스용 Skype에서 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="94031-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="94031-118">비즈니스용 Skype 서버에서 미디어 바이패스 배포</span><span class="sxs-lookup"><span data-stu-id="94031-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

