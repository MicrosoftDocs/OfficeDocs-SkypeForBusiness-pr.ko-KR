---
title: 비즈니스용 Skype 서버 2015에서 토폴로지 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 초기 인터뷰 질문을 완료한 후 사이트의 FQDN(FQDN) 및 IP 주소를 편집할 수 있습니다. 이렇게 하려면 글로벌 토폴로지 페이지에서 편집할 사이트를 두 번 클릭합니다.
ms.openlocfilehash: ba18070b21494028d31b4167ab92a622794c5e51
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834888"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="b2721-104">비즈니스용 Skype 서버 2015에서 토폴로지 편집</span><span class="sxs-lookup"><span data-stu-id="b2721-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="b2721-105">초기 인터뷰 질문을 완료한 후 사이트의 FQDN(FQDN) 및 IP 주소를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="b2721-106">이렇게 하려면 **글로벌 토폴로지** 페이지에서 편집할 사이트를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="b2721-107">계획 도구에 선택한 사이트에 대한 사이트 토폴로지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="b2721-108">사이트 페이지 아래쪽에는 다음과 같은 네 개의 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-108">At the bottom of the site page are four tabs:</span></span>

![계획 도구 사이트 토폴로지](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="b2721-110">사이트 토폴로지 - 권장 토폴로지의 시각적 개요가 있는 현재 표시된 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="b2721-111">에지 네트워크 다이어그램 - 에지 네트워크 다이어그램 페이지는 디자이너가 계획 도구에서 대부분의 작업을 하는 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="b2721-112">이 다이어그램에는 권장 비즈니스용 Skype 서버 2015 토폴로지의 네트워크 구성이 표시되어 있으며, 서버, 풀 및 하드웨어 및 DNS(Domain Name System) 부하 런서에 대한 IP 주소 및 FQDNS에 대한 편집 가능한 항목이 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="b2721-113">에지 관리 보고서 - 에지 관리 보고서에는 총 4개의 보고서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![에지 관리 보고서 페이지](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="b2721-115">요약 보고서 - 에지 네트워크 구성에 대한 일반 설정 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="b2721-116">**에지** 네트워크 다이어그램 페이지의 값을 실제 배포에 사용할 토폴로지 TCP/IP 및 FQDN 값으로 편집하면 해당 주소와 이름이 여기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="b2721-117">그렇지 않으면 기본 텍스트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="b2721-118">인증서 보고서 - 인증서 보고서에는 토폴로지에 필요한 인증서의 주체 이름 및 주체 대체 이름이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="b2721-119">방화벽 보고서 - 방화벽 보고서에는 인프라에서 경계 방화벽을 구성하는 데 필요한 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="b2721-120">여기에는 IP 주소(기본값 또는 편집된 값), 서버 역할, 원본 IP 및 포트, 대상 IP 및 포트, 전송 프로토콜, 응용 프로그램 프로토콜 및 관련 메모가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="b2721-121">DNS 보고서 - DNS 보고서에는 만들어야 하는 DNS 항목에 대한 관련 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="b2721-122">보고서 유형, FQDN, IP 주소 및 적절한 작업을 위한 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="b2721-123">사이트 요약 - 사이트 요약에서는 초기 인터뷰 질문에 답변하거나 디자인 사이트의 값을 입력하여 선택한 내용에 대한 개요를 **제공합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2721-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="b2721-124">용량 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2721-125">사이트 요약 페이지의 정보는 각 디자인에 대해 사용자 지정되며, 여기서 설명하는 모든 섹션이나 정보를 포함하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="b2721-126">네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="b2721-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="b2721-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="b2721-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="b2721-128">디자이너가 비즈니스용 Skype 서버 2015 계획 도구에서 하는 대부분의 작업은 네트워크 다이어그램의 항목에 대한 IP 주소 및 FQDNS(정식 도메인 이름)에 대한 항목을 정의하는 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="b2721-129">이 페이지에 입력한 정보는 보고서 및 계획 도구에 포함된 기타 정보로 이어됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![계획 도구 네트워크 다이어그램](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="b2721-131">계획 도구는 IP 주소 및 FQDNS에 대한 기본 텍스트가 있는 네트워크 다이어그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="b2721-132">네트워크 다이어그램과 입력 값을 편집하려면</span><span class="sxs-lookup"><span data-stu-id="b2721-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="b2721-133">작업을 시작할 네트워크 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="b2721-134">예를 들어 텍스트를 두 번 클릭하고 **access1.contoso.com.**</span><span class="sxs-lookup"><span data-stu-id="b2721-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="b2721-135">대화 상자가 열리면 131.107.155.3을 대체하는 access1.contoso.com 서버의 실제 FQDN과 실제 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="b2721-136">**확인** 을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="b2721-137">하드웨어 부하 분산 장치의 가상 IP 주소를 제공하거나 풀의 서버에 대한 DNS(Domain Name System) 부하 분산용 서버 항목을 제공하여 IP 주소 및 FQDN을 계속 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="b2721-p111">계획 도구의 유용한 기능은 디자이너가 풀의 각 서버를 별도로 편집할 필요 없이 IP 주소 범위 및 서버 호스트 이름을 점진적으로 할당할 수 있다는 것입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="b2721-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="b2721-140">풀링된 프런트 엔드 서버를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="b2721-141">대화 상자가 열리면 **IP 및 FQDN을 이 클러스터에 있는 모든 동일한 서버의 시작 지점으로 사용하시겠습니까?** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="b2721-142">예를 들어 첫 번째 서버의 시작 값은 fe0101.contoso.com IP 주소는 192.168.21.122입니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="b2721-143">프런트 엔드 fe0.contoso.com **FQDN에** 입력하고 프런트 엔드 서버 **IP** 주소에 192.168.21.131을 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2721-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="b2721-144">자동 증가 기능은 풀의 모든 서버를 fe01~fe06로 업데이트하고 모든 IP 주소를 192.168.21.131에서 136으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="b2721-145">모든 편집을 완료한 후 다음 단계를 완료하여 토폴로지 저장</span><span class="sxs-lookup"><span data-stu-id="b2721-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="b2721-146">계획 도구 디자인을 저장하려면 **파일을** 클릭한  다음 토폴로지 저장 또는 토폴로지 다른 페이지로 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b2721-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="b2721-147">**다른 이름으로 계획 도구 저장** 대화 상자가 나타나면 **파일 이름** 에 파일 이름을 입력한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2721-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2721-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2721-148">See also</span></span>
<span data-ttu-id="b2721-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="b2721-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="b2721-150">디자인 편집</span><span class="sxs-lookup"><span data-stu-id="b2721-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
