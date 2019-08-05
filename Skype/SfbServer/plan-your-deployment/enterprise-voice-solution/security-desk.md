---
title: 비즈니스용 Skype 서버에 보안 데스크 포함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 비즈니스용 Skype Server Enterprise Voice의 E9-1 배포에 조직의 보안 데스크를 포함 하는 방법을 계획 합니다.
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187563"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="d5b11-103">비즈니스용 Skype 서버에 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="d5b11-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="d5b11-104">비즈니스용 Skype Server Enterprise Voice의 E9-1 배포에 조직의 보안 데스크를 포함 하는 방법을 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d5b11-105">회사에서 긴급 통화에 참여 하려면 보안 지원팀이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-105">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="d5b11-106">E9에서 보안 데스크를 통합 하는 방법을 결정 하려면-1-1 배포를 선택 하는 방법에 대 한 자세한 내용은 다음 질문에 대답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-106">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="d5b11-107">**긴급 통화 시 보안 지원팀에 알림을 받도록 하 고 싶으신가요?**</span><span class="sxs-lookup"><span data-stu-id="d5b11-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="d5b11-108">비즈니스용 Skype 서버에서 하나 이상의 보안 사용자의 비즈니스용 Skype SIP 주소로 IM (인스턴트 메시징) 알림을 보내도록 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="d5b11-109">이러한 경고에는 비상 전화를 걸고 있는 사람의 이름, 번호, 위치가 포함 되며, 긴급 상황에 대 한 지원으로 보안 인력이 이용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="d5b11-110">**각 비상 전화를 통해 보안 지원팀에 회의를 하 고 싶으신가요?**</span><span class="sxs-lookup"><span data-stu-id="d5b11-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="d5b11-111">비상 서비스 서비스 제공 업체에서 지원 되는 경우, 각 비상 전화에 콜백 번호를 포함 하도록 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-111">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="d5b11-112">공급자는이 번호를 사용 하 여 조직의 보안 담당자에 게 긴급 통화로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-112">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="d5b11-113">이 회의는 위치 정책에서 단방향 (수신 전용) 또는 양방향 (양방향)으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-113">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5b11-114">원하는 경우 각 위치 정책에 대해 서로 다른 응급 인력을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-114">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="d5b11-115">이렇게 하면 회사 내의 다른 영역에 대 한 응답을 사용자 지정 하거나 네트워크 외부가 아닌 내부에서 시작 된 비상 전화에 대해 다른 동작을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-115">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="d5b11-116">메일 그룹을 사용 하 여 알림을 받을 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b11-116">You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

