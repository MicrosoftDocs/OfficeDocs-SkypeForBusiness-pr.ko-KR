---
title: 비즈니스용 Skype 서버 2015에서 토폴로지 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 초기 인터뷰 질문을 완료 한 후에는 사이트의 FQDN (정규화 된 도메인 이름) 및 IP 주소를 편집할 수 있습니다. 이렇게 하려면 전역 토폴로지 페이지에서 편집 하려는 사이트를 두 번 클릭 합니다.
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816447"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="54b27-104">비즈니스용 Skype 서버 2015에서 토폴로지 편집</span><span class="sxs-lookup"><span data-stu-id="54b27-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="54b27-105">초기 인터뷰 질문을 완료 한 후에는 사이트의 FQDN (정규화 된 도메인 이름) 및 IP 주소를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="54b27-106">이렇게 하려면 **전역 토폴로지** 페이지에서 편집 하려는 사이트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="54b27-107">계획 도구에 선택한 사이트의 사이트 토폴로지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="54b27-108">사이트 페이지의 맨 아래에는 4 개의 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-108">At the bottom of the site page are four tabs:</span></span>

![계획 도구 사이트 토폴로지](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="54b27-110">사이트 토폴로지-권장 되는 토폴로지에 대 한 시각적 개요를 포함 하는 현재 표시 된 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="54b27-111">Edge 네트워크 다이어그램-Edge 네트워크 다이어그램 페이지는 디자이너가 계획 도구에서 대부분의 작업을 수행 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="54b27-112">다이어그램에는 권장 되는 비즈니스용 Skype 서버 2015 토폴로지에 대 한 네트워크 구성, 서버, 풀 및 하드웨어 및 DNS (Domain Name System) 부하 분산 장치에 대 한 IP 주소 및 Fqdn에 대 한 편집 가능한 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="54b27-113">Edge 관리 보고서-Edge 관리 보고서에는 총 4 개의 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![에지 관리 보고서 페이지](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="54b27-115">요약 보고서-Edge 네트워크 구성에 대 한 설정의 일반적인 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="54b27-116">**Edge 네트워크 다이어그램** 페이지의 값을 실제 배포에 사용 되는 토폴로지 TCP/IP 및 FQDN 값으로 편집 하면 해당 주소와 이름이 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="54b27-117">그렇지 않으면 기본 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="54b27-118">인증서 보고서-인증서 보고서에는 토폴로지에 필요한 인증서의 주체 이름 및 주체 대체 이름이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="54b27-119">방화벽 보고서-방화벽 보고서에는 인프라에서 경계 방화벽을 구성 하는 데 필요한 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="54b27-120">여기에는 IP 주소 (기본값 또는 편집 된 값), 서버 역할, 원본 IP 및 포트, 대상 IP 및 포트, 전송 프로토콜, 응용 프로그램 프로토콜, 관련 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="54b27-121">DNS 보고서-DNS 보고서에는 사용자가 만들어야 하는 DNS 항목에 대 한 관련 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="54b27-122">적절 한 작동에 필요한 레코드 종류, FQDN, IP 주소, 메모 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="54b27-123">사이트 요약-사이트 요약에는 초기 인터뷰 질문에 응답 하거나 **디자인 사이트**의 값을 입력 하 여 선택한 내용이 간략하게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="54b27-124">또한 용량 정보도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54b27-125">사이트 요약 페이지의 정보는 각 디자인에 대해 사용자 지정 되며 여기에서 자세히 설명 하는 일부 섹션 또는 정보는 포함 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="54b27-126">네트워크 구성 다이어그램 편집</span><span class="sxs-lookup"><span data-stu-id="54b27-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="54b27-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="54b27-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="54b27-128">비즈니스용 Skype Server 2015 계획 도구에서 디자이너가 수행 하는 대부분의 작업은 네트워크 다이어그램의 엔트리에 대 한 IP 주소 및 Fqdn (정규화 된 도메인 이름)의 항목을 정의 하는 것으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="54b27-129">이 페이지에 입력 되는 정보는 계획 도구에 포함 된 보고서 및 기타 정보로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![계획 도구 네트워크 다이어그램](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="54b27-131">계획 도구는 IP 주소와 Fqdn에 대 한 기본 텍스트가 포함 된 네트워크 다이어그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="54b27-132">네트워크 다이어그램 및 입력 값을 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="54b27-133">작업을 시작할 네트워크의 섹션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="54b27-134">예를 들어, **access1.contoso.com**텍스트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="54b27-135">열리는 대화 상자에서 서버 access1.contoso.com의 실제 FQDN과 실제 IP 주소를 입력 하 고 131.107.155.3를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="54b27-136">**확인** 을 클릭 하 여 항목을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="54b27-137">IP 주소 및 Fqdn을 계속 편집 하 여 하드웨어 부하 분산 장치에 대 한 가상 IP 주소를 제공 하거나 풀에 있는 서버의 DNS (Domain Name System) 부하 분산에 대 한 서버 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="54b27-138">계획 도구의 유용한 기능은 디자이너에서 풀의 개별 서버를 편집 하는 대신 IP 주소와 서버 호스트 이름 범위를 점차적으로 할당할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-138">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool.</span></span> <span data-ttu-id="54b27-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-139">For example:</span></span>

1. <span data-ttu-id="54b27-140">풀링된 프런트 엔드 서버를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="54b27-141">대화 상자가 열리면 **이 클러스터의 모든 해당 서버에 대해 ip 및 FQDN을 시작 점으로 사용**하 시겠습니까?를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="54b27-142">예를 들어 첫 번째 서버의 시작 값은 fe0101.contoso.com이 고 192.168.21.122의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="54b27-143">**프런트 엔드 서버 FQDN**에 fe0.contoso.com를 입력 하 고 **프런트 엔드 서버 IP 주소**에 192.168.21.131를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="54b27-144">자동 증가 기능은 풀의 모든 서버를 fe01로 업데이트 하 고 192.168.21.131에서 136 까지의 모든 IP 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="54b27-145">모든 편집을 완료 한 후 다음 단계를 완료 하 여 토폴로지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="54b27-146">계획 도구 디자인을 저장 하려면 **파일**을 클릭 한 다음 **토폴로지 저장** 또는 **다른 이름으로 토폴로지 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="54b27-147">**계획 도구 저장** 대화 상자가 표시 되는 경우 파일 **이름**에 파일 이름을 입력 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b27-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="54b27-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54b27-148">See also</span></span>
<span data-ttu-id="54b27-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="54b27-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="54b27-150">디자인 편집</span><span class="sxs-lookup"><span data-stu-id="54b27-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
