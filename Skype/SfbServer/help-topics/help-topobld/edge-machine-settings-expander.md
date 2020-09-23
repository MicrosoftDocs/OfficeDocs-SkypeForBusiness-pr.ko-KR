---
title: 에지 컴퓨터 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 에지 서버 풀에 있는 서버의 속성을 편집하려면 다음을 수행합니다.
ms.openlocfilehash: e62cfa000379ed7318c5780bf91ac40035e6beee
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218919"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="4b420-103">에지 컴퓨터 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="4b420-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="4b420-104">에지 서버 풀에 있는 서버의 속성을 편집하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="4b420-p101">**내부 이름 또는 FQDN**은 FQDN(정규화된 도메인 이름)을 편집하여 변경할 수 있습니다. FQDN은 내부 에지 네트워크 인터페이스에 대한 DNS(Domain Name System) 호스트(A) 레코드 및 서버에 할당된 인증서의 주체 이름과 일치해야 합니다. **내부 IP 주소** 값은 경계 네트워크 디자인을 기준으로 내부 네트워크로 정의된 네트워크 인터페이스에 할당되는 IP 주소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="4b420-p102">대화 상자의 다음 세 섹션에서는 이 에지 서버의 외부 구성에 대한 IP 주소를 정의합니다. IP 주소를 변경하는 기능은 에지 서버 풀 수준에서 속성 설정의 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 설정의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="4b420-110">SIP 액세스</span><span class="sxs-lookup"><span data-stu-id="4b420-110">SIP Access</span></span>

<span data-ttu-id="4b420-p103">SIP(Session Initiation Protocol) 액세스에 대한 네트워크 인터페이스에 할당된 외부 IP 주소를 편집합니다. 이 IP 주소는 공용 IP 주소이거나 개인 IP 주소 범위의 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b420-113">풀 설정 페이지에서 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 설정이 사용하도록 설정되면 SIP 액세스에 대한 IP 주소만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="4b420-114">웹 회의</span><span class="sxs-lookup"><span data-stu-id="4b420-114">Web Conferencing</span></span>

<span data-ttu-id="4b420-p104">웹 회의에 대한 네트워크 인터페이스에 할당된 외부 IP 주소를 편집합니다. 이 IP 주소는 공용 IP 주소이거나 개인 IP 주소 범위의 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="4b420-117">오디오/비디오</span><span class="sxs-lookup"><span data-stu-id="4b420-117">Audio/Video</span></span>

<span data-ttu-id="4b420-p105">A/V(오디오/비디오)에 대한 네트워크 인터페이스에 할당된 외부 IP 주소를 편집합니다. 이 IP 주소는 공용 IP 주소이거나 개인 IP 주소 범위의 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="4b420-p106">**NAT 사용 공용 IP 주소가 사용됨**에 대한 설정은 일반적으로 A/V 네트워크 인터페이스 또는 에지 서버에 대한 외부 인터페이스에 사용되는 공용 주소입니다. **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 설정을 사용하도록 설정하면 이 공용 IP 주소가 세 가지 외부 인터페이스 모두에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b420-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

