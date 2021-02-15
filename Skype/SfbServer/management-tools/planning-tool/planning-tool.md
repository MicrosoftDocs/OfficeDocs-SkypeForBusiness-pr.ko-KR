---
title: 비즈니스용 Skype 서버 2015 계획 도구
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: 비즈니스용 Skype 서버 2015 계획 도구 사용에 대한 지침입니다.
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832388"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="d7bff-103">비즈니스용 Skype 서버 2015 계획 도구</span><span class="sxs-lookup"><span data-stu-id="d7bff-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="d7bff-104">비즈니스용 Skype 서버 2015 계획 도구 사용에 대한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="d7bff-105">비즈니스용 Skype 서버 2015 계획 도구는 디자인할 비즈니스용 Skype 서버 2015 토폴로지에 대한 질문을 하는 인터뷰와 같은 마법사 기반 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="d7bff-106">계획 도구는 제공된 정보를 토폴로지 디자인 및 용량에 대한 기본 설정 방법과 함께 사용하여 제공된 답변을 기반으로 권장 토폴로지가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="d7bff-107">비즈니스용 Skype 서버 [2015](https://go.microsoft.com/fwlink/p/?LinkID=282725)계획 도구에서 계획 도구를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="d7bff-108">궁극적으로 계획 도구의 목표는 완전한 비즈니스용 Skype 서버 2015 토폴로지 디자인의 잠재적 복잡성을 완화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="d7bff-109">또한 이 도구는 Microsoft 웹 사이트에 연결할 수 있는 인터넷 연결을 사용할 수 있는 경우 도구 내에서 계획 및 배포 설명서에 대한 상황적 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="d7bff-110">인프라의 TCP/IP 주소 및 FQDNS(정식 도메인 이름)로 토폴로지 사용자 지정 후 계획 도구는 DNS(Domain Name System) 명명, 방화벽 규칙, 인증서 등 다양한 보고서를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="d7bff-111">이 도구를 사용하는 것은 구현을 계획하는 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="d7bff-112">다음 단계에서는 비즈니스용 [Skype 서버 2015](https://www.microsoft.com/download/details.aspx?id=51196)용량 계산기로 사이트 정보를 입력하고, 필요한 경우 조정한 다음 비즈니스용 [Skype 서버 2015 스트레스](https://www.microsoft.com/download/details.aspx?id=50367) 및 성능 도구를 사용하여 구현이 요구 사항을 충족하는지 시뮬레이션하고 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="d7bff-113">계획 도구는 다음 두 가지 형식으로 정보를 내보내는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="d7bff-114">Microsoft Excel(.xml 스프레드시트)</span><span class="sxs-lookup"><span data-stu-id="d7bff-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="d7bff-115">Microsoft Visio(.vdx)</span><span class="sxs-lookup"><span data-stu-id="d7bff-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="d7bff-116">다음 항목에서는 계획 도구를 소개하고 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bff-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d7bff-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d7bff-117">In this section</span></span>

- [<span data-ttu-id="d7bff-118">비즈니스용 Skype 서버에서 계획 도구 설치</span><span class="sxs-lookup"><span data-stu-id="d7bff-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="d7bff-119">선택적 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="d7bff-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="d7bff-120">비즈니스용 Skype 서버 2015에서 계획 도구 탐색</span><span class="sxs-lookup"><span data-stu-id="d7bff-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="d7bff-121">비즈니스용 Skype 서버 2015의 초기 토폴로지 디자인 만들기</span><span class="sxs-lookup"><span data-stu-id="d7bff-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="d7bff-122">비즈니스용 Skype 서버 2015에서 토폴로지 편집</span><span class="sxs-lookup"><span data-stu-id="d7bff-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="d7bff-123">네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="d7bff-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="d7bff-124">비즈니스용 Skype 서버 2015에서 관리자 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="d7bff-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="d7bff-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7bff-125">See also</span></span>

[<span data-ttu-id="d7bff-126">비즈니스용 Skype 서버 2015 설치</span><span class="sxs-lookup"><span data-stu-id="d7bff-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="d7bff-127">비즈니스용 Skype 서버 2015의 인스턴트 메시징 및 현재 상태 계획</span><span class="sxs-lookup"><span data-stu-id="d7bff-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
