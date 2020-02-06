---
title: Lync Server 2010에 대한 Branch Office Appliance 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: Survivable Branch 기기 또는 Survivable Branch 서버의 속성을 편집 하려면 일반에서 다음을 구성 합니다.
ms.openlocfilehash: 5aa8a41cbe6c73cd103810c2661979cbba6bbdd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820310"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="eec78-103">Lync Server 2010에 대한 Branch Office Appliance 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="eec78-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="eec78-104">Survivable Branch 기기 또는 Survivable Branch 서버의 속성을 편집 하려면 **일반**에서 다음을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="eec78-105">**FQDN**: Survivable branch 기기 또는 Survivable branch 서버의 정규화 된 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="eec78-106">**구성 된 모든 IP 주소 사용** Survivable branch 기기 또는 Survivable branch 서버에서 구성 된 ip 주소를 모두 용도에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="eec78-107">**선택한 IP 주소로 서비스 사용 제한** PSTN에 사용할 IP 주소 및 서버를 정의하는 고유 주소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="eec78-108">**기본 IP 주소**: PSTN 연결 기능을 제외하고는 모든 용도로 정의 및 구성되는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="eec78-109">**PSTN IP 주소**: 공중 전화망(PSTN) 기능과 연결된 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="eec78-110">**연결** 을 구성 하 여 다른 서버 역할이 Survivable branch 기기 또는 Survivable branch 서버와 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="eec78-111">**보관 서버 연결** Survivable Branch 기기 또는 Survivable Branch 서버와 연결 하려는 보관 서버 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="eec78-112">이 Survivable Branch 기기 또는 Survivable Branch 서버와 연결 하려는 보관 서버를 만들지 않은 경우 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="eec78-113">**모니터링 서버 연결** Survivable Branch 기기 또는 Survivable Branch 서버와 연결 하려는 모니터링 서버 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="eec78-114">이 Survivable Branch 기기 또는 Survivable Branch 서버와 연결 하려는 모니터링 서버를 만들지 않은 경우 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="eec78-115">**Edge 풀 연결 (미디어 구성 요소의 경우)** 목록에서 Survivable Branch 기기 또는 Survivable Branch 서버와 연결 하려는 Edge 서버 또는 Edge 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="eec78-116">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="eec78-117">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="eec78-118">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eec78-118">**Help** Displays this help screen.</span></span>
  

