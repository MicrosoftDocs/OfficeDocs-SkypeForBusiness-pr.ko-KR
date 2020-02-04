---
title: 통화 허용 제어 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC용 네트워크를 구성한 후 대역폭 제한을 적용하려면 CAC를 사용하도록 설정해야 합니다.
ms.openlocfilehash: 345668c61697dfa90e9e511d98ac82e6468440cc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684861"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="daf4a-104">통화 허용 제어 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="daf4a-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="daf4a-p102">CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC용 네트워크를 구성한 후 대역폭 제한을 적용하려면 CAC를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="daf4a-107">제어판이나 관리 셸 cmdlet을 사용하여 CAC를 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="daf4a-108">사이트의 **속성 편집** 대화 상자의 **통화 허용 제어 설정** 섹션에서 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="daf4a-109">**통화 허용 제어 사용** CAC를 사용 하도록 설정 하려면이 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="daf4a-110">전체 네트워크에 대해 CAC를 사용하지 않도록 설정하려면 이 설정을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="daf4a-111">CAC를 사용하도록 설정하려면 CAC용 네트워크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="daf4a-112">자세한 내용은 배포 설명서의 [비즈니스용 Skype 서버 2015에서 통화 허용 제어 배포](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="daf4a-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="daf4a-113">**호출 허용 제어를 실행 하는 프런트 엔드 풀** CAC를 사용 하도록 설정한 경우이를 실행 하는 풀을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="daf4a-114">드롭다운 목록에서 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="daf4a-114">Select the pool from the drop-down list.</span></span>
    

