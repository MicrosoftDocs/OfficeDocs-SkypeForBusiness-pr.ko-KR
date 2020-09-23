---
title: Lync Server 2010용 Edge 서버 FQDN 설정 확장기
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 외부 설정에서 속성을 정의 하려면 다음을 구성 합니다.
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218249"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2f6d0-103">Lync Server 2010용 Edge 서버 FQDN 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="2f6d0-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2f6d0-104">**외부 설정**에서 속성을 정의 하려면 다음을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="2f6d0-105">웹 회의 및 오디오/비디오에 대해 고유 풀 FQDN 및 IP 주소를 정의 하려면 **웹 회의 및 A/V에 서로 다른 fqdn 및 ip 주소 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f6d0-106">별도의 FQDN 및 IP 주소에 대 한 확인란을 선택 하지 않으면에 지 서버에서 제공 하는 세 가지 서비스 각각에 대해 개별 포트를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="2f6d0-107">구성할 정규화 된 도메인 이름은 액세스에 지 서비스에 연결 된 FQDN 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="2f6d0-108">A/V에 지 서비스에서 NAT (network address translation) IP 주소 및 구성을 사용 하도록 하려면 **a/v에 지 서비스는 nat 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="2f6d0-109">사용 하도록 설정 된에 지 서비스의 경우 **풀 FQDN** 과 **포트 아래에 포트가 입력** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="2f6d0-110">서비스를 고유 하 게 식별 하는 포트 및 **액세스에 지 서비스** 풀 FQDN을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="2f6d0-111">**웹 회의에 지 서비스** 풀 FQDN (웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용을 선택 하지 않은 경우) 및 서비스를 고유 하 게 식별 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="2f6d0-112">**A/v에 지 서비스** 풀 FQDN (웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용을 선택 하지 않은 경우) 및 서비스를 고유 하 게 식별 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="2f6d0-113">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2f6d0-114">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2f6d0-115">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6d0-115">**Help** Displays this help screen.</span></span>
  

