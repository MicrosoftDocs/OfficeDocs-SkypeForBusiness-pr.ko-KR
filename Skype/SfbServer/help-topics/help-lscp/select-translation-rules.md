---
title: 변환 규칙 선택
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)에서는 번호가 로컬 전화 걸기 형식이어야 할 수 있습니다. 번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 요청 URI를 처리하기 위한 변환 규칙을 하나 이상 선택적으로 정의할 수 있습니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.
ms.openlocfilehash: 3f448a9ac97c2bc7b57a8a87a6544ad84472e65e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803698"
---
# <a name="select-translation-rules"></a><span data-ttu-id="c8fd3-106">변환 규칙 선택</span><span class="sxs-lookup"><span data-stu-id="c8fd3-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="c8fd3-107">Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c8fd3-108">트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)에서는 번호가 로컬 전화 걸기 형식이어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="c8fd3-109">번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 요청 URI를 처리하기 위한 변환 규칙을 하나 이상 선택적으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="c8fd3-110">예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c8fd3-111">하나 이상의 변환 규칙을 트렁크 구성과 Enterprise Voice 트렁크 피어에 대한 변환 규칙을 구성하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="c8fd3-112">트렁크 피어에 변환 규칙을 구성한 경우 두 규칙이 충돌할 수 Enterprise Voice 변환 규칙을 트렁크 구성과 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="c8fd3-113">기존 변환 규칙을 사용하려면 목록에서 규칙을 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd3-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="c8fd3-114">비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015를 참조하세요.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="c8fd3-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

