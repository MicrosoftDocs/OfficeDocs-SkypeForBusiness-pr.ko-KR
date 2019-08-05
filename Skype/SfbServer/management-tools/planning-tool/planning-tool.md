---
title: 계획 도구를 사용하여 Lync Server 2013의 토폴로지 디자인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: 비즈니스용 Skype 서버 2015 계획 도구를 사용 하는 방법에 대 한 지침입니다.
ms.openlocfilehash: b130ca05200ea30bed8008399050affa96438644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191235"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="32039-103">계획 도구를 사용하여 Lync Server 2013의 토폴로지 디자인</span><span class="sxs-lookup"><span data-stu-id="32039-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="32039-104">비즈니스용 Skype 서버 2015 계획 도구를 사용 하는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="32039-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="32039-105">비즈니스용 Skype Server 2015 계획 도구는 디자인 중인 비즈니스용 Skype 서버 2015 토폴로지에 대해 질문을 하는 마법사 기반 인터뷰 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="32039-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="32039-106">계획 도구는 제공 되는 정보를 사용 하 여 토폴로지 디자인 및 용량에 대 한 기본 방법과 결합 하 여 제공 된 답변에 따라 추천 토폴로지를 제시 합니다.</span><span class="sxs-lookup"><span data-stu-id="32039-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="32039-107">[비즈니스용 Skype 서버 2015 계획 도구](https://go.microsoft.com/fwlink/p/?LinkID=282725)에서 계획 도구를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32039-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="32039-108">계획 도구의 목표는 궁극적으로 비즈니스용 Skype Server 2015 토폴로지를 디자인 하는 것의 가능성을 줄이기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32039-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="32039-109">또한이 도구는 Microsoft 웹 사이트에 연결 하는 데 인터넷 연결을 사용할 수 있는 경우 도구 내부의 계획 및 배포 설명서에 대 한 상황별 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32039-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="32039-110">인프라의 TCP/IP 주소와 Fqdn (정규화 된 도메인 이름)을 사용 하 여 토폴로지를 사용자 지정한 후에는 계획 도구에서 DNS (Domain Name System) 명명, 방화벽 규칙, 인증서 등을 다루는 일련의 보고서를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32039-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="32039-111">이 도구를 사용 하는 것이 구현 계획의 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="32039-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="32039-112">다음 단계에서는 비즈니스용 [Skype server 2015 용량 계산기](https://www.microsoft.com/en-us/download/details.aspx?id=51196)에 사이트 정보를 입력 하 고 필요에 따라 조정한 다음 [비즈니스용 Skype server 2015 스트레스 및 성능 도구](https://www.microsoft.com/en-us/download/details.aspx?id=50367) 를 사용 하 여 다음을 시뮬레이션 하 고 확인 합니다. 구현은 사용자의 요구를 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="32039-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="32039-113">계획 도구는 다음 두 가지 형식의 정보를 내보내는 기능도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32039-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="32039-114">Microsoft Excel (xml 스프레드시트)</span><span class="sxs-lookup"><span data-stu-id="32039-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="32039-115">Microsoft Visio (vdx)</span><span class="sxs-lookup"><span data-stu-id="32039-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="32039-116">다음 항목에서는 계획 도구를 소개 하 고 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="32039-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="32039-117">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="32039-117">In this section</span></span>

- [<span data-ttu-id="32039-118">Lync Server 2013에서 선택적 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="32039-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="32039-119">선택적 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="32039-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="32039-120">Lync Server 2013에서 계획 도구 탐색</span><span class="sxs-lookup"><span data-stu-id="32039-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="32039-121">Lync Server 2013에 대한 초기 토폴로지 디자인 만들기</span><span class="sxs-lookup"><span data-stu-id="32039-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="32039-122">비즈니스용 Skype 서버 2015에서 토폴로지 편집</span><span class="sxs-lookup"><span data-stu-id="32039-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="32039-123">네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="32039-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="32039-124">비즈니스용 Skype Server 2015의 관리자 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="32039-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="32039-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32039-125">See also</span></span>

[<span data-ttu-id="32039-126">비즈니스용 Skype 서버 2015 설치</span><span class="sxs-lookup"><span data-stu-id="32039-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="32039-127">비즈니스용 Skype 서버 2015의 메신저 대화 및 현재 상태 계획</span><span class="sxs-lookup"><span data-stu-id="32039-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
