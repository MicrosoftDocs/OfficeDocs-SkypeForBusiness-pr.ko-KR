---
title: Edge 기계 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: Edge 서버 풀의 서버에 대 한 속성을 편집 하려면 다음을 수행 합니다.
ms.openlocfilehash: 75be5becb255365922b25a16f8a6004d4b7030c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197293"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="58564-103">Edge 기계 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="58564-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="58564-104">Edge 서버 풀의 서버에 대 한 속성을 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="58564-105">정규화 된 도메인 이름 (FQDN)을 편집 하 여 **내부 이름 또는 fqdn** 을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58564-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="58564-106">FQDN은 DNS (Domain Name System) 호스트 (A) 레코드와 내부에 지 네트워크 인터페이스에 대해 서버에 할당 된 인증서의 주체 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="58564-107">**내부 IP 주소의** 값은 경계 네트워크 디자인을 기준으로 내부 네트워크로 정의 되는 네트워크 인터페이스에 할당 된 IP 주소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="58564-108">다음 세 개의 대화 상자 섹션에서는이 Edge 서버의 외부 구성에 대 한 IP 주소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="58564-109">IP 주소를 변경 하는 기능은 **웹 회의에 별도의 FQDN과 IP 주소를 사용 하도록** 설정 하 고 Edge 서버 풀 수준의 속성 설정에서 A/V에 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="58564-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="58564-110">SIP 액세스</span><span class="sxs-lookup"><span data-stu-id="58564-110">SIP Access</span></span>

<span data-ttu-id="58564-111">SIP (세션 시작 프로토콜) 액세스를 위해 네트워크 인터페이스에 할당 된 외부 IP 주소를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="58564-112">이 IP 주소는 공용 IP 주소 이거나 개인 IP 주소 범위의 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58564-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58564-113">그룹 설정 페이지에 대 한 **별도의 FQDN과 IP 주소를 사용 하도록 설정 하** 는 경우 SIP 액세스에 대 한 ip 주소만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58564-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="58564-114">웹 회의</span><span class="sxs-lookup"><span data-stu-id="58564-114">Web Conferencing</span></span>

<span data-ttu-id="58564-115">웹 회의를 위해 네트워크 인터페이스에 할당 된 외부 IP 주소를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="58564-116">이 IP 주소는 공용 IP 주소 이거나 개인 IP 주소 범위의 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58564-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="58564-117">오디오/비디오</span><span class="sxs-lookup"><span data-stu-id="58564-117">Audio/Video</span></span>

<span data-ttu-id="58564-118">오디오/비디오 (A/V) 용 네트워크 인터페이스에 할당 된 외부 IP 주소를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="58564-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="58564-119">이 IP 주소는 공용 IP 주소 이거나 개인 IP 주소 범위의 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58564-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="58564-120">**NAT 사용 공용 IP 주소** 에 대 한 설정은 A/V 네트워크 인터페이스 또는 일반 서버에 대 한 외부 인터페이스에 사용 되는 공용 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58564-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="58564-121">**별도의 FQDN과 웹 회의에 대 한 IP 주소를 설정 하 고 A/V** 를 사용 하는 경우이 공용 IP 주소는 세 개의 외부 인터페이스 모두에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58564-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

