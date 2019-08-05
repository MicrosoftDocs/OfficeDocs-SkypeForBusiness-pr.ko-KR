---
title: 비즈니스용 Skype에서 IP 주소 유형 구성
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
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '요약: 비즈니스용 Skype 서버를 구현 하기 전에 아래의 IP 주소 유형 고려 사항을 검토 합니다.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196859"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="96c5e-103">비즈니스용 Skype에서 IP 주소 유형 구성</span><span class="sxs-lookup"><span data-stu-id="96c5e-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="96c5e-104">**요약:** 비즈니스용 Skype 서버를 구현 하기 전에 아래의 IP 주소 유형 고려 사항을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="96c5e-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="96c5e-105">토폴로지 작성기에서 구성한 토폴로지 설정을 사용 하 여 IP 주소 형식을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="96c5e-106">이 섹션에서는 프런트 엔드 서버, 중재 서버 및 Edge 서버에서 IP 주소 유형을 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="96c5e-107">프런트 엔드 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="96c5e-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="96c5e-108">토폴로지 작성기를 사용 하 여 프런트 엔드 서버에 IP 주소 유형을 배포 하려면 다음 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="96c5e-109">프런트 엔드 서버에 IP 주소 유형을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="96c5e-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="96c5e-110">**Enterprise Edition 프런트 엔드 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-110">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="96c5e-111">또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-111">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="96c5e-112">**속성 편집** 대화 상자에서 구성 하려는 IP 주소 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="96c5e-113">이중 스택 구성의 경우 **IPv4 사용** 및 **IPv6 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="96c5e-114">**프런트 엔드 서버 풀의 속성 편집 대화 상자**</span><span class="sxs-lookup"><span data-stu-id="96c5e-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="96c5e-115">**구성 된 모든 IP 주소를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-115">**Use all configured IP addresses**.</span></span> <span data-ttu-id="96c5e-116">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있도록 허용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-116">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="96c5e-117">이 옵션은 IP 버전 6 (IPv6) 구성에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="96c5e-118">**선택한 IP 주소로 서비스 사용량을 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-118">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="96c5e-119">새 서버에서 사용할 특정 주소를 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-119">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="96c5e-120">이 옵션을 선택 하는 경우 **기본 IP 주소**에 대 한 값을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-120">If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="96c5e-121">**주 IP 주소**</span><span class="sxs-lookup"><span data-stu-id="96c5e-121">**Primary IP address**.</span></span> <span data-ttu-id="96c5e-122">서버가 PSTN (공공 교환 전화 네트워크)을 제외한 모든 통신에 사용할 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-122">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="96c5e-123">입력 하는 IP 주소는 선택 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-123">The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="96c5e-124">**PSTN IP 주소**.</span><span class="sxs-lookup"><span data-stu-id="96c5e-124">**PSTN IP address**.</span></span> <span data-ttu-id="96c5e-125">중재 서버가 프런트 엔드 서버에서 collocated 경우 PSTN IP 주소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-125">Define a PSTN IP address when a Mediation Server is collocated on the Front End Server.</span></span> <span data-ttu-id="96c5e-126">이 주소는 선택한 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-126">This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="96c5e-127">프런트 엔드 서버의 PSTN IP 주소 구성 (또는 기타 이유)을 지원 하기 위해 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="96c5e-128">비즈니스용 Skype 서버용으로 지원 되는 NIC 구성에 대 한 자세한 내용은 [Lync server 2013의 서버 하드웨어 플랫폼](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96c5e-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="96c5e-129">중재 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="96c5e-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="96c5e-130">토폴로지 작성기를 사용 하 여 다음 절차의 단계를 수행 하 여 중재 서버에 IP 주소 유형을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="96c5e-131">중재 서버에서 IP 주소 유형을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="96c5e-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="96c5e-132">토폴로지 작성기의 **중재 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="96c5e-133">또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="96c5e-134">**속성 편집** 대화 상자에서 구성 하려는 IP 주소 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-134">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="96c5e-135">이중 스택 구성은 **IPv4 사용** 을 선택 하 고 다음 그림과 같이 **IPv6을 사용 하도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-135">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="96c5e-136">**중재 서버 풀에 대 한 속성 편집 대화 상자**</span><span class="sxs-lookup"><span data-stu-id="96c5e-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="96c5e-137">**구성 된 모든 IP 주소를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-137">**Use all configured IP addresses**.</span></span> <span data-ttu-id="96c5e-138">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있도록 허용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-138">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96c5e-139">이 옵션은 IP 버전 6 (IPv6) 구성에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="96c5e-140">**선택한 IP 주소로 서비스 사용량을 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-140">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="96c5e-141">새 서버에서 사용할 특정 주소를 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-141">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="96c5e-142">이 옵션을 선택 하는 경우 기본 IP 주소에 대 한 값을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-142">If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="96c5e-143">**주 IP 주소**</span><span class="sxs-lookup"><span data-stu-id="96c5e-143">**Primary IP address**.</span></span> <span data-ttu-id="96c5e-144">서버가 PSTN (공공 교환 전화 네트워크)을 제외한 모든 통신에 사용할 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-144">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="96c5e-145">입력 하는 IP 주소는 선택 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-145">The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="96c5e-146">**PSTN IP 주소**.</span><span class="sxs-lookup"><span data-stu-id="96c5e-146">**PSTN IP address**.</span></span> <span data-ttu-id="96c5e-147">중재 서버가 프런트 엔드 서버에서 collocated 경우 PSTN IP 주소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-147">Define a PSTN IP address when a Mediation Server is collocated on the Front End Server.</span></span> <span data-ttu-id="96c5e-148">이 주소는 선택한 주소 유형의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-148">This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="96c5e-149">*전용* 중재 서버에서는 2 개의 네트워크 카드만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="96c5e-150">Sserver 역할이 프런트 엔드에서 collocated 되는 경우 이중 네트워크 카드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="96c5e-151">비즈니스용 Skype Server 2015의 지원 되는 NIC 구성에 대 한 자세한 내용은 비즈니스용 [Skype server 2015의 하드웨어](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96c5e-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="96c5e-152">비즈니스용 Skype Server 2019의 지원 되는 NIC 구성에 대 한 자세한 내용은 비즈니스용 [Skype server 2019의 하드웨어](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96c5e-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="96c5e-153">에지 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="96c5e-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="96c5e-154">토폴로지 작성기를 사용 하 여 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="96c5e-155">Edge 서버에 IP 주소 유형을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="96c5e-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="96c5e-156">토폴로지 작성기의 **Edge 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="96c5e-157">또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="96c5e-158">**속성 편집** 창에서 지원 하려는 IP 주소 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="96c5e-159">선택한 각 주소 유형에 대해 적절 한 내부 및 외부 주소를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c5e-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
