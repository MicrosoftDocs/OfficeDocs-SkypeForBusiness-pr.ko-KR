---
title: 비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서는 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크가 동일하지는 않습니다. 관리자는 Get-CsTrunk cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 보아야 합니다.
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103004"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="c62b5-103">비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c62b5-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="c62b5-104">비즈니스용 Skype 서버에서는 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크는 하나만 같지 않을 뿐만 아니라 [관리자가 Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62b5-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="c62b5-105">이 Get-CsTrunk 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c62b5-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="c62b5-106">**모든 SIP 트렁크에 대한 정보를 확인**</span><span class="sxs-lookup"><span data-stu-id="c62b5-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="c62b5-107">다음 명령은 조직에서 사용 중이면 모든 SIP 트렁크에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c62b5-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="c62b5-108">**특정 SIP 트렁크에 대한 정보를 보기 위해**</span><span class="sxs-lookup"><span data-stu-id="c62b5-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="c62b5-109">이 명령은 ID가 PstnGateway:192.168.0.240인 SIP 트렁크에 대한 정보만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c62b5-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="c62b5-110">**풀에 할당된 모든 SIP 트렁크에 대한 정보 보기**</span><span class="sxs-lookup"><span data-stu-id="c62b5-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="c62b5-111">이 예에서는 풀에 할당된 모든 SIP 트렁크에 대한 정보를 atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c62b5-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`