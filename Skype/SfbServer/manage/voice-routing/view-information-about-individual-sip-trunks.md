---
title: 비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks는 서로 동일 하지 않으며, 관리자는 CsTrunk cmdlet을 사용 하 여 개별 SIP 트렁크에 대 한 정보를 확인 해야 합니다.
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816927"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="aa2c6-103">비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="aa2c6-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="aa2c6-104">비즈니스용 Skype 서버에서 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks는 서로 동일 하지 않으며, 관리자가 [CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet을 사용 하 여 개별 SIP 트렁크에 대 한 정보를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c6-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="aa2c6-105">CsTrunk cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c6-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="aa2c6-106">**모든 SIP trunks에 대 한 정보를 보려면**</span><span class="sxs-lookup"><span data-stu-id="aa2c6-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="aa2c6-107">다음 명령은 조직에서 사용 중인 모든 SIP trunks에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c6-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="aa2c6-108">**특정 SIP 트렁크에 대 한 정보 보기**</span><span class="sxs-lookup"><span data-stu-id="aa2c6-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="aa2c6-109">이 명령은 Id PstnGateway: 192.168.0.240와 함께 SIP 트렁크에 대 한 정보만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c6-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="aa2c6-110">**풀에 할당 된 모든 SIP Trunks에 대 한 정보 보기**</span><span class="sxs-lookup"><span data-stu-id="aa2c6-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="aa2c6-111">이 예제에서는 풀 atl-cs-001.litwareinc.com에 할당 된 모든 SIP trunks에 대 한 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c6-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
