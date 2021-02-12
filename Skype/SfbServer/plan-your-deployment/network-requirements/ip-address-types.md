---
title: 비즈니스용 Skype에서 IP 주소 유형 구성
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
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '요약: 비즈니스용 Skype 서버를 구현하기 전에 아래 IP 주소 유형 고려 사항을 검토합니다.'
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825264"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="56352-103">비즈니스용 Skype에서 IP 주소 유형 구성</span><span class="sxs-lookup"><span data-stu-id="56352-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="56352-104">**요약:** 비즈니스용 Skype 서버를 구현하기 전에 아래 IP 주소 유형 고려 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="56352-105">토폴로지 작성기에서 구성한 토폴로지 설정을 사용하여 IP 주소 유형을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="56352-106">이 섹션에서는 프런트 엔드 서버, 중재 서버 및 에지 서버에 IP 주소 유형을 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="56352-107">프런트 엔드 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="56352-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="56352-108">토폴로지 작성기에서 다음 절차의 단계를 수행하여 프런트 엔드 서버에 IP 주소 유형을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="56352-109">프런트 엔드 서버에 IP 주소 유형을 배포하려면</span><span class="sxs-lookup"><span data-stu-id="56352-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="56352-p102">**Enterprise Edition 프런트 엔드 풀** 아래에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집** 을 선택합니다. 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="56352-112">**속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="56352-113">이중 스택 구성의 경우 **IPv4** 사용 및 **IPv6 사용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="56352-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="56352-114">**프런트 엔드 서버 풀에 대한 속성 편집 대화 상자**</span><span class="sxs-lookup"><span data-stu-id="56352-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="56352-p104">**구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="56352-117">이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="56352-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="56352-p105">**선택한 IP 주소로 서비스 사용 제한**. 새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 **기본 IP 주소** 의 값을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="56352-p106">**기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="56352-p107">**PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에 배치되는 경우 PSTN IP 주소를 정의합니다. 이 주소는 선택한 주소 유형의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="56352-127">프런트 엔드 서버에서 PSTN IP 주소 구성을 지원하기 위한 추가 NI(네트워크 인터페이스 카드) 설치는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56352-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="56352-128">비즈니스용 Skype 서버의 지원되는 NIC 구성에 대한 자세한 내용은 [Lync Server 2013용](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)서버 하드웨어 플랫폼을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56352-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="56352-129">중재 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="56352-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="56352-130">토폴로지 작성기에서 다음 절차의 단계를 수행하여 중재 서버에 IP 주소 유형을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="56352-131">중재 서버에 IP 주소 유형을 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="56352-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="56352-132">토폴로지 작성기의 **중재** 풀에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="56352-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="56352-133">또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="56352-p110">**속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다. 이중 스택 구성의 경우 다음 그림과 같이 **IPv4 사용** 과 **IPv6 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="56352-136">**중재 서버 풀의 속성 편집 대화 상자**</span><span class="sxs-lookup"><span data-stu-id="56352-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="56352-p111">**구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56352-139">이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="56352-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="56352-140">**선택한 IP 주소로 서비스 사용 제한**.</span><span class="sxs-lookup"><span data-stu-id="56352-140">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="56352-141">새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-141">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="56352-142">이 옵션을 선택하는 경우 기본 IP 주소의 값을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-142">If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="56352-p113">**기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="56352-p114">**PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에 배치되는 경우 PSTN IP 주소를 정의합니다. 이 주소는 선택한 주소 유형의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="56352-149">전용 중재 서버에서는  두 개의 네트워크 카드만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="56352-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="56352-150">중재 Sserver 역할이 프런트 엔드에 함께 있는 경우 이중 네트워크 카드가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56352-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="56352-151">비즈니스용 Skype 서버 2015의 지원되는 NIC 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015) 하드웨어를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56352-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="56352-152">비즈니스용 Skype 서버 2019의 지원되는 NIC 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019) 하드웨어를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56352-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="56352-153">에지 서버에 IP 주소 유형 배포</span><span class="sxs-lookup"><span data-stu-id="56352-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="56352-154">토폴로지 작성기에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="56352-155">에지 서버에 IP 주소 유형을 배포하는 경우</span><span class="sxs-lookup"><span data-stu-id="56352-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="56352-156">토폴로지 작성기에서 에지 풀 아래에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="56352-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="56352-157">또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="56352-158">속성 **편집** 창에서 지원할 IP 주소 구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="56352-159">선택한 각 주소 유형에 대해 적절한 내부 및 외부 주소를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56352-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
