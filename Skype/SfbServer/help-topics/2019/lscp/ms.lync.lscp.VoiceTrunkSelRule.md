---
title: 변환 규칙 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)를 사용하려면 번호가 로컬 전화 번호 형식이어야 합니다. 번호를 E.164 형식에서 로컬 전화 번호 형식으로 변환하려면 선택적으로 하나 이상의 변환 규칙을 정의하여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다. 예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.
ms.openlocfilehash: c16c5676eec0659d4cfe47bb878ca4955576a3fc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798115"
---
# <a name="select-translation-rules"></a><span data-ttu-id="b7b26-106">변환 규칙 선택</span><span class="sxs-lookup"><span data-stu-id="b7b26-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="b7b26-107">Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b26-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="b7b26-108">트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)를 사용하려면 번호가 로컬 전화 번호 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b26-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="b7b26-109">번호를 E.164 형식에서 로컬 전화 번호 형식으로 변환하려면 선택적으로 하나 이상의 변환 규칙을 정의하여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b26-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="b7b26-110">예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b26-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b7b26-111">하나 이상의 번역 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 기능은 트렁크 피어에서 번역 규칙을 구성 하는 대신 사용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b26-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="b7b26-112">두 규칙이 충돌할 수 있기 때문에 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b7b26-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="b7b26-113">기존 변환 규칙을 사용하려면 목록에서 규칙을 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b26-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

