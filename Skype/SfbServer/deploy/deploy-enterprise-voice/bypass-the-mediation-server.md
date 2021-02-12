---
title: 항상 중재 서버를 무시하도록 비즈니스용 Skype 서버에서 미디어 우회 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 미디어 우회가 비즈니스용 Skype 서버 2016에서 중재 서버를 항상 우회하도록 Enterprise Voice.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804218"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1a35b-103">항상 중재 서버를 무시하도록 비즈니스용 Skype 서버에서 미디어 우회 구성</span><span class="sxs-lookup"><span data-stu-id="1a35b-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="1a35b-104">미디어 우회가 비즈니스용 Skype 서버 2016에서 중재 서버를 항상 우회하도록 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1a35b-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="1a35b-105">이 항목의 단계를 사용하여 미디어 우회에 대한 전역 설정을 구성하는 경우 비즈니스용 Skype 끝점과 트렁크 연결에 대해 미디어 우회를 구성한 피어 간의 연결이 양호한 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="1a35b-106">비즈니스용 Skype 끝점과 각 트렁크 연결이 미디어 우회를 사용하도록 설정된 중재 서버에 대한 모든 피어 간에 양호한 연결이 없는 경우 미디어 우회를 사용할 때 사이트 및 지역 정보를 사용하도록 전역 미디어 우회 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="1a35b-107">이렇게 하면 미디어가 중재 서버를 바이패스하는 경우를 보다 정밀하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="1a35b-108">이렇게하려면 비즈니스용 [Skype](use-site-and-region-information.md) 서버에서 미디어 우회 전역 설정 구성의 단계를 사용하여 [](deploy-network.md#BKMK_AssociateSubnets) 사이트 및 지역 정보를 사용하고 서브넷을 네트워크 사이트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1a35b-109">항상 중재 서버를 바이패스하도록 전역적으로 미디어 바이패스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1a35b-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="1a35b-110">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1a35b-111">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1a35b-112">목록에서 **전역** 구성을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="1a35b-113">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="1a35b-114">**항상 바이패스** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="1a35b-115">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a35b-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a35b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a35b-116">See also</span></span>

[<span data-ttu-id="1a35b-117">비즈니스용 Skype의 미디어 우회 계획</span><span class="sxs-lookup"><span data-stu-id="1a35b-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="1a35b-118">비즈니스용 Skype 서버에서 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="1a35b-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

