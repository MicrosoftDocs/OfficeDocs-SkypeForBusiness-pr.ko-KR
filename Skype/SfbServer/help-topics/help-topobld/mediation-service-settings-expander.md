---
title: 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 중재 서버에 대해 다음을 지정할 수 있습니다.
ms.openlocfilehash: a6e0321ddde79a088610e9e2b1c79739c68b2b90
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684511"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="bffb7-103">중재 서비스 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="bffb7-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="bffb7-104">**중재 서버**에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="bffb7-105">중재 서버를 프런트 엔드 풀 또는 Standard Edition 서버에 collocating 하는 경우에는 **Collocated 중재 서버를 사용할 수**있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="bffb7-106">중재 서버를 collocate 하지 않도록 선택 하는 경우이 섹션에는 정의 가능한 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="bffb7-107">중재 서버의 collocation을 사용 하도록 설정한 경우 TLS (전송 계층 보안)에 대 한 서버에서 수신 대기 포트 범위를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="bffb7-108">기본적으로 이 포트는 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-108">By default, this port is 5067.</span></span> <span data-ttu-id="bffb7-109">**TCP 포트 사용**을 선택하면 배치된 중재 서버의 TCP(Transmission Control Protocol) 포트를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="bffb7-110">이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 공중 전화망(PSTN) 요구 사항을 참조하여 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="bffb7-111">기본적으로 TCP 포트 값은 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="bffb7-112">Collocated 중재 서버와 연결 된 PSTN 게이트웨이를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="bffb7-113">이미 게이트웨이를 정의한 경우 중재 서버와 연결 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="bffb7-114">중재 서버와 연결 된 게이트웨이가 두 개 이상 있는 경우 연결 된 첫 번째 게이트웨이가 기본 게이트웨이가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="bffb7-115">기본 게이트웨이로 다른 게이트웨이를 선택해야 하는 경우 기본값으로 설정할 게이트웨이를 선택하고 **기본값으로 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="bffb7-116">기본값으로 설정한 게이트웨이의 선택을 취소하려면 **기본값으로 설정 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bffb7-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="bffb7-117">Enterprise Edition 프런트 엔드 풀 또는 Standard Edition server에 대 한 설정을 정의 하 고 구성 하는 방법에 대 한 자세한 내용은 [토폴로지 정의 및 구성](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) , [중재 서버 배포 및 피어 정의](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bffb7-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


