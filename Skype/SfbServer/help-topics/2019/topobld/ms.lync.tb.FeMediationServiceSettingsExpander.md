---
title: 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 중재 서버의 경우 다음을 지정할 수 있습니다.
ms.openlocfilehash: e3593fd98c9207b6dd7033e5aac26170988ae956
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096904"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="e1bef-103">중재 서비스 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="e1bef-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="e1bef-104">**중재 서버** 에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bef-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="e1bef-105">중재 서버를 프런트 엔드 풀 또는 Standard Edition 서버에 함께 사용하는 경우 중재 서버 함께 사용 확인란을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1bef-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="e1bef-106">중재 서버를 배치하지 않도록 선택하면 이 섹션에서 정의할 수 있는 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bef-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="e1bef-p102">중재 서버 배치를 사용하도록 설정하면 TLS(전송 계층 보안)를 사용하도록 서버의 수신 대기 포트 범위를 정의해야 합니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용** 을 선택하면 배치된 중재 서버의 TCP(Transmission Control Protocol) 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 공중 전화망(PSTN) 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="e1bef-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="e1bef-p103">배치된 중재 서버와 연결된 PSTN 게이트웨이를 정의합니다. 이미 게이트웨이를 정의한 경우 해당 게이트웨이를 중재 서버와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bef-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="e1bef-p104">중재 서버와 연결된 게이트웨이가 둘 이상인 경우 연결된 첫 번째 게이트웨이가 기본 게이트웨이가 됩니다. 기본 게이트웨이로 다른 게이트웨이를 선택해야 하는 경우 기본값으로 설정할 게이트웨이를 선택하고 **기본값으로 설정** 을 클릭합니다. 기본값으로 설정한 게이트웨이의 선택을 취소하려면 **기본값으로 설정 안 함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1bef-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="e1bef-117">Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버의 설정을 정의 및 구성하는 데 대한 자세한 내용은 [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) 및 [Deploying Mediation Servers and Defining Peers를 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)</span><span class="sxs-lookup"><span data-stu-id="e1bef-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span></span>