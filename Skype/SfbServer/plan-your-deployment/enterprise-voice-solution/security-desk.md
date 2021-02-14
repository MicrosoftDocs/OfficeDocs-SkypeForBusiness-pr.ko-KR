---
title: 비즈니스용 Skype 서버에 보안 데스크 포함
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 비즈니스용 Skype 서버의 E9-1-1 배포에 조직의 보안 데스크를 포함하는 방법을 Enterprise Voice.
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813408"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="77f8d-103">비즈니스용 Skype 서버에 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="77f8d-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="77f8d-104">비즈니스용 Skype 서버의 E9-1-1 배포에 조직의 보안 데스크를 포함하는 방법을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="77f8d-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="77f8d-p101">회사에서 긴급 통화를 처리하기 위한 보안 데스크가 필요한 경우가 있습니다. E9-1-1 배포에 보안 데스크를 통합하는 방법을 결정하려면 다음과 같은 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f8d-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="77f8d-107">**긴급 통화가 있는 경우 보안 데스크에 알림을 보낼지 여부**</span><span class="sxs-lookup"><span data-stu-id="77f8d-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="77f8d-108">비즈니스용 Skype 서버가 하나 이상의 보안 담당자의 비즈니스용 Skype SIP 주소에 IM(인스턴트 메시징) 알림을 보내도록 위치 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f8d-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="77f8d-109">이러한 경고는 긴급 통화를 거는 사용자의 이름, 번호 및 위치를 포함하며 보안 담당자가 긴급 상황을 지원하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f8d-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="77f8d-110">**각 긴급 통화에 대해 보안 데스크와 전화 회의를 할지 여부**</span><span class="sxs-lookup"><span data-stu-id="77f8d-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="77f8d-p103">긴급 서비스 공급자에서 지원되는 경우 각 긴급 통화에 콜백 번호를 포함하도록 위치 정책을 구성할 수 있습니다. 이 번호는 공급자가 조직의 보안 담당자를 긴급 통화에 참조로 포함하는 데 사용됩니다. 이러한 참조는 위치 정책에서 단방향(듣기만) 또는 양방향으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f8d-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="77f8d-p104">필요에 따라 각 위치 정책에 대해 서로 다른 긴급 담당자를 구성할 수 있습니다. 이렇게 하면 회사 내 여러 영역에 대한 응답성을 사용자 지정하거나, 내부의 긴급 통화와 네트워크 외부의 긴급 통화에 대해 서로 다른 동작을 만들 수 있습니다. 메일 그룹을 사용해서 알림을 제공할 담당자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f8d-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

